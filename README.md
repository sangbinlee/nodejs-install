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






# How To Install Node.js on Ubuntu 22.04


    
    sudo apt update

    
    sangbinlee9@master:~/front-end$ node --version
    v12.22.9
    sangbinlee9@master:~/front-end$ nodejs -v
    v12.22.9




    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh


    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash

    source ~/.bashrc

    nvm list-remote


       v18.17.0   (LTS: Hydrogen)
       v18.17.1   (LTS: Hydrogen)
       v18.18.0   (LTS: Hydrogen)
       v18.18.1   (LTS: Hydrogen)
       v18.18.2   (Latest LTS: Hydrogen)
        v19.0.0
        v19.0.1
        v19.1.0
        v19.2.0
        v19.3.0
        v19.4.0
        v19.5.0

 

    nvm install v18.18.2
 

    
    sangbinlee9@master:~$ nvm list
    ->     v18.18.2
             system
    default -> v18.18.2
    iojs -> N/A (default)
    unstable -> N/A (default)
    node -> stable (-> v18.18.2) (default)
    stable -> 18.18 (-> v18.18.2) (default)
    lts/* -> lts/iron (-> N/A)
    lts/argon -> v4.9.1 (-> N/A)
    lts/boron -> v6.17.1 (-> N/A)
    lts/carbon -> v8.17.0 (-> N/A)
    lts/dubnium -> v10.24.1 (-> N/A)
    lts/erbium -> v12.22.12 (-> N/A)
    lts/fermium -> v14.21.3 (-> N/A)
    lts/gallium -> v16.20.2 (-> N/A)
    lts/hydrogen -> v18.18.2
    lts/iron -> v20.9.0 (-> N/A)
    sangbinlee9@master:~$


# npx create-react-app react-1
    
    
    sangbinlee9@master:~/front-end$ npx create-react-app react-1
    
    Creating a new React app in /home/sangbinlee9/front-end/react-1.
    
    Installing packages. This might take a couple of minutes.
    Installing react, react-dom, and react-scripts with cra-template...
    
    
    added 1463 packages in 52s
    
    242 packages are looking for funding
      run `npm fund` for details
    
    Initialized a git repository.
    
    Installing template dependencies using npm...
    
    added 69 packages, and changed 1 package in 5s
    
    246 packages are looking for funding
      run `npm fund` for details
    Removing template package using npm...
    
    
    removed 1 package, and audited 1532 packages in 3s
    
    246 packages are looking for funding
      run `npm fund` for details
    
    8 vulnerabilities (2 moderate, 6 high)
    
    To address all issues (including breaking changes), run:
      npm audit fix --force
    
    Run `npm audit` for details.
    Git commit not created Error: Command failed: git commit -m "Initialize project using Create React App"
        at checkExecSyncError (node:child_process:890:11)
        at execSync (node:child_process:962:15)
        at tryGitCommit (/home/sangbinlee9/front-end/react-1/node_modules/react-scripts/scripts/init.js:62:5)
        at module.exports (/home/sangbinlee9/front-end/react-1/node_modules/react-scripts/scripts/init.js:350:25)
        at [eval]:3:14
        at Script.runInThisContext (node:vm:123:12)
        at Object.runInThisContext (node:vm:299:38)
        at node:internal/process/execution:82:21
        at [eval]-wrapper:6:24 {
      status: 128,
      signal: null,
      output: [ null, null, null ],
      pid: 13705,
      stdout: null,
      stderr: null
    }
    Removing .git directory...
    
    Success! Created react-1 at /home/sangbinlee9/front-end/react-1
    Inside that directory, you can run several commands:
    
      npm start
        Starts the development server.
    
      npm run build
        Bundles the app into static files for production.
    
      npm test
        Starts the test runner.
    
      npm run eject
        Removes this tool and copies build dependencies, configuration files
        and scripts into the app directory. If you do this, you can’t go back!
    
    We suggest that you begin by typing:
    
      cd react-1
      npm start
    
    Happy hacking!
    sangbinlee9@master:~/front-end$





#  cd react-1
#  npm start
    
    Compiled successfully!
    
    You can now view react-1 in the browser.
    
      Local:            http://localhost:3000
      On Your Network:  http://192.168.0.65:3000
    
    Note that the development build is not optimized.
    To create a production build, use npm run build.
    
    webpack compiled successfully
    
    



![image](https://github.com/sangbinlee/nodejs-install/assets/4024414/8bdde3f6-d1b0-4c43-a6ac-4d641351644d)





![image](https://github.com/sangbinlee/nodejs-install/assets/4024414/8901fda2-33a0-4641-87bb-6b255e7c3d42)
















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






