# farookphuket.com
> ***farookphuket.com*** is the Laravel+NextJS+TailwindCSS project which I use to start to learn NextJS and hoping to replace my personal blog with nextjs in the future


## last update

---
## date 2 Oct 2022
just commit the source code to githup

---

## index page 
[index_page]:https://archive.org/download/arch_linux_myconfig_24-aug-2022_edit/see-next_001_index.png

![index_page]


## Login page
[login_page]:https://archive.org/download/arch_linux_myconfig_24-aug-2022_edit/see-next_002_login-page.png
![login_page]

## Register page
[register_page]:https://archive.org/download/arch_linux_myconfig_24-aug-2022_edit/see-next_003_register-page.png

![register_page]

## Admin page
[admin_page]:https://archive.org/download/arch_linux_myconfig_24-aug-2022_edit/see-next_004_admin-page.png

![admin_page]

## Member page
[member_page]:https://archive.org/download/arch_linux_myconfig_24-aug-2022_edit/see-next_005_member-page.png

![member_page]


# how to use this source code
> got lazy to read [? watch the video](#watch-the-video)

by clone this repo into your folder in my case i will do it on the /srv/http folder that i have setup apache server to host my web project on `http://farook.x22` already open the terminal program run :

`cd /srv/http/farook.x22`
`git clone https://github.com/farookphuket/farookphuket.com.git .`

now the source code is copy into my `/srv/http/farook.x22` folder make sure i'm in the folder by command `pwd` now

in the folder `farook.x22/api` let edit the file `.env.EXAMPLE` by change it name to `.env` then edit the line below

```
APP_URL=http://farook.x22
FRONTEND_URL=http://farook.x22:3022
SESSION_DOMAIN=.farook.x22


DB_CONNECTION=sqlite

# make sure you have replace the below name to your name
DB_DATABASE=/srv/http/farook.x22/api/DB/DB.sqlite

```

you may realize that there is no folder call `vendor` represent here that because the vendor folder is too big to upload to git it will take too much time so that's why I remove it , after you edit the line above in .env file then run ***(make sure you're in `/srv/http/farook.x22/api` folder)*** `composer update` to get the folder `vendor` back

to avoid from `cors origin error` we need to edit the config file because we're not using port 3000 for our frontend let edit file `sanctum.php` that live in `api/config/sanctum.php` make sure you have appended `farook.x22` and `farook.x22:3022` after `127.0.0.1:8000,`

```

    'stateful' => explode(',', env('SANCTUM_STATEFUL_DOMAINS', sprintf(
        '%s%s%s',
        'localhost,localhost:3000,127.0.0.1,127.0.0.1:8000,farook.x22,farook.x22:3022,::1',
        env('APP_URL') ? ','.parse_url(env('APP_URL'), PHP_URL_HOST) : '',
        env('FRONTEND_URL') ? ','.parse_url(env('FRONTEND_URL'), PHP_URL_HOST) : ''
    ))),


```

 

as i mention above that i have setup apache server for host my project so now i can open the web browser at `http://farook.x22` now i can the `laravel version`


the next step is to connect `nextJS` frontend

`cd nextjs` now when you in this folder you will realize that 2 folders has missing `node_modules` and `.next` this 2 folders are important but to push to githup it take too much time so I have to delete it first

now let edit file `.env.local.EXAMPLE` to `.env.local` then edit the below line to your info

```
NEXT_PUBLIC_BACKEND_URL=http://farook.x22
NEXT_PUBLIC_FRONTEND_ORIGIN=http://farook.x22:3022

NEXT_PUBLIC_APP_TITLE="farookphuket"
NEXT_PUBLIC_MY_WEBSITE="farookphuket"

NEXT_PUBLIC_MY_PHONE_NUMBER="+66 95 954 3920,+66 81 397 4489"
NEXT_PUBLIC_MY_EMAIL="firefrook@gmail.com"


```

now run `npm install && npm run dev` open the web browser at `http://farook.x22:3022` you should see the index page. 


so let go hacking!!



# watch the video
> will create the video in the future baby
