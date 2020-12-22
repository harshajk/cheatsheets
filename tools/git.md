# Git

## Set the username/email for a specific repository
```
git config user.name "Your project specific name"i
git config user.email "your@project-specific-email.com" 
```

### Verify your settings
```
git config --get user.name
git config --get user.email
```

## Set the username/email globally
```
git config --global user.name "Your global username"
git config --global user.email "your@email.com"
```

### Verify your settings:
```
git config --global --get user.name
git config --global --get user.email
```

## Set the username/email system wide
```
git config --system user.name "Your default name"
git config --system user.email "your@system-email.com"
```

### Verify your settings:

git config --system --get user.name
git config --system --get user.email

