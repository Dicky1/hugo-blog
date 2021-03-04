+++
author = "Dicky Setiono"
title = "Deploy guhogo di netlify"
date = "2021-03-04"
tags = [ "hugo","deploy" ]
categories = [ "Hugo" ]
series = ["Themes Guide"] 
aliases = ["migrate-from-jekyl"]
+++

## Apa itu Hugo?
Hugo adalah salah satu static site generators open source yang paling populer yang di develop menggunakan Go.

Hugo mengambil direktori sumber file dan template yang akan digunakan sebagai ide untuk pembuatan situs web, situs web yang dibangun menggunakan hugo sangat cepat dan aman 

## Feature Di Hugo

* Hugo is the fastest tool of its kind. <1ms perhalaman rata rata build situs kurang dari satu detik
* Hugo mendukung unlimited content types, taxonomies, menu, dynamic API-driven content, dan masih banyak lagi
* sintaks markdown di hugo sangat sederhana dan fleksibilitas
* Hugo memberikan dukungan i18n untuk situs multi bahasa
* Dan yang terakhir hugo memberikan kita untuk menulis konten dalam berbagai format seperti JSON atau AMP

## Persiapan Deploy Hugo Di Netlify

Sebelum kita deploy ada beberapa hal yang harus di persiapkan : 

1. web hugo yang sudah siap untuk di hosting
2. Akun git (Github/Gitlab/Bitbucker)
3. Akun Netlify

Silahkan pergi ke [Netlify](https://app.netlify.com/) dan pilih metode pendaftaran yang kalian sukai. __"disarankan menggunakan akun git"__ 

![img](https://d33wubrfki0l68.cloudfront.net/0e9f9cefe968382536d4e4baa66e49945ad2694c/e20ef/images/hosting-and-deployment/hosting-on-netlify/netlify-signup.jpg)

Pilih Github dan akan muncul modal authorization untuk authentication. Pilih __"Athorize Application"__

![img](https://d33wubrfki0l68.cloudfront.net/66276caf9e5deee836ba60fab50f78f6074e3ca0/0cc43/images/hosting-and-deployment/hosting-on-netlify/netlify-first-authorize.jpg)

Tahap selanjutnya akan muncul dashboard baru kamu, pilih __"New site from git"__

![img](https://d33wubrfki0l68.cloudfront.net/1a92de85be074abc024967fa7088c8b719c32466/f7496/images/hosting-and-deployment/hosting-on-netlify/netlify-add-new-site.jpg)

Netlify kemudian akan memberikan langkah langkah yang diperlukan, kamu harus memilih opsi git lagi dan kali ini anda memberi netlify izin ke repo kamu

![img](https://d33wubrfki0l68.cloudfront.net/742c7be22b24a5df82a39f7cd259a04a7abdd150/db696/images/hosting-and-deployment/hosting-on-netlify/netlify-create-new-site-step-1.jpg)

Dan sekali lagi muncul modal Github Authorization

![img](https://d33wubrfki0l68.cloudfront.net/dd85bd12e419baeb7ef56e45c43235d2004ce341/77531/images/hosting-and-deployment/hosting-on-netlify/netlify-authorize-added-permissions.jpg)

Selanjutnya pilih repo yang ingin kamu gunakan. Jika kamu memiliki banyak repository kamu dapat memfilternya menggunakan pencarian repo

![img](https://d33wubrfki0l68.cloudfront.net/188f9bfa9eb4997757414ec0ac1979d7111c9741/8f7a6/images/hosting-and-deployment/hosting-on-netlify/netlify-create-new-site-step-2.jpg)

Setelah dipilih, kamu akan di bawa ke tampilan persiapan. Disini kamu dapat memilih branch untuk di deploy

## Cara konfigurasi versi hugo di netlify

pada projek kamu silahkan tambah file __*netlify.toml*__

```toml
[build]
publish = "public"
command = "hugo --gc --minify"

[context.production.environment]
HUGO_VERSION = "0.81.0"
HUGO_ENV = "production"
HUGO_ENABLEGITINFO = "true"

[context.split1]
command = "hugo --gc --minify --enableGitInfo"

[context.split1.environment]
HUGO_VERSION = "0.81.0"
HUGO_ENV = "production"

[context.deploy-preview]
command = "hugo --gc --minify --buildFuture -b $DEPLOY_PRIME_URL"

[context.deploy-preview.environment]
HUGO_VERSION = "0.81.0"

[context.branch-deploy]
command = "hugo --gc --minify -b $DEPLOY_PRIME_URL"

[context.branch-deploy.environment]
HUGO_VERSION = "0.81.0"

[context.next.environment]
HUGO_ENABLEGITINFO = "true"
```
## Build and Deploy Site

Di console netlify piliy __"Deploy Site"__ dan kamu akan diarahkan ke console untuk memastikan build kamu berhasil atau tidak

![img](https://d33wubrfki0l68.cloudfront.net/a9f55d92792a554cb775cd0d10eddf445338b83a/0a424/images/hosting-and-deployment/hosting-on-netlify/netlify-deploying-site.gif)

Nah itu dia cara deploy hugo di netlify, jika masih ada yang belom jelas silahkan tinggalkan pesan di menu contact
