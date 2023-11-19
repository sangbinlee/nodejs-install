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
