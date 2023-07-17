# passwd

```
this command is used to changes password for the users 
```

### How to delete a password for the user
`sudo passwd -d [username]`

### How to lock a account so that use can't login
`sudo passwd -d [username]`

### How to unlock a account so that use can login
`sudo passwd -u [username]`

### How to pass a password from standard output as standard input to this command
`sudo passwd --stdin [username]`

### How to delete a password from a user, so that usercan login without any password
`sudo passwd -d [username]`

### How to get status for the user's password
`sudo passwd -S [username]`
```
this output will have following field
1. user's login name
2. type of password user has ( PS | LK | NP )
3. last date when password was changed 
4. minimum expiry age and maximum expiry age
5. warning period for the password
6. inactivity period for the password 
```


