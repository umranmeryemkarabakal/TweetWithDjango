# TweetWithDjango

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white" alt="Django" />
  <img src="https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white" alt="SQLite" />
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5" />
</p>

## Overview

A small Twitter-like web app built with Django 5: users sign up, log in, post short messages and delete their own. The same “add tweet” flow is implemented three ways: a plain HTML form, a Django Form and a ModelForm.

**Quick start:** `pip install -r requirements.txt && python djangotweet/manage.py runserver`

## Proje hakkında

Django 5 ile yazılmış, Twitter benzeri küçük bir web uygulaması. Kullanıcılar kayıt olup giriş yapabilir, kısa mesaj paylaşabilir ve kendi mesajlarını silebilir. “Tweet ekleme” akışı üç farklı yolla yazılmıştır: düz HTML formu, Django Form ve ModelForm.

## Özellikler

- Kayıt, giriş ve çıkış (Django auth)
- Tweet listeleme, ekleme ve silme
- HTML formu / `forms.Form` / `ModelForm` karşılaştırması
- Şablon kalıtımı (`base.html`) ve özel CSS

## Kurulum ve çalıştırma

```bash
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

```bash
cd djangotweet
python manage.py migrate
python manage.py createsuperuser   # isteğe bağlı, admin paneli için
python manage.py runserver
```

Ardından `http://127.0.0.1:8000/tweetapp/` adresini açın.

## Dosya yapısı

```text
TweetWithDjango/
└── djangotweet/
    ├── djangotweet/
    │   ├── __init__.py
    │   ├── asgi.py
    │   ├── settings.py
    │   ├── urls.py
    │   └── wsgi.py
    ├── templates/
    │   ├── registration/  (2 dosya)
    │   └── base.html
    ├── tweetapp/
    │   ├── migrations/  (3 dosya)
    │   ├── static/  (1 dosya)
    │   ├── templates/  (4 dosya)
    │   ├── __init__.py
    │   ├── admin.py
    │   ├── apps.py
    │   ├── forms.py
    │   ├── models.py
    │   ├── tests.py
    │   ├── urls.py
    │   └── views.py
    └── manage.py
```

## Notlar

- `settings.py` içindeki `SECRET_KEY` yalnızca yerel geliştirme içindir; yayına alınacaksa ortam değişkenine taşınmalıdır.
- Veritabanı dosyası (`db.sqlite3`) depodan çıkarıldı; ilk çalıştırmada `migrate` ile oluşturulur.
