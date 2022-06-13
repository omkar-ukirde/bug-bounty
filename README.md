## This will always have random stuff regarding bug bounty study

### 1. Google dork to learn on real websites XSS </br>
    inurl:”.php?searchst­ring=” </br>
    inurl:”.php?keyword=” </br>
### 2. One liner XSS tester
    waybackurls adafruit.com | grep "=" | egrep -iv ".(jpg|jpeg|gif|css|tif|tiff|png|ttf|woff|woff2|ico|svg|js)" | qsreplace -a | kxss | possibly-reflected-XSS.txt
    gospider -S targets_urls.txt -c 10 -d 5 --blacklist ".(jpg|jpeg|gif|css|tif|tiff|png|ttf|woff|woff2|ico|pdf|svg|txt)" --other-source | grep -e "code-200" | awk '{print $5}'| grep "=" | qsreplace -a | dalfox pipe | tee result.txt
### 3. Google Dork to find login page with OTP
    intext:"Sign in with OTP"
