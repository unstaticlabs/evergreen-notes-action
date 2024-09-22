# evergreen-notes-action

Transform markdown notes into an evergreen notes website.

## Usage

```yaml
name: Evergreen Notes
on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Build
        uses: unstaticlabs/evergreen-notes-action
          
      - name: Install SSH Client 🔑
        uses: webfactory/ssh-agent@v0.5.1
        with:
          ssh-private-key: ${{ secrets.DEPLOY_KEY }}

      - name: Deploy 🚀
        uses: JamesIves/github-pages-deploy-action@releases/v3
        with:
          SSH: true
          BRANCH: gh-pages
          FOLDER: www
```
