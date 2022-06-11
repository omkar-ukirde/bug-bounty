This will always have random stuff regarding bug bounty study

# 1. google dork for XSS </br>
    inurl:”.php?searchst­ring=” </br>
    inurl:”.php?keyword=” </br>
# 2. One liner XSS tester
    waybackurls adafruit.com | grep "=" | grep -v ".css\|.js" | qsreplace -a | kxss
