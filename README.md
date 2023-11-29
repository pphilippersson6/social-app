# Social app
This is a social media website. It allows users to post, like, comment on posts and follow each other. It is created using the django-rest-framework

## Project scope
1. A user can create an account
2. A user can log into the account they created.
3. A user can see all posts shared
4. A user can add a post.
5. A user can like a post.
6. A user can comment on a post.

## Running the program
```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python3 manage.py runserver
```

## models
### user
A user is the person interacting with the app.
A user has:
- name
- email
- password

### post
A post is created by a user and belongs to a user.
It includes
- title
- content

### likes
A like belongs to a user and a post
It has the following fields:
- user_id
- post_id

### comments
A comment is created for a post by a user
It contains:
- user
- post
- content

## Apis
This app contains the following endpoints:
POST user/signup/
POST user/login/
POST post/create/
POST user/like_post/
POST user/comment_post/
POST user/follow/
GET user/following/
GET user/followers/
GET user/posts/
GET post/all_posts/
PUT post/edit/<int:id>
DELETE post/delete/<int:id>/
GET post/view/<int:id>/
POST user/unfollow/
POST user/like_post/<int:post_id>/
POST user/unlike_post/<int:post_id>/
POST user/logout/

## Authentication
All endpoints excluding `POST user/signup/` and `POST user/login/` are authenticated using a jwt token that is given to the user during login and it is passed as a header
```
'Authorization': 'Bearer <token'
```

## Database
This project uses the sqlite database for storing data.

