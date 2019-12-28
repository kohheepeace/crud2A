# crud2A
- Crud2A is a list of tutorial of application: **CRUD** with **Authentication** and **Authorization**.

## Purpose
Many programming frameworks have it's tutorial page.

Example:
- https://reactjs.org/tutorial/tutorial.html
- https://vuejs.org/v2/guide/
- https://redux.js.org/basics/basic-tutorial

etc...


But for me their tutorial is sometimes confusing ...😕

So the purpose of crud2A is **to standardize these tutorials**.

## Crud2A Spec


## Authentication Header:

`Authorization: Bearer 'accessToken-here'`

## Endpoints:

### Authentication(Login):

`POST /login`
```json
{
  "email": "hogehoge@example",
  "password": "hogehoge"
}
```

### User Registration(Sign Up):

`POST /users`
```json
{
  "email": "hogehoge@example",
  "password": "hogehoge"
}
```

Required fields: `email`, `password`

### Get Current User

`GET /me`

Authentication required, returns a current logged in user.

```json
{
  "email": "hogehoge@example",
  "password": "hogehoge"
}
```

### Get All Posts

`GET /posts`
```json
[
  {
    "id": 1,
    "title": "Hogehoge title",
    "content": "hogehoge content",
    "user_id": 1,
    "created_at": "2019-12-23T11:56:54.855Z",
    "updated_at": "2019-12-23T12:43:25.120Z"
  },
  {
    "id": 2,
    "title": "Hugahuga title",
    "content": "hugahuga content",
    "user_id": 3,
    "created_at": "2019-12-25T04:48:57.971Z",
    "updated_at": "2019-12-25T04:48:57.971Z"
  }
]
```


### Get My Posts

`GET /me/posts`
```json
[
  {
    "id": 1,
    "title": "My Hogehoge title",
    "content": "my hogehoge content",
    "user_id": 1,
    "created_at": "2019-12-23T11:56:54.855Z",
    "updated_at": "2019-12-23T12:43:25.120Z"
  },
  {
    "id": 2,
    "title": "My Hugahuga title",
    "content": "my hugahuga content",
    "user_id": 3,
    "created_at": "2019-12-25T04:48:57.971Z",
    "updated_at": "2019-12-25T04:48:57.971Z"
  }
]
```

Authentication required, will return current_user's posts.

### Create Post

`POST /posts`
```json
{
  "title": "Hogehoge Title",
  "content": "hogehoge content",
}
```

Authentication required, will return a single post.

Required fields: `title`, `content`


### Update Post

`PUT /posts/:id`
```json
{
  "title": "Hogehoge Title",
  "content": "hogehoge content",
}
```

Authentication required, returns the updated post.

Optional fields: `title`, `content`


### Delete Post

`DELETE /posts/:id`

Authentication required.

## Refs
https://api.stackexchange.com/docs