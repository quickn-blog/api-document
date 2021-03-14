<div align="center">
    <h1>
        Structures
    </h1>
</div>

## AccountLevel

```Rust
#[derive(Clone, Copy, Debug, PartialEq, Eq)]
pub enum AccountLevel {
    Default = 0,
    Admin = 1,
}
```

## AccountError

```Rust
#[derive(Clone, Copy, Debug, PartialEq, Eq, Deserialize, Serialize)]
pub enum AccountError {
    Nothing,
    PassNotMatched,
    UserNotExists,
    DatabaseError,
    UsernameAlreadyExists,
    EmailAlreadyExists,
    NetworkError,
    PasswordVerifyFailed,
}
```

## BlogError

```Rust
#[derive(Clone, Copy, Debug, PartialEq, Eq, Deserialize, Serialize)]
pub enum BlogError {
    Nothing,
    AuthError,
    DatabaseError,
    NetworkError,
    PermissionError,
    TooShortTitle,
    TooShortBody,
    InvalidTags,
}
```

## AccountToken

```Rust
#[derive(Clone, Copy, Debug, PartialEq, Eq, Deserialize, Serialize)]
pub struct AccountToken {
    pk: i32,
}
```