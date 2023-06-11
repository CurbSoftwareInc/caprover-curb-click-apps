## Tooljet Env Variables

[ToolJet Env Vars Docs Source](https://docs.tooljet.com/docs/setup/env-vars)

| Variable                       | Description                                                                 |
|--------------------------------|-----------------------------------------------------------------------------|
| `TOOLJET_HOST`                 | The public URL of ToolJet client (e.g., `https://app.tooljet.com`)          |
| `SECRET_KEY_BASE`              | Secret key base                                                             |
| `LOCKBOX_MASTER_KEY`           | Lockbox master key                                                          |
| `DATABASE_URL`                 | Database URL (e.g., `postgres://username:password@hostname:port/database_name?sslmode=disable`) |
| `COMMENT_FEATURE_ENABLE`       | Enable comment feature (true/false)                                         |
| `ENABLE_MULTIPLAYER_EDITING`   | Enable multiplayer editing feature (true/false)                             |
| `ENABLE_MARKETPLACE_FEATURE`   | Enable marketplace feature (true/false)                                     |
| `ENABLE_MARKETPLACE_DEV_MODE`  | Enable marketplace development mode (true/false)                            |
| `ENABLE_TOOLJET_DB`            | Enable ToolJet database (true/false)                                        |
| `TOOLJET_DB`                   | ToolJet database (default value is `tooljet_db`)                            |
| `TOOLJET_DB_HOST`              | Database host                                                               |
| `TOOLJET_DB_USER`              | Database username                                                           |
| `TOOLJET_DB_PASS`              | Database password                                                           |
| `TOOLJET_DB_PORT`              | Database port                                                               |
| `PGRST_JWT_SECRET`             | JWT token client provided for authentication                                |
| `PGRST_HOST`                   | PostgREST database host                                                     |
| `SERVER_HOST`                  | Configure a hostname for the server as a proxy pass. Defaults to `server`   |
| `DEFAULT_FROM_EMAIL`           | From email for the email fired by ToolJet                                   |
| `SMTP_USERNAME`                | SMTP username                                                               |
| `SMTP_PASSWORD`                | SMTP password                                                               |
| `SMTP_DOMAIN`                  | SMTP domain or host                                                         |
| `SMTP_PORT`                    | SMTP port                                                                   |
| `SLACK_CLIENT_ID`              | Client ID of the Slack app                                                  |
| `SLACK_CLIENT_SECRET`          | Client secret of the Slack app                                              |
| `GOOGLE_CLIENT_ID`             | Google client ID                                                            |
| `GOOGLE_CLIENT_SECRET`         | Google client secret                                                        |
| `GOOGLE_MAPS_API_KEY`          | Google Maps API key                                                         |
| `APM_VENDOR`                   | Application performance monitoring vendor                                   |
| `SENTRY_DNS`                   | DSN tells a Sentry SDK where to send events                                 |
| `SENTRY_DEBUG`                 | Enable Sentry debugging (true/false, default is false)                      |
| `TOOLJET_SERVER_URL`           | The URL of ToolJet server (e.g., `https://server.tooljet.com`)              |
| `NODE_EXTRA_CA_CERTS`          | Absolute path to certificate PEM file (e.g., `/ToolJet/ca/cert.pem`)        |
| `DISABLE_PASSWORD_RETRY_LIMIT` | Disable the password retry check (true/false)                               |
| `PASSWORD_RETRY_LIMIT`         | Change the default password retry limit (5)                                 |
| `DISABLE_TOOLJET_TELEMETRY`    | Disable ToolJet telemetry (true/false)                                      |
| `SSO_GOOGLE_OAUTH2_CLIENT_ID`  | Google OAuth client ID                                                      |
| `SSO_GIT_OAUTH2_CLIENT_ID`     | GitHub OAuth client ID                                                      |
| `SSO_GIT_OAUTH2_CLIENT_SECRET` | GitHub OAuth client secret                                                  |
| `SSO_GIT_OAUTH2_HOST`          | GitHub OAuth

