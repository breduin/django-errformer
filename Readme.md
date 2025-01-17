# Errformer

# Install

# Parameters

- ERRFORMER_ADMIN_CHAT_ID - Telegram chat id
- ERRFORMER_INCLUDE_TRACEBACK - Include traceback in message
- ERRFORMER_PROJECT_NAME - Project name

# Usage

- Add `TelegramErrformerHandler` to logging handlers

```python
LOGGING = {
    "handlers": {
        "telegram": {"class": "errformer.handlers.TelegramErrformerHandler"},
    },
}
```

- Add `ErrformerMiddleware` to middleware

```python
MIDDLEWARE = [
    ...
    "errformer.middleware.ErrformerMiddleware",
]
```
