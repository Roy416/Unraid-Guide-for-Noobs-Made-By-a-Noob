1. Go to Authelia's appdata folder and open users_database.yml. 
2. Copy and paste the existing user. Make sure the indentation is the same!
3. Open the terminal and type the command below. As before, the random password is what the user will log into Authelia with.
```
docker run --rm authelia/authelia:latest authelia crypto hash generate argon2 --random --random.length 64 --random.charset alphanumeric
```
4. Paste the digest in password. Change the remaining fields.
