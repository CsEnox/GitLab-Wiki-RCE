# GitLab-Wiki-RCE
RCE Exploit for Gitlab &lt; 13.9.4

- RCE via unsafe inline Kramdown options when rendering certain Wiki pages
- Allows any user with push access to a wiki to execute arbitrary ruby code.

### Usage
```bash
python3 exploit.py -u root -p password -c "commandhere" -t "http://gitlab.example.com"
```

### Credits
- https://hackerone.com/reports/1125425 ( vakzz ) 
- Also referred some code from here [here](https://github.com/ctrlsam/GitLab-11.4.7-RCE)
