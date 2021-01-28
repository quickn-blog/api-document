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
#[derive(Clone, Copy, Debug, PartialEq, Eq)]
pub enum AccountError {
    Nothing,
    PassNotMatched,
    UserNotExists,
}
```