# gmail_fetch
Collect mail from Gmail accounts, filter and store locally.


## WHY?

Because you have several Gmail accounts and would like to retrieve mail to
local folders so you can read and handle email faster and more convenient.


## WHAT?

gmail_fetch is a solution for retrieving Gmail from different accounts,
logging in via Oauth2, filtering the mail according to the rules you set up
and storing the mail into local imap folders. There is also a gmail_smtp
included for sending mail via Oauth2. It works out-of-the box as long as you
have gmail_fetch set up according to the recipe found with `gmail_fetch -h`. 


## HOW?

Simply put the file "gmail_fetch" into a folder in your defined PATH. Rename
the file "gmail.conf" to ".gmail.conf". Put the file into your home directory.
Edit the file ".gmail.conf" to include the path to the files ".mail" and
".mail2" as well as to the possibly created file "dead.letter". 

Add filter rules to each remote server so that gmail_fetch knows where to
deliver the retrieved mail. Just follow the examples in the files, and you'll
be fine.

You need to have Ruby installed to run gmail_fetch.

My "conkyrc" is included as an example of how you can get visual notice of the
mail_fetch running, network being unreachable, inability to login to local imap 
or remote servers and new mail count for the mail folders you decide to keep a 
tab on.

For more conky magic, check [my conky bar setup](https://github.com/isene/conky).

Run `gmail_fetch -h` to see the full help file, including the full docs to
set up your Ouath login to Gmail.

This repo is a continuation of my previous [mailfetch repo](https://github.com/isene/mailfetch). 
Since Google decided to drop Gmail logins by username/password, I had to
rewrite the solution to accommodate for the Oauth2 logins.

## WHEN?

Add an entry as a cron job using "crontab -e" that lookes like this:

```
* * * * * /home/yourusername/bin/gmail_fetch >/dev/null 2>&1
```

## WHO?

Uncopyrighted and released into the Public Domain by Geir Isene (https://isene.com)
