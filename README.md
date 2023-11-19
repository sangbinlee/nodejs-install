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


    
    sangbinlee9@master:/etc/nginx/sites-available$ cd /etc/nginx/sites-enabled/
    sangbinlee9@master:/etc/nginx/sites-enabled$ ll
    total 8
    drwxr-xr-x 2 root root 4096 Nov 20 02:10 ./
    drwxr-xr-x 8 root root 4096 Nov 20 02:40 ../
    lrwxrwxrwx 1 root root   34 Nov 20 01:51 default -> /etc/nginx/sites-available/default
    lrwxrwxrwx 1 root root   38 Nov 20 02:10 sodi9.store -> /etc/nginx/sites-available/sodi9.store
    sangbinlee9@master:/etc/nginx/sites-enabled$
    





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



#  sudo systemctl restart nginx
sangbinlee9@master:/etc/nginx/sites-available$ sudo systemctl restart nginx
sangbinlee9@master:/etc/nginx/sites-available$




# http://sodi9.store/
![image](https://github.com/sangbinlee/nodejs-install/assets/4024414/317395df-3d8f-49f9-a790-1fab174071e3)



# Setting Up Server Blocks (Recommended)
    sudo mkdir -p /var/www/your_domain/html
    sudo chown -R $USER:$USER /var/www/your_domain/html
    sudo chmod -R 755 /var/www/your_domain

    
    nano /var/www/your_domain/html/index.html

    
        <html>
            <head>
                <title>Welcome to your_domain!</title>
            </head>
            <body>
                <h1>Success!  The your_domain server block is working!</h1>
            </body>
        </html>

    sudo nano /etc/nginx/sites-available/your_domain
    
        server {
                listen 80;
                listen [::]:80;
        
                root /var/www/your_domain/html;
                index index.html index.htm index.nginx-debian.html;
        
                server_name your_domain www.your_domain;
        
                location / {
                        try_files $uri $uri/ =404;
                }
        }

    sudo ln -s /etc/nginx/sites-available/your_domain /etc/nginx/sites-enabled/

#    sudo systemctl restart nginx

 
      
# How To Secure Nginx with Let's Encrypt on Ubuntu 22.04

    
    sudo snap install core; sudo snap refresh core
    sudo apt remove certbot
    sudo snap install --classic certbot
    sudo ln -s /snap/bin/certbot /usr/bin/certbot

    sudo nano /etc/nginx/sites-available/example.com
    
    ...
    server_name example.com www.example.com;
    ...
    
    sudo nginx -t

    sudo systemctl reload nginx

    sudo ufw status

    sudo ufw allow 'Nginx Full'
    sudo ufw delete allow 'Nginx HTTP'


    sudo ufw status

    sudo certbot --nginx -d sodi9.store -d www.sodi9.store

    
        
        
        sangbinlee9@master:/etc/nginx/sites-available$  sudo certbot --nginx -d sodi9.store -d www.sodi9.store
        Saving debug log to /var/log/letsencrypt/letsencrypt.log
        Enter email address (used for urgent renewal and security notices)
         (Enter 'c' to cancel): sangbinlee9@gmail.com
        
        - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
        Please read the Terms of Service at
        https://letsencrypt.org/documents/LE-SA-v1.3-September-21-2022.pdf. You must
        agree in order to register with the ACME server. Do you agree?
        - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
        (Y)es/(N)o: Y
        
        - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
        Would you be willing, once your first certificate is successfully issued, to
        share your email address with the Electronic Frontier Foundation, a founding
        partner of the Let's Encrypt project and the non-profit organization that
        develops Certbot? We'd like to send you email about our work encrypting the web,
        EFF news, campaigns, and ways to support digital freedom.
        - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
        (Y)es/(N)o: Y
        Account registered.
        Requesting a certificate for sodi9.store and www.sodi9.store
        
        Successfully received certificate.
        Certificate is saved at: /etc/letsencrypt/live/sodi9.store/fullchain.pem
        Key is saved at:         /etc/letsencrypt/live/sodi9.store/privkey.pem
        This certificate expires on 2024-02-17.
        These files will be updated when the certificate renews.
        Certbot has set up a scheduled task to automatically renew this certificate in the background.
        
        Deploying certificate
        Successfully deployed certificate for sodi9.store to /etc/nginx/sites-enabled/sodi9.store
        Successfully deployed certificate for www.sodi9.store to /etc/nginx/sites-enabled/sodi9.store
        Congratulations! You have successfully enabled HTTPS on https://sodi9.store and https://www.sodi9.store
        
        - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
        If you like Certbot, please consider supporting our work by:
         * Donating to ISRG / Let's Encrypt:   https://letsencrypt.org/donate
         * Donating to EFF:                    https://eff.org/donate-le
        - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -



    
    


# sudo systemctl status snap.certbot.renew.service
      
      
      sangbinlee9@master:/etc/nginx/sites-available$ sudo systemctl status snap.certbot.renew.service
      ○ snap.certbot.renew.service - Service for snap application certbot.renew
           Loaded: loaded (/etc/systemd/system/snap.certbot.renew.service; static)
           Active: inactive (dead)
      TriggeredBy: ● snap.certbot.renew.timer
      sangbinlee9@master:/etc/nginx/sites-available$
      
      

      
    
# sudo certbot renew --dry-run
          
      
      sangbinlee9@master:/etc/nginx/sites-available$ sudo certbot renew --dry-run
      Saving debug log to /var/log/letsencrypt/letsencrypt.log
      
      - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
      Processing /etc/letsencrypt/renewal/sodi9.store.conf
      - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
      Account registered.
      Simulating renewal of an existing certificate for sodi9.store and www.sodi9.store
      
      - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
      Congratulations, all simulated renewals succeeded:
        /etc/letsencrypt/live/sodi9.store/fullchain.pem (success)
      - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
      sangbinlee9@master:/etc/nginx/sites-available$
      



![image](https://github.com/sangbinlee/nodejs-install/assets/4024414/80c194f6-f799-4ccd-83dd-d140c6168fd9)






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






