# 🇷🇺 Русская Рулетка для Файлов  
*(Russian File Roulette)*

> **A suicidal Python script that randomly deletes a file from your project.**  
> **All code, comments, strings, and error messages are in Russian – for extra immersion.**

[![Python](https://img.shields.io/badge/python-3.6+-blue?logo=python)](https://python.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Maintained? да](https://img.shields.io/badge/maintained%3F-да-red)](#)
[![Code language: Russian](https://img.shields.io/badge/code%20language-Russian%20Cyrillic-white)](#)
[![Stars](https://img.shields.io/github/stars/brolookslikeanfish67-hub/russian-roulette-real?style=social)](#)

---

## ⚠️ WARNING – READ BEFORE YOU RUN  
**This script will permanently delete a random file from the folder you run it in.**  
No recycle bin. No `undo`. No mercy.

- ❌ Do NOT run it inside your thesis folder.  
- ❌ Do NOT run it on production servers.  
- ❌ Do NOT run it on your boss’s laptop (unless you recorded a reaction video).  
- ❌ Do NOT run it at all – unless you are prepared to lose a beloved file forever.

**You have been warned.** But if you’re still reading, you probably already decided to do it.

---

##  What is this?

Russian File Roulette is a tiny Python script that does exactly what the name suggests:

1. Scans all files in the current working directory (except itself).  
2. Selects one at random (`random.choice`).  
3. Asks for your final confirmation: `да` (yes) or `нет` (no).  
4. Deletes the file permanently if you answer `да`.  

Everything inside the script – variables, functions, comments, and terminal output – is written in **Русский язык** so debugging feels like an intense KGB interrogation.

---

##  FULL SETUP GUIDE  
*(Even your babushka can do it.)*

### 1. Prerequisites  
- **Python 3.6+** installed on your machine.  
  Check with:  
  ```bash
  python --version
If you don't have it, download from python.org.

2. Get the script
You have two ways:

Option A – Clone the repo (recommended for cool people)
Bash

git clone https://github.com/brolookslikeanfish67-hub/russian-roulette-real.git
cd russian-roulette-real
Option B – Create the script manually
Create a new folder somewhere safe (NOT inside important projects).
Inside that folder, create a file named удалитель.py.
Copy and paste the complete Russian code below into that file.
<details> <summary>Click to reveal the full source code (русский код)</summary>
Python

#!/usr/bin/env python3
# -*- coding: utf-8 -*-

import os
import random

def получить_список_файлов():
    """
    Возвращает список всех файлов в текущей директории,
    исключая сам этот скрипт.
    """
    файлы = []
    for элемент in os.listdir('.'):
        if os.path.isfile(элемент) and элемент != os.path.basename(__file__):
            файлы.append(элемент)
    return файлы

def удалить_случайный_файл():
    файлы = получить_список_файлов()
    if not файлы:
        print("Нет файлов для удаления. Повезло, товарищ!")
        return

    жертва = random.choice(файлы)
    print(f"Случайный выбор пал на: {жертва}")
    подтверждение = input("Вы уверены, что хотите удалить этот файл? (да/нет): ")

    if подтверждение.lower() == 'да':
        os.remove(жертва)
        print(f"Файл {жертва} был удалён. Прощай, товарищ!")
    else:
        print("Трусость спасла файл. Но Сталин бы не оценил.")

if __name__ == "__main__":
    print("=" * 50)
    print("Русская рулетка для файлов. Запускай на свой страх и риск!")
    print("=" * 50)
    удалить_случайный_файл()
</details>
3. (Optional) Make it executable
On Linux/macOS you can do:

Bash

chmod +x удалитель.py
4. Run the roulette
In your terminal, navigate to the folder containing the script and execute:

Bash

python удалитель.py
or, if you made it executable:

Bash

./удалитель.py
5. What will happen?
You will see something like this:

text

==================================================
Русская рулетка для файлов. Запускай на свой страх и риск!
==================================================
Случайный выбор пал на: important_business_logic.py
Вы уверены, что хотите удалить этот файл? (да/нет):
If you type да and press Enter – the file is gone. Instant.
If you type нет – the file stays, but a digital ghost of Stalin will judge you.

 Safety (lol)
The script never deletes the file without confirmation (unless you have the future “Stalin Mode”).
It will not delete its own удалитель.py (so you can keep playing).
There is absolutely no undo. Not even os.undelete() exists.
“Trust me, I am a Russian programmer.”
– No sane person ever.

 Roadmap for other devs if they want to make this better cuz i aint (coming chaos)
Stalin Mode (--без-спроса): No confirmation – file is deleted instantly. Pure adrenaline.
Gulag Backup (--гулаг): Instead of deletion, the file is exiled to a ГУЛАГ/ folder. Rehabilitation possible.
Web Edition: A front-end with a spinning revolver that “deletes” uploaded files with a dramatic animation.
GitHub Action: Automatically play roulette on every commit. Imagine your CI pipeline deleting a random test file. 
PRs are welcome – but we do not guarantee any reasoning behind them.

 Why?
GitHub needed more chaotic energy.
To prove that code can be deadly and completely unreadable at the same time.
Because Russian sounds perfect when something terrible is happening.
You ever wanted to “accidentally” delete a colleague’s script? Now you can (but don’t, really).

If you accidentally nuked your passwords.txt, open an issue  I will read it and laugh.
