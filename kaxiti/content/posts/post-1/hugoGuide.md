---
title: "Hugo blog guide"
date: 2023-03-21T12:03:52+02:00
author: "Odysseas Oikonomou"
---

Σε Αυτό το guide θα δείξω πως να στίσετε ένα *hugo* static blog.

Αρχικά πρέπει να εγκατασταθεί το hugo με το package manager επιλογής σας, προσκοπικά χρησιμοποιώ manjaro οπότε θα γίνει με την εντολή:

`sudo pacman -S hugo`

Μετά από Αυτό δημιουργούμε δυο repos στο github με ότι ονόματα θέλουμε, το ένα θα είναι local και το άλλο το production.


Στη δική μου περίπτωσή έχω το blog και το kaxiti.io.
Το kaxiti.io το κάνουμε
[github page](https://pages.github.com/).


κάνουμε clone το blog `git clone https://github.com/user/repo`

Μπαίνουμε στο αρχείο `cd /blog` και εκτελούμε `hugo new site <SITENAME>`

Τώρα μπορούμε να μπούμε στο [hugo themes](https://themes.gohugo.io/) και να διαλέξουμε ένα *look* για το Blog μας.


**ΠΡΟΣΟΧΗ** για να δουλέψει το theme ακολουθάμε προσεκτικά της οδηγίες του καθενός και κιριος το προσθέτουμε ως submodule και όχι locally!


*τιπ!* Κάποιες φορές πρέπει να γίνει αλαγη του config από yml σε toml.


Σε αυτό το σημείο αν κάνουμε `hugo server` μπορούμε να δούμε το blog μας locally.


# github pages hosting


Αρχικά στο `config.toml` αλλάζουμε το `baseURL = 'localhost'` σε `baseURL = 'livelink-του-github-pages'`


Διαγράφουμε το folder public και προσθέτουμε το δεύτερο repo μας ως submodule: `git submodule add -f https://github.com/<REPO>/ public`


στη συνέχεια με την εντολή `hugo -t <theme-name>` στήνουμε το submodule μας και είναι έτοιμο για push


`cd public`


`git add .`


`git commit -m "live site"`


`git push origin`


Αν όλα έχουν γίνει σωστά το site μας είναι live!
