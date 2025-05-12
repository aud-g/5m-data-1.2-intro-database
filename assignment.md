# Assignment

## Brief

Create an ERD for each of the following case study question.

## Instructions

Paste the answer as DBML in the answer code section below each question.

### Question 1

Construct an ERD for a social media company whose database includes information about users, their followers, and the posts that they make. Users can follow multiple users and create multiple posts.

Each entity has the following attributes:

- User: id, username, email, created_at
- Post: id, title, body, user_id, status, created_at
- Follows: following_user_id, followed_user_id, created_at

Answer:

```dbml
Table User {
  id int [pk, increment]
  username varchar
  email varchar
  created_at timestamp
}

Table Post {
  id int [pk, increment]
  title varchar
  body text
  user_id int [ref: > User.id]
  status varchar
  created_at timestamp
}

Table Follows {
  following_user_id int [ref: > User.id, pk]
  followed_user_id int [ref: > User.id, pk]
  created_at timestamp
}

```

### Question 2

Construct an ERD for a company that sells books online. The company has a website where customers can browse available books and add them to their shopping carts. Each cart can contain multiple books.

There are 4 entities, think of what attributes each entity should have.

- Customer
- Book
- Cart
- CartItem

Answer:

```dbml
Table Customer {
  id int [pk, increment]
  name varchar
  email varchar
  address varchar
}

Table Book {
  id int [pk, increment]
  title varchar
  author varchar
  price decimal
  isbn varchar
}

Table Cart {
  id int [pk, increment]
  customer_id int [ref: > Customer.id]
  created_at datetime
}

Table CartItem {
  cart_id int [ref: > Cart.id, pk]
  book_id int [ref: > Book.id, pk]
  quantity int
}
```

## Submission

- Submit the URL of the GitHub Repository that contains your work to NTU black board.
- Should you reference the work of your classmate(s) or online resources, give them credit by adding either the name of your classmate or URL.
