# Display Name Spoof Prevention
This script was inspired by a **sharp increase** in the rate of **Display-Name spoofing** that I've seen during the duration of my work in Email Security, Business-to-Business, enterprise, and even small-town IT.

It is designed to digest a name (_usually an executive or authority of sorts_) and spit out an email "**Header-From**" filter for that name. This generated filter will match all email _FROM:_ patters regardless of the reply-to email in the header.

Here's a sample output from the script...
```
[zack@AMD64-arch ~]$ ./ceo_filter_gen.sh "John Y. Smith" -c
Regex successfully generated for name "John Y. Smith"!
Please enter this into the content filters section of an ESG/ESS for headers.

From:\s*"?\s*((J(\.|[Oo0]h?n(a[Tt7]han|a[Tt7]h[Oo0]n|ny|n[IiLl1]{0,2}[Ee3])?)?(\s+Y\.?)?\s+[Ss5]m[IiLl1]{0,2}[Tt7]h)|([Ss5]m[IiLl1]{0,2}[Tt7]h,?\s+J(\.|[Oo0]h?n(a[Tt7]han|a[Tt7]h[Oo0]n|ny|n[IiLl1]{0,2}[Ee3])?)?(\s+Y\.?)?))\s*"?\s+<

For confidence, test the Regex here: https://regoio.herokuapp.com/
PLEASE NOTE: THE TESTER ABOVE IS CASE-SENSITIVE!!!
```

Seriously. That output will match any case too.
It will match the name "**John Y. Smith**" in the following header variations:
```
From: "jon SmiTH <jsmith@legit.enterprise.net>" <fake@spammer.net>
From:    "  Sml7h, Johnathon "   <notreally@yahoo.net>
From: J Y 5m1th <somefakeaddress@gmail.com>
From:"Smith, J" <other@fake.address>
```
You get the point...

_Please note: I've recently updated the custom John rule to include Johnny/Jonny._

## What is Display-Name spoofing?

## Why?

## Prevention and Detection

## Dangers of Open-Source
Some may be concerned by me releasing the regular expressions some admins might use to filter display names.

To quell those fears, I should note that this project is intended to _inspire_ other formulas, solutions, and knowledge of email content filters to improve an administrator's role in **protecting their users**, as their job title states.

By writing this project up in a few days (both as a brainstorm and to automate a frequent task), I am trying to demonstrate to others that a solution to these common problems can be easily drafted with a little effort.

---

## TO-Do
Things to still check off the list for this project will be listed here, as well as any bugs to fix.

[ ] **Expand** the predefined list of names that have variations _(like Zack, Joe, & Mary)_.
[ ] Improve **string scanning** for the built regex to lessen the impact of _potential script errors_.
[ ] Finish this README document.
