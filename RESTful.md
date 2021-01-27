<div align="center">
    <h1>
        RESTful API
    </h1>
</div>

> NOTE THAT ALL RESPONSE ARE `JSON`

## Reponse block

```Rust
{
    status: bool,
    body: Option<ResponseBody>,
}
```

## GET /api/ping

Send ping to server

### ResponseBody
```Rust
{
    reply: String, // pong!
}
```

## GET /api/account_service/info?jwt={token}

Get user id (primary key) in database by JWT token

ResponseBody
```Rust
{
    username: String,
    nickname: String,
    email: String,
    level: AccountLevel,
}
```