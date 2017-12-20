```
Câu 1: Tạo database như hình trên (sau khi tạo thì import database, sẽ gửi sau)
CREATE DATABASE `train_mysql` DEFAULT CHARACTER SET utf8 COLLATE utf8_unicode_ci;

CREATE TABLE IF NOT EXISTS `user`(
    `id` INT(11) NOT NULL AUTO_INCREMENT,
    `fullname` VARCHAR(255),
    `email` VARCHAR(255),
    `rank` VARCHAR(255),
    `is_active` TINYINT(1),
    `create_at` TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
    PRIMARY KEY(`id`)
);

CREATE TABLE IF NOT EXISTS `category` (
  `id` INT(11) NOT NULL AUTO_INCREMENT,
  `title` VARCHAR(255),
  `description` VARCHAR(255),
  PRIMARY KEY(`id`)
);

CREATE TABLE IF NOT EXISTS `news`(
	`id` INT(11) NOT NULL AUTO_INCREMENT,
    `category_id` INT(11) NOT NULL,
    `title` VARCHAR(255),
    `view` INT(11),
    `is_active` TINYINT(1),
    `content` TEXT,
    `created_at` TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
    `updated_at` TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
    PRIMARY KEY(`id`),
    FOREIGN KEY(`category_id`) REFERENCES category(id)
);

CREATE TABLE IF NOT EXISTS `comment`(
	`id` INT(11) NOT NULL AUTO_INCREMENT,
    `target_table` VARCHAR(20),
    `target_id` INT(11),
    `user_id` INT(11) NOT NULL,
    `comment` TEXT,
    `create_at` TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
    `updated_at` TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
    PRIMARY KEY (`id`),
    FOREIGN KEY (`user_id`) REFERENCES user(id)
);

CREATE TABLE IF NOT EXISTS `follow`(
	`id` INT(11) NOT NULL AUTO_INCREMENT,
    `from_user_id` INT(11) NOT NULL,
    `to_user_id` INT(11) NOT NULL,
    `created_at` TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    PRIMARY KEY(`id`),
    FOREIGN KEY (`from_user_id`) REFERENCES user(id)
);

CREATE TABLE IF NOT EXISTS `blog`(
	`id` INT(11) NOT NULL AUTO_INCREMENT,
    `category_id` INT(11) NOT NULL,
    `user_id` INT(11) NOT NULL,
    `title` VARCHAR(255),
    `view` INT(11),
    `is_active` TINYINT(1),
    `content` TEXT,
    `created_at` TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
    `updated_at` TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
    PRIMARY KEY (`id`),
    FOREIGN KEY (`category_id`) REFERENCES category(`id`),
    FOREIGN KEY (`user_id`) REFERENCES user(`id`)
);

Import Database
use train_mysql;
source /only_data.sql;
```
