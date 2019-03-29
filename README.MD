# Automatically update Google Domian Dynamic DNS with Script & Crontab

### Add a Dynamic DNS
![](https://i.imgur.com/JAEvhVr.png)

### Get the Username & Password

Get them with click on the "view credentials" and paste it into dynamicDNS_update.sh
```
#!/bin/bash

USERNAME="*******************"
PASSWORD="*******************"
HOSTNAME="foo.example.com"

# Resolve current public IP
IP=$(curl ifconfig.me)

# Update Google DNS Record
URL="https://${USERNAME}:${PASSWORD}@domains.google.com/nic/update?hostname=${HOSTNAME}&myip=${IP}"
curl -s $URL
```

### Crontab
Automatically update your Public IP to Dynamic DNS every minutes
```
$ crontab -e
```
Add this into your crontab and save
```
* * * * * /your/path/to/dynamicDNS_update.sh
```

Learn more about crontab:
- https://crontab.guru/


### Author
- Jacky Tan 陳翰弘

### Support
<a href="https://www.buymeacoffee.com/4zyD1tw" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: auto !important;width: auto !important;" ></a>

