# TensorBoard

## Prerequisites

```
pip install tensorboard==1.14.0
pip uninstall tensorboard-plugin-wit
```

## Run TensorBoard

```
tensorboard --logdir ./log/
```

## Using TensorBoard for Logging

### TensorFlow
```
# Using model.fit(callback)
log_dir = "logs/fit/" + datetime.datetime.now().strftime("%Y%m%d-%H%M%S")
tensorboard_callback = tf.keras.callbacks.TensorBoard(log_dir=log_dir, histogram_freq=1)

model.fit(x=x_train,
          y=y_train,
          epochs=5,
          validation_data=(x_test, y_test),
          callbacks=[tensorboard_callback])

# Using tf.GradientTape()
def train_step(model, optimizer, x_train, y_train):
  with tf.GradientTape() as tape:
    predictions = model(x_train, training=True)
    loss = loss_object(y_train, predictions)
  grads = tape.gradient(loss, model.trainable_variables)
  optimizer.apply_gradients(zip(grads, model.trainable_variables))

train_summary_writer = tf.summary.create_file_writer(train_log_dir)

for epoch in range(EPOCHS):
  for (x_train, y_train) in train_dataset:
    train_step(model, optimizer, x_train, y_train)
  with train_summary_writer.as_default():
    tf.summary.scalar('loss', train_loss.result(), step=epoch)
    tf.summary.scalar('accuracy', train_accuracy.result(), step=epoch)


```

### PyTorch
```
from torch.utils.tensorboard import SummaryWriter

# Writer will output to ./runs/ directory by default
writer = SummaryWriter()

writer.add_image('images', grid, 0)
writer.add_graph(model, images)
writer.add_scalar('Loss/train', np.random.random(), n_iter)

writer.close()
```