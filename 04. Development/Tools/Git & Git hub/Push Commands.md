bash

```bash
git add .
git commit -m "notes: $(date '+%Y-%m-%d %H:%M')"
git push origin main
```

If your branch is `master`:

bash

```bash
git push origin master
```

First-time setup (if not done):

bash

```bash
git init
git remote add origin https://github.com/yourusername/your-repo.git
git branch -M main
git push -u origin main
```