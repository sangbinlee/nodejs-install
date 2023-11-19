# nodejs-install
nodejs-install


![image](https://github.com/sangbinlee/nodejs-install/assets/4024414/8df787ca-e894-435f-b253-e6d5decce4c7)







# node --version
  sangbinlee9@master:~$ node --version
  v12.22.9


# install nginx
    sudo apt update
    sudo apt install nginx




# sudo ufw app list
    sangbinlee9@master:~$ sudo ufw app list
    Available applications:
      Nginx Full
      Nginx HTTP
      Nginx HTTPS
      OpenSSH


# sudo ufw enable

# sudo ufw status





#  systemctl status nginx
    
    sangbinlee9@master:~$ systemctl status nginx
    ● nginx.service - A high performance web server and a reverse proxy server
         Loaded: loaded (/lib/systemd/system/nginx.service; enabled; vendor preset: enabled)
         Active: active (running) since Mon 2023-11-20 01:51:03 KST; 5min ago
           Docs: man:nginx(8)
        Process: 3657 ExecStartPre=/usr/sbin/nginx -t -q -g daemon on; master_process on; (code=exited, status=0/SUCCESS)
        Process: 3658 ExecStart=/usr/sbin/nginx -g daemon on; master_process on; (code=exited, status=0/SUCCESS)
       Main PID: 3752 (nginx)
          Tasks: 5 (limit: 18901)
         Memory: 7.7M
            CPU: 33ms
         CGroup: /system.slice/nginx.service
                 ├─3752 "nginx: master process /usr/sbin/nginx -g daemon on; master_process on;"
                 ├─3754 "nginx: worker process" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" ""
                 ├─3755 "nginx: worker process" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" ""
                 ├─3756 "nginx: worker process" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" ""
                 └─3757 "nginx: worker process" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" ""
    
    Nov 20 01:51:03 master systemd[1]: Starting A high performance web server and a reverse proxy server...
    Nov 20 01:51:03 master systemd[1]: Started A high performance web server and a reverse proxy server.
    sangbinlee9@master:~$






# http://sodi9.store/


![image](https://github.com/sangbinlee/nodejs-install/assets/4024414/eb0e7eab-f552-46a9-858d-62e4746335c9)






#  curl sodi9.store
    
    sangbinlee9@master:~$ curl sodi9.store
    <!DOCTYPE html>
    <html>
    <head>
    <title>Welcome to nginx!</title>
    <style>
        body {
            width: 35em;
            margin: 0 auto;
            font-family: Tahoma, Verdana, Arial, sans-serif;
        }
    </style>
    </head>
    <body>
    <h1>Welcome to nginx!</h1>
    <p>If you see this page, the nginx web server is successfully installed and
    working. Further configuration is required.</p>
    
    <p>For online documentation and support please refer to
    <a href="http://nginx.org/">nginx.org</a>.<br/>
    Commercial support is available at
    <a href="http://nginx.com/">nginx.com</a>.</p>
    
    <p><em>Thank you for using nginx.</em></p>
    </body>
    </html>
    sangbinlee9@master:~$



# nginx

    sudo systemctl stop nginx
    sudo systemctl start nginx
    sudo systemctl restart nginx
    
    //만약 설정 변경을  리로드 할 수 있다. 
    sudo systemctl reload nginx
    
    //디폴트로, Nginx는 서버가 부팅될 때 자동으로 스타트  disable 
    sudo systemctl disable nginx
    
    //다시 위 설정 enable하기
    sudo systemctl enable nginx







#  sudo vi /etc/nginx/sites-available/sodi9.store

    sangbinlee9@master:~$ sudo vi /etc/nginx/sites-available/sodi9.store
    
    
    server {
    
            listen 80;
            listen [::]:80;
    
            server_name sodi9.store www.sodi9.store;
    
            location / {
                    proxy_pass http://127.0.0.1:3000;
            }
    }





#  sudo ln -s /etc/nginx/sites-available/sodi9.store /etc/nginx/sites-enabled/
    sudo ln -s /etc/nginx/sites-available/sodi9.store /etc/nginx/sites-enabled/




# sudo ln -s /etc/nginx/sites-available/sodi9.store /etc/nginx/sites-enabled/
    
    sangbinlee9@master:~$  sudo ln -s /etc/nginx/sites-available/sodi9.store /etc/nginx/sites-enabled/


# sudo vi /etc/nginx/nginx.conf
    
    sangbinlee9@master:~$ sudo vi /etc/nginx/nginx.conf


        server_names_hash_bucket_size 64;





![image](https://github.com/sangbinlee/nodejs-install/assets/4024414/02e42558-dc34-42b9-bc86-15e545b92900)




#  sudo nginx -t
    
    
    sangbinlee9@master:~$  sudo ln -s /etc/nginx/sites-available/sodi9.store /etc/nginx/sites-enabled/
    sangbinlee9@master:~$ sudo vi /etc/nginx/nginx.conf
    sangbinlee9@master:~$ sudo vi /etc/nginx/nginx.conf
    sangbinlee9@master:~$ sudo nginx -t
    [sudo] password for sangbinlee9:
    nginx: the configuration file /etc/nginx/nginx.conf syntax is ok
    nginx: configuration file /etc/nginx/nginx.conf test is successful
    sangbinlee9@master:~$




# cd /etc/nginx/sites-available/


    
    sangbinlee9@master:~$ cd /etc/nginx/sites-available/
    sangbinlee9@master:/etc/nginx/sites-available$ ll
    total 16
    drwxr-xr-x 2 root root 4096 Nov 20 02:07 ./
    drwxr-xr-x 8 root root 4096 Nov 20 02:40 ../
    -rw-r--r-- 1 root root 2412 May 31 02:31 default
    -rw-r--r-- 1 root root  140 Nov 20 02:07 sodi9.store
    sangbinlee9@master:/etc/nginx/sites-available$



# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 
# 






