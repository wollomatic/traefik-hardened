# certificate storage

```
touch acme.json
sudo chown 2000:2000 acme.json
sudo chmod 600 acme.json
```

for the dns challenge example, you need to create a separate file:
```
touch acmedns.json
sudo chown 2000:2000 acmedns.json
sudo chmod 600 acmedns.json
```
