# Assignment-2
SQL
DROP DATABASE IF EXISTS movie;
CREATE database movie;


CREATE TABLE users (userID int not null auto_increment, 
firstname varchar(20),
lastname varchar(20),
primary key (userID));


INSERT INTO users (firstname, lastname) VALUES
('Fawad','Younus'),
('Saad','Younus'),
('Mariam','Shabbir'),
('Wajidul','Hussain'),
('Atib','Ali');

CREATE TABLE movies (
movieID int not null auto_increment,
title varchar (30),
genre varchar(20),
RottenTom float,
primary key (movieID));


INSERT INTO movies (title, genre, RottenTom) VALUES
('Crazy Rich Asians','Action',9.3),
('The Meg','Action',4.6),
('Mission Impossible','Action',9.7),
('Christopher Robin','Family',7.0),
('The Nun','Horror',2.8),
('Incredibles 2','Animation',9.4);

 
CREATE TABLE reviews(
userID int,
movieID int,
userrating int);

INSERT INTO reviews (userID, movieID, userrating) VALUES
(1,1,4),(1,2,4),(1,3,3),(1,4,4),(1,5,4),(1,6,5),
(2,1,3),(2,2,3),(2,3,2),(2,4,5),(2,5,5),(2,6,3),
(3,1,5),(3,2,5),(3,3,5),(3,4,4),(3,5,5),(3,6,3),
(4,1,4),(4,2,3),(4,3,2),(4,4,2),(4,5,4),(4,6,3),
(5,1,5),(5,2,3),(5,3,3),(5,4,4),(5,5,4),(5,6,3);

SELECT users.firstname, users.lastname, movies.title, movies.genre, movies.RottenTom, reviews.userrating from reviews
JOIN users on users.userID = reviews.userID
JOIN movies on reviews.movieID = movies.movieID
ORDER BY title;
