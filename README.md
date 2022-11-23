# Anofuss Remote

Run command on host via ssh without depending on untrusted/unknown docker images or javascript libraries.

In other words: a no fuss action to run a remote command.

## Requirements

Depends on `openssh` (present in ubuntu-latest).

Paste the _private key_ (`SSH_KEY`) and _known_hosts_ (`KNOWN_HOST`) into two specific Actions secrets.

## Usage

### Minimal configuration

```yaml
runs-on: ubuntu-latest
steps:
- name: Restart daemon
  uses: vacare/anofuss-remote@v1
  with:
    host: example.com
    username: deploy
    key: ${{ secrets.SSH_KEY }}
    known_hosts: ${{ secrets.KNOWN_HOSTS }}
    command: /after-build.sh
```

## See also

Combine with
[Anofuss Upload](https://github.com/vacare/anofuss-upload) to upload file before and after commands.
