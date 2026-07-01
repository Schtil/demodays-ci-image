# demodays-ci-image

Базовый образ для GitLab CI задания «Мини-поисковик по заявкам» (`python:3.12-slim-bookworm` + `git` + `ca-certificates`).

Собирается и публикуется в GHCR при пуше в `main`:

```text
ghcr.io/schtil/demodays-ci-image:latest
```

Нужен, чтобы `.gitlab-ci.yml` в `mini-search-template` / `mini-search-reference-solution` не ставил `git`/`ca-certificates` через `apt-get` на каждый job, а брал готовый образ.

## Первая публикация

После первого успешного workflow пакет в GHCR по умолчанию **приватный**, даже если репозиторий публичный. Один раз вручную: GitHub → профиль → Packages → `demodays-ci-image` → Package settings → Change visibility → Public. Иначе GitLab-раннеры не смогут анонимно вытащить образ.
