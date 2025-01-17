# Errformer

Send errors and logs to Telegram chat.

# Install

```bash
pip install django-errformer
```

# Parameters

*settings.py:*

- ERRFORMER_ADMIN_CHAT_ID - Telegram chat id (your Telegram chat id, required)
- ERRFORMER_INCLUDE_TRACEBACK - Include traceback in message (default: True)
- ERRFORMER_PROJECT_NAME - Project name (not required)

# Usage

- Add `TelegramErrformerHandler` to logging handlers

```python
LOGGING = {
    "handlers": {
        "level": "INFO",
        "telegram": {"class": "errformer.handlers.TelegramErrformerHandler"},
    },
    "loggers": {  # loggers for django.request, set your app name here
        "django": {
            "handlers": ["telegram", "console"],  # set handlers
            "level": "INFO",  # set log level
        },
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

Find DjangoErrformerBot in Telegram and tell it '/start', so that it can send messages to you.

# License

MIT
