# acme.sh
Install wildcard ssl with acme.sh manually

1. Install acme.sh

2. Issue ssl:
```
acme.sh --issue -d domain.com -d '*.domain.com' --dns --yes-I-know-dns-manual-mode-enough-go-ahead-please
```

3. Follow instruction from console to verify your domain with TXT-record

4. Cmd (like step 2 but with --renew param):
```
acme.sh --issue -d domain.com -d '*.domain.com' --dns --yes-I-know-dns-manual-mode-enough-go-ahead-please --renew
```

5. Isntall ssl
```
acme.sh --install-cert -d domain.com \
--key-file /etc/ssl/private/domain.com.key \
--fullchain-file /etc/ssl/certs/domain.com.crt
```

6. Use it (with nginx for example)
```
ssl_certificate /etc/ssl/certs/domain.com.crt;
ssl_certificate_key /etc/ssl/private/domain.com.key;
```
