# renovate-config

![CI](https://github.com/paweloczadly/renovate-config/actions/workflows/ci.yml/badge.svg)

Centralized Renovate configuration used across my personal and OSS repositories. The goal is to keep dependencies up to date across all projects using one secure, GitHub App–based setup.

---

## ⚙️ How it works

- Renovate runs **only in this repository** using a GitHub Actions workflow.
- Authentication uses a **GitHub App** (`renovate-oczadly-io`), not a PAT.
- Multiple repositories are updated via the `RENOVATE_REPOSITORIES` list.
- Individual projects only contain a minimal `.github/renovate.json`.

This setup keeps all logic, secrets and policies in one place.

---

## 🧩 Adding a new repository

1. Install the GitHub App: **https://github.com/apps/renovate-oczadly-io**.

2. Add the repository to `RENOVATE_REPOSITORIES` inside `.github/workflows/renovate.yml` in this repo.

3. Create `.github/renovate.json` in that repository:

```json
{
  "extends": ["local>paweloczadly/renovate-config//renovate/01-commons"]
}
```

---

## 📄 License

MIT.

---

## 👤 Author

Paweł Oczadły ([GitHub](https://github.com/paweloczadly) / [LinkedIn](https://linkedin.com/in/paweloczadly)).
