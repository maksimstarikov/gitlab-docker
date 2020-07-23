gitlab docker-compose image

```
docker run --detach \
    --hostname gitlab.maxistar.me \
    --publish 1080:80 --publish 1022:22 \
    --name gitlab \
    --volume /srv/gitlab/config:/etc/gitlab \
    --volume /srv/gitlab/logs:/var/log/gitlab \
    --volume /srv/gitlab/data:/var/opt/gitlab \
    gitlab/gitlab-ce:latest

```

```
docker-compose up
```

register runner:
```
docker run --rm \
-v /srv/gitlab-runner/config:/etc/gitlab-runner \
gitlab/gitlab-runner register \
--non-interactive   --executor "shell"   --url "http://plusdental.maxistar.me/" \
--registration-token "QnxbySk6E67GFwJvR7ya"   \
--description "bash-docker-runner" \
--tag-list "docker,aws"   --run-untagged="true"   \
--locked="false" \
--access-level="not_protected"
```
