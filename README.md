# WAF Payload Collection

This project was created to help provide rigorous tests for Web Application Firewalls (WAFs) rules.\
You can use these payloads to ensure the expected response is received from a sent payload or to check the efficacy of a WAF solution.\
Some false positives are included to test if an acceptable payload is incorrectly identified as malicious.

The payloads were divided into their respective categories, duplicates, comments, blank lines, etc. were removed. Data has been cleaned as good as possible to contain as much real/working payloads as possible.\
To check for bypasses, most XSS payloads exist three times - with *alert()*, *prompt()* and *confirm()* - since WAFs may block only *alert()*.

## Sources
Payloads from the following Github repositories and web pages are included:

- [SecLists "Fuzzing"](https://github.com/danielmiessler/SecLists/tree/master/Fuzzing): LFI, SQLi, XSS, XML-FUZZ, XSS-Fuzzing, XXE-Fuzzing and Polygots
- [Foospidy's Payloads](https://github.com/foospidy/payloads/tree/master/other): XSS, SQLi and code injection payloads
- [PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings): [XXE Injection](https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/XXE%20Injection), [Comman Injection](https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/Command%20Injection/Intruder), [dotdotpwn.txt](https://raw.githubusercontent.com/swisskyrepo/PayloadsAllTheThings/master/Directory%20Traversal/Intruder/dotdotpwn.txt), [Traversal.txt](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/File%20Inclusion/Intruders/Traversal.txt), [JHADDIX_LFI.txt](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/File%20Inclusion/Intruders/JHADDIX_LFI.txt), [SQL Injection](https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/SQL%20Injection/Intruder) and [XSS Injection](https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/XSS%20Injection/Intruders) payloads
- [Awesome-WAF](https://github.com/0xInfection/Awesome-WAF#known-bypasses): Exotic WAF bypasses
- [WAF Efficacy Framework](https://github.com/fastly/wafefficacy/tree/main/nuclei/payloads): payloads and most of its false positives
- [WAF community bypasses](https://github.com/waf-bypass-maker/waf-community-bypasses/blob/main/payloads.twitter.csv)
- [SQLi](https://github.com/wallarm/gotestwaf/blob/master/testcases/owasp/sql-injection.yml) and [Community SQLi](https://github.com/wallarm/gotestwaf/blob/master/testcases/community/community-sqli.yml), [XML](https://github.com/wallarm/gotestwaf/blob/master/testcases/owasp/xml-injection.yml) and [Community XXE](https://github.com/wallarm/gotestwaf/blob/master/testcases/community/community-xxe.yml), [XSS](https://github.com/wallarm/gotestwaf/blob/master/testcases/owasp/xss-scripting.yml) and [Community XSS](https://github.com/wallarm/gotestwaf/blob/master/testcases/community/community-xss.yml) of [GoTestWAF](https://github.com/wallarm/gotestwaf/tree/master/testcases) and most of its [false positives](https://github.com/wallarm/gotestwaf/blob/master/testcases/false-pos/texts.yml).
- Payloadbox's [XXE Injection Payload List](https://github.com/payloadbox/xxe-injection-payload-list/blob/master/Intruder/xxe-injection-payload-list.txt.txt)
- Payloadbox's [SQL Injection Payload List](https://github.com/payloadbox/sql-injection-payload-list)
- Log4Shell Payloads from [Ox4Shell](https://github.com/ox-eye/Ox4Shell#description), [Log4Shell hell](https://www.scmagazine.com/native/ransomware/log4shell-hell-anatomy-of-an-exploit-outbreak) and [log4shell-analysis](https://github.com/righettod/log4shell-analysis/tree/main/payloads)
- Shellshock payloads are taken from [Inside Shellshock](https://blog.cloudflare.com/inside-shellshock/) and [Tishna](https://github.com/marciopocebon/Tishna/blob/master/shellshock.sh)

The last day of access on them was October 07, 2022.

## How to use

Payloads can be found in *nuclei/payloads/[category]/true-positives.txt* \
You can use any tool of your choice for testing, because they are just simple text files with one payload per line. \
However, this repository was created for use with [WAF Efficacy Framework](https://github.com/fastly/wafefficacy) in mind.

### WAF Efficacy Framework

WAF Efficacy Framework was chosen because it is free, open source, modular and allows easy integration of new test scenarios/payloads. It is user-friendly, actively developed and standardized. Last but not least all requests are recorded and logged in JSON format and include request/response pairs and additional metadata.

- **nuclei/config.yaml**\
  Config file for Nuclei

- **nuclei/templates**\
  Contains YAML template files for Nuclei

- **nuclei/payloads**\
  Contains payloads (true/false positives) in text files

Just clone the repository and overwrite the contents of the nuclei folder with the one in this repository.
Then run the tool as usual.


## Disclaimer

We do not claim any copyright. This is just a collection of payloads from different sources.
Most of them are MIT licensed and you have to comply to the rules of the licenses used.
