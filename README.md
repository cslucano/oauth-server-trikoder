#Installing

##Generating public and private keys
Execute in the project root folder

###To generate the private key
```bash
openssl genrsa -out private.key 2048
```

###Extract the public key from the private key
```bash
openssl rsa -in private.key -pubout -out public.key
```

If needed edit `config/packages/trikoder_oauth2.yaml` 


Generate string password (parameter `encryption_key`)
```bash
php -r 'echo base64_encode(random_bytes(32)), PHP_EOL;'
```

Update the database
```bash
bin/console doctrine:schema:update --force
```



