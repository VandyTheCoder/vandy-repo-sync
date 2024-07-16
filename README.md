# Vandy Repo Sync
Vandy Repo Sync enables you to synchronize code to other code management platforms, such as GitLab, Gitee, etc.

## Try Git Repo Sync

You can use the following example as a template to create a new file with any name under `.github/workflows/`.

```yaml
name: <action-name>

on: 
  - push
  - delete

jobs:
  sync:
    runs-on: ubuntu-latest
    name: Git Repo Sync
    steps:
    - uses: actions/checkout@v2
      with:
        fetch-depth: 0
    - uses: VandyTheCoder/vandy-repo-sync@v0.0.2
      with:
        # Such as https://github.com/VandyTheCoder/vandy-repo-sync.git
        target-url: <target-url>
        # Such as vandy
        target-username: <target-username>
        # You can store token in your project's 'Setting > Secrets' and reference the name here. Such as ${{ secrets.ACCESS_TOKEN }}
        target-token: <target-token>
```
