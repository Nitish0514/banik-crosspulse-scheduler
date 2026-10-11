# Banik CrossPulse public scheduler

This repository contains only the public hourly scheduler workflow. The CrossPulse source repository remains private.

## Required repository secrets

Add these secrets under **Settings → Secrets and variables → Actions**:

- `CROSSPULSE_REPO_TOKEN`: fine-grained GitHub token restricted to `Nitish0514/banik-crosspulse-signals`, with Contents read/write.
- `CROSSPULSE_TELEGRAM_BOT_TOKEN`: the existing Telegram bot token.
- `CROSSPULSE_TELEGRAM_CHAT_ID`: the owner chat ID.
- `CROSSPULSE_CONTROL_API_SECRET`: the existing CrossPulse control secret.

The workflow is schedule-only and does not run code from pull requests. It checks out `main` from the private repository, runs one signal scan, and writes scanner state back to the private repository. Automatic CoinDCX orders remain disabled.

Do not paste secrets into files, issues, commits, or chat messages.
