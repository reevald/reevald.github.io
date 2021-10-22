---
layout: post
title: "Cara Install Flask di Localhost"
tagline: "Catatan Flask"
description: "Belajar menginstall Flask di Localhost."
category: [Tutorial]
tags: [Flask, Python, Backend, Framework, Web]
---
{% include JB/setup %}

## Overview

### Apa itu Flask?

Berdasarkan Wikipedia: Flask adalah kerangka kerja aplikasi web bersifat kerangka kerja mikro yang ditulis dalam bahasa pemrograman Python dan menggunakan dependensi Werkzeug dan Jinja2.

### Contoh Penggunaan Flask

Aplikasi yang menggunakan Flask antara lain adalah Pinterest, LinkedIn, dan halaman web komunitas situs Flask itu sendiri.

## Instalasi Flask

### Langkah 1 : Install Python

Untuk windows : [https://www.petanikode.com/python-windows/](https://www.petanikode.com/python-windows/)  
Untuk linux : [https://docs.python-guide.org/starting/install3/linux/](https://docs.python-guide.org/starting/install3/linux/)

### Langkah 2 : Buat Virtual Environment

	python3 -m venv FlaskEnv

Setelah dibuat kemudian kita aktifkan virtual environmentnya

Untuk windows :

	FlaskEnv\Scripts\activate

Untuk linux :

	source FlaskEnv/bin/activate

### Langkah 3 : Install Flask di Virtual Environment

Pastikan sudah diaktifkan environmentnya, untuk menginstal Flask ketikan :

	pip install flask

### Langkah 4 : Membuat Aplikasi Flask "Hello World"

Struktur direktori aplikasi yang akan dibuat:

	.
    |-- app
        |-- __init__.py
        |-- routes.py
    |-- public
    |-- main.py

Isi file \_\_init__.py :

	from flask import Flask
	app = Flask(__name__)
	from app import routes

Isi file routes.py :

	from app import app
	@app.route('/')
	@app.route('/index')
	def index():
	    return "Hello, World!"

Isi file main.py :

	from app import app

Untuk menjalankannya, pertama kita atur dulu variabel FLASK_APP:

Pastikan sudah berada di root folder project.
Untuk windows:

	set FLASK_APP=main.py

Untuk linux:

	export FLASK_APP=main.py

Setelah itu baru kita jalankan untuk kita lihat hasilnya via browser:

	flask run

Output :

<img src="{{ HOME_PATH }}assets/images/output-flask-run.PNG" class="img-responsive" />

Jika kita buka via browser akan diperoleh :

<img src="{{ HOME_PATH }}assets/images/flask-run-browser.PNG" class="img-responsive" />

## Referensi
- [The Flask Mega-Tutorial Part I: Hello, World!](https://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-i-hello-world).
- [Flask Python](https://husite.notion.site/Flask-Python-09c8d6ab7f9943b5b87d986302f2d4e9)
