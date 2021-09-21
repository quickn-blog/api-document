<div align="center">
    <h1>
        RESTful API
    </h1>
</div>

> NOTE THAT ALL REQUEST AND RESPONSE ARE `JSON`

## Reponse block

```Rust
{
    status: bool,
    body: Option<ResponseBody>,
}
```

## Account Service Request

```Rust
{
    token: String,
    body: Option<RequestBody>,
}
```

## GET /api/account_service/ping

Send ping to server.

### ResponseBody

```Rust
{
    reply: String, // pong!
}
```

## GET /api/account_service/get_user?pk={}

Get user information in the databaseby primary key

### ResponseBody

```Rust
{
    username: String,
    nickname: String,
    email: String,
    level: AccountLevel,
}
```

## GET /api/account_service/info?token={token}

Get user id (primary key) in the database by JWT token.

### ResponseBody

```Rust
{
    id: i64,
    username: String,
    nickname: String,
    email: String,
    level: AccountLevel,
}
```

## POST /api/account_service/login

Get login.

### Request

```Rust
{
    username: String,
    pass: String,
}
```

### ResponseBody

```Rust
{
    result: AccountError,
    token: Option<String>,
}
```

## POST /api/account_service/register

Register an account.

### Request

```Rust
{
    username: String,
    pass: String,
    email: String,
    nickname: String,
}
```

### ResponseBody

```Rust
{
    result: AccountError,
}
```

## GET /api/blog/count_posts

Return the number of posts in the database.

### ResponseBody

```Rust
{
    error: BlogError,
    count: i64,
}
```

## POST /api/blog/new_post

Create a new post.

### Reqiured service

- Account Service

### RequestBody

```Rust
{
    title: String,
    body: String,
    tag: Vec<String>,
}
```

### ResponseBody

```Rust
{
    result: BlogError,
}
```

## GET /api/blog/view_post?id={id}

Return the content of required post.

### RequestBody

```Rust
{
    id: i64,
}
```

### ResponseBody

```Rust
{
    result: BlogError,
    post: Option<PublicPost>,
}
```

## POST /api/blog/delete_post

Delete a new post.

### Reqiured service

- Account Service

### RequestBody

```Rust
{
    id: i64,
}
```

### ResponseBody

```Rust
{
    result: BlogError,
}
```

## GET /api/blog/recent_posts?count={count}

Get list of count of recently created posts.

### ResponseBody

```Rust
{
    error: BlogError,
    posts: Vec<i64>,
}
```

## POST /api/blog/edit_post

Modify a post.

### Reqiured service

- Account Service

### RequestBody

```Rust
{
    id: i64,
    title: String,
    body: String,
    tag: Vec<String>,
}
```

### ResponseBody

```Rust
{
    result: BlogError,
}
```

## GET /api/blog/posts?start={start}&count={count}

Get list of count of recently created posts from start.

### ResponseBody

```Rust
{
    error: BlogError,
    posts: Vec<PostHeader>,
}
```
