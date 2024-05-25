# Reconnaissance & Enumeration

BugBounty reconnaissance process should be maximally automated as we need to scan big scopes of systems and find the weakest ones.

You should know how to do basic [web enumeration](../ctf/web-exploitation/enumeration.md), and be able to use scripting language.&#x20;

An example of simple pipeline:

```bash
domain="ya.ru"
subfinder -d $domain -o subdomains.txt
cat subdomains.txt | httprobe > urls.txt
for url in $(cat urls.txt); do
    ffuf -w ~/Wordlists/SecLists/Discovery/Web-Content/common.txt -u $url/FUZZ >> all-subdirs.txt
done
```



### Using Osmedeus for automation

{% embed url="https://www.osmedeus.org/" %}

Osmedeus is a workflow engine for cybersecurity. It has several built-in pipelines and have a good integration with project-discovery tools
