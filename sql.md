# SQL CheatSheet

## MySQL/MariaDB

### Installation (Ubuntu18.04)
```
# Installation for MariaDB
sudo apt-get install mariadb-server mariadb-client
sudo mysql_secure_installation
```

### Enter/Exit CLI
```
# Enter
mysql -u $USER -p
# Exit
`Ctrl` + `d`
```

### Commands
#### Create user
```
CREATE USER 'username'@'%' IDENTIFIED BY 'password';
```

#### Grant user privileges
```
GRANT ALL PRIVILEGES ON *.* TO 'username'@'%';
FLUSH PRIVILEGES;
```

#### List schemas/tables
```
LIST DATABASES;
SHOW DATABASES;
USE database;
LIST TABLES;
```

#### List DB users
```
SELECT user, host, password FROM mysql.user;
```

#### Create schema
```
CREATE DATABASE IF NOT EXISTS db_name
CHARACTER SET utf8
COLLATE utf8_BIN
;
```

#### Delete schema
```
DROP DATABASE IF EXISTS db_name;
```

# Create table
```
CREATE TABLE `database`.`table` (
  `user_id` VARCHAR(20) NOT NULL,
  `user_name` VARCHAR(4) CHARACTER SET 'utf8' NOT NULL,
  PRIMARY KEY (`line_id`),
  FOREIGN KEY (task_id), 
    REFERENCES tasks (task_id) 
    ON UPDATE RESTRICT 
    ON DELETE CASCADE
)
```

# Alter table
```
ALTER TABLE tablename MODIFY columnname VARCHAR(20);
```

# Insert
```
INSERT INTO table (name, age) VALUES ('A', '10'), ('B', '9');
```

# Select
```
SELECT col 
FROM table 
WHERE condition 
GROUP BY col
HAVING condition
ORDER BY col 
LIMIT n;
```

# Update
```
UPDATE table SET col_1 = var_1 WHERE col_2 = var_2;
```

# Delete
```
DELETE FROM table WHERE col = var;
```

# Join
Inner Join ($A cap B$)