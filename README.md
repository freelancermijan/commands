<h1 align="center">wpscan</h1>

### Vulnerable plugin, themes, users
    wpscan --url https://wordpress.org -e vp,vt,u -o scanned.txt

### Vulnerable plugins, All plugins, Vulnerable themes, All themes, Timthumbs, Config backups, Db exports, User, Media
    wpscan --url https://wordpress.org -e vp,vt,tt,cb,dbe,u,m -v -o scanned.txt

### Password brute force attack
    wpscan --url https://wordpress.org -e u --passwords /usr/share/wordlists/rockyou.txt -o scanned.txt
