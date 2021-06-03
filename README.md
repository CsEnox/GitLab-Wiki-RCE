# GitLab-Wiki-RCE
RCE Exploit for Gitlab &lt; 13.9.4

- RCE via unsafe inline Kramdown options when rendering certain Wiki pages
- Allows any user with push access to a wiki to execute arbitrary ruby code.

### Usage
```bash
python3 exploit.py -u root -p password -c "commandhere" -t "http://gitlab.example.com"
```

### Environment
- Tested on Gitlab 13.9.1 CE
- Building your own test environment using docker :
```
export GITLAB_HOME=/srv/gitlab

sudo docker run --detach \
  --hostname gitlab.example.com \
  --publish 443:443 --publish 80:80 --publish 22:22 \
  --name gitlab \
  --restart always \
  --volume $GITLAB_HOME/config:/etc/gitlab \
  --volume $GITLAB_HOME/logs:/var/log/gitlab \
  --volume $GITLAB_HOME/data:/var/opt/gitlab \
  gitlab/gitlab-ce:13.9.1-ce.0
```

### Credits
- https://hackerone.com/reports/1125425 ( vakzz ) 
- Also referred some code from here [here](https://github.com/ctrlsam/GitLab-11.4.7-RCE)
