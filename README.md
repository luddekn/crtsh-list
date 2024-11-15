## About
A Python script aimed towards bug bounty hunters and penetration testers that outputs every result from a crt.sh search, removes any duplicate domain or subdomain from that result, and lets the user only output domains and subdomains that include a specific word, it also allows the user to save the results to a file to use in further enumeration!
## Installation
```
git clone https://github.com/luddekn/crtsh-list.git
```
Install the script requirements:
```
pip3 install -r requirements.txt
```
## Usage
```
usage: crtsh-list.py [-h] -d DOMAIN [-o OUTPUT] [-g GREP] [-fs FILTERS]

options:
  -h, --help            show this help message and exit
  -d DOMAIN, --domain DOMAIN
                        Provide the name of the domain you want to search for.
  -o OUTPUT, --output OUTPUT
                        Provide a name for the output file if you want to save the output.
  -g GREP, --grep GREP  Grep the output to only return results that include the name of the domain.
  -fs FILTERS, --filters FILTERS
                        Filter out specific words from the output, such as www. or *. for example, you can filter multiple words using a comma (example: -fs *.,www).
```
Output every result of the domain search:
```
python3 crtsh-list.py -d example.com
```
Filter the output to remove results:
```
python3 crtsh-list.py -d example.com -fs *.,www
```
Save every result of the domain search to a specified file (file gets created for you):
```
python3 crtsh-list.py -d example.com -o results.txt
```
Grep the output to only include results that include the specific keyword:
```
python3 crtsh-list.py -d example.com -g example.com
```
Save the grepped output to a specified file (file gets created for you):
```
python3 crtsh-list.py -d example.com -g example.com -o results.txt
```


