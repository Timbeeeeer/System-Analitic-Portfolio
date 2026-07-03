Create Table book (
    book_id Int Primary Key Auto_Increment,
    title Varchar(50),
    author_id Int Not Null,
    genre_id Int,
    price Decimal(8,2),
    amount Int,
    Foreign Key (author_id) References author (author_id) On Delete Cascade,
    Foreign Key (genre_id) References genre (genre_id) On Delete Set Null
    );


Select
    name_genre, title, name_author
    From book
    inner join genre on genre.genre_id = book.genre_id
    inner join author on author.author_id = book.author_id
    where name_genre = 'Роман'
    order by title;


SELECT name, city, date_first, date_last
    FROM trip
    WHERE DATEDIFF(date_last, date_first) = (
        SELECT MIN(DATEDIFF(date_last, date_first)) 
        FROM trip
    );








