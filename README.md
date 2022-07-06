## This will always have random stuff regarding bug bounty study

### Download DNS bruteforce ultimate file
    wget https://wordlists-cdn.assetnote.io/data/manual/best-dns-wordlist.txt -O /usr/share/wordlists/best-dns-wordlist.txt
### Find all subdomains using certificates, active bruteforcing DNS and sources like Shodan, etc.
    amass enum -active -d owasp.org -brute -src -ip -w /usr/share/wordlists/best-dns-wordlist.txt
### Google dork to learn on real websites XSS
    inurl:”.php?searchst­ring=”
    inurl:”.php?keyword=”
### One liner XSS tester
    waybackurls adafruit.com | grep "=" | egrep -iv ".(jpg|jpeg|gif|css|tif|tiff|png|ttf|woff|woff2|ico|svg|js)" | qsreplace -a | kxss | possibly-reflected-XSS.txt
    gospider -S targets_urls.txt -c 10 -d 5 --blacklist ".(jpg|jpeg|gif|css|tif|tiff|png|ttf|woff|woff2|ico|pdf|svg|txt)" --other-source | grep -e "code-200" | awk '{print $5}'| grep "=" | qsreplace -a | dalfox pipe | tee result.txt
    subfinder -d target.com | gau |  dalfox pipe
### Google Dork to find login page with OTP
    intext:"Sign in with OTP"
    
