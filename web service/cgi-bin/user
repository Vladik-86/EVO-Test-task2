#!/usr/bin/env python3

import cgi
import html

form = cgi.FieldStorage()
name = form.getfirst("user_name", "Введіть ім'я")
name = html.escape(name)

print("Content-type: text/html\n")
print()

with open('users.txt', encoding = 'UTF-8') as f:
    for line in f:
        if name in line.split():
            print("<p>Вже бачилися, {}</p>".format(name))
            break
    else:
        with open('users.txt', 'a', encoding = 'UTF-8') as f:
            f.write(name + '\n')
            print("<p>Привіт, {}</p>".format(name))
