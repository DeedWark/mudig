# Most Useful DIG commands in the same script

**To use this script**

- Install dns-utils :
```
sudo apt-get install dnsutils -y
```

and do that commands :

- to add into your bin :
```
sudo mv mudig /usr/bin/mudig
```

- if you don't want, you can just put an alias into your **.bashrc** file (add):
```
alias mudig='/usr/bin/dns'
```
- **How to use**:
  *You can just type the domain and the script will try to **resolve DKIM Key** with **Google** as selector*
```
mudig domain.com
```
- *You can put domain + selector : (To try to get the DKIM key)*
```
mudig domain.com mailjet
```

- Example : 
```
mudig domain.com
 DNS (A): 
89.88.87.86

 MX fields: 
1 aspmx.l.google.com.
5 alt1.aspmx.l.google.com.
5 alt2.aspmx.l.google.com.
10 alt3.aspmx.l.google.com.
10 alt4.aspmx.l.google.com.

 TXT records: 
"v=spf1 include:_spf.google.com ip4:10.11.12.13 -all"

 DMARC key:
"v=DMARC1; p=reject; pct=100; rua=mailto:meto@ag.dmarcian.com;
ruf=mailto:tome@fr.dmarcian.com; aspf=r;"

 DKIM key: 
Add a selector (ex: domain.com selector)

Try with Google as selector:
"v=DKIM1; k=rsa; p=FG0LfMyS0YtfHKrkUkBCEzfZs480LfMySxgi9f1w+7Z2IFG+AtUjrf8/9N3
gLieaZKZT1SEhR8TnhfOm" "FG0LfMyS0YtfHKrkUkBCEmFfe1862CcZBShKr6/T8/UB/oZF8XMRd0
NOsru6LGx9Yp89jIYS5YRuvbA0/TLgOOfGefwfFyy4BMDFadazF6BxNPc/+UoFrYHKRZp
yD/kEd4FDAd65ddlksQIDAQAB"
```

**TIPS for DIG command :**
- add a .digrc file (into your home for example) and write that in :
```
+nocmd +noall +answer
```
