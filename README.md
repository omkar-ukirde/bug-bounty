## This will always have random stuff regarding bug bounty study

### 1. Google dork to learn on real websites XSS </br>
    inurl:”.php?searchst­ring=” </br>
    inurl:”.php?keyword=” </br>
### 2. One liner XSS tester
    waybackurls adafruit.com | grep "=" | grep -v ".css\|.js" | qsreplace -a | kxss | possibly-reflected-XSS.txt
    gospider -S targets_urls.txt -c 10 -d 5 --blacklist ".(jpg|jpeg|gif|css|tif|tiff|png|ttf|woff|woff2|ico|pdf|svg|txt)" --other-source | grep -e "code-200" | awk '{print $5}'| grep "=" | qsreplace -a | dalfox pipe | tee result.txt
    assetfinder testphp.vulnweb.com | gau |  dalfox pipe
