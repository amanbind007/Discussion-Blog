# JSP-Servlet based Discussion Blog 
It is a Blog created using servlet and JSP.
It is for practice only.

Requirements
1. Apache Tomcat Server 9
2. MySql
3. Java JDBC Driver for MySql

MySQL Credential
user : root
password : dragonats@007

# Screenshots
Registration<br>
<img width="75%" src="https://github.com/amanbind007/Discussion-Blog/blob/master/Screenshot%202022-09-09%20at%2011.51.42%20AM.png?raw=true"><br>
login<br>
<img width="75%" src="https://github.com/amanbind007/Discussion-Blog/blob/master/Screenshot%202022-09-09%20at%2011.52.04%20AM.png?raw=true"><br>
Home Page<br>
![](https://github.com/amanbind007/Discussion-Blog/blob/master/chrome-capture-2022-8-9.gif?raw=true)<br>
Creating Post<br>
![](https://github.com/amanbind007/Discussion-Blog/blob/master/chrome-capture-2022-8-9%20(1).gif?raw=true)<br>
Viewing Post and Commenting on it<br>
![](https://github.com/amanbind007/Discussion-Blog/blob/master/chrome-capture-2022-8-9%20(2).gif?raw=true)<br>


# Database Schema
create database blog;<br>
CREATE TABLE blog.users(<br>
    id int primary key auto_increment,<br>
    username varchar(100) not null unique,<br>
    password varchar(100) not null,<br>
    email varchar(100) not null,<br>
    address varchar(100),<br>
    userRole varchar(20),<br>
    createDate timestamp<br>
) engine=InnoDB default charset=utf8;<br>
<br>
CREATE TABLE blog.post(<br>
    id int primary key auto_increment,<br>
    userId int,<br>
    title varchar(100) not null,<br>
    description varchar(300),<br>
    content longtext,<br>
    author varchar(100),<br>
    readCount int default 0,<br>
    createDate timestamp,<br>
    foreign key (userId) references users (id),<br>
    foreign key (author) references users (username)<br>
) engine=InnoDB default charset=utf8;<br>
<br>
CREATE TABLE blog.reply(<br>
    id int primary key auto_increment,<br>
    userId int,<br>
    postId int,<br>
    content varchar(300) not null,<br>
    author varchar(100),<br>
    createDate timestamp,<br>
    foreign key (userId) references users (id) on delete set null,<br>
    foreign key (postId) references post (id) on delete cascade,<br>
    foreign key (author) references users (username) on delete cascade<br>
) engine=InnoDB default charset=utf8;<br>

# WAR File
<a href = "">Link</a>

