**Install Nginx on PUBLIC server**

**--------------------------------**

sudo yum install nginx -y

sudo systemctl start nginx

sudo systemctl enable nginx





*Configure reverse proxy*

*-------------------------*

sudo vi /etc/nginx/nginx.conf



location / {

&#x20;   proxy\_pass http://<PRIVATE IP>:<PORT NO>;



&#x20;   proxy\_set\_header Host $host;

&#x20;   proxy\_set\_header X-Real-IP $remote\_addr;

}





Restart Nginx

\---------------

sudo nginx -t

sudo systemctl restart nginx







Test connection

\----------------

Eg: 



**curl** *http://10.0.141.111:9090*



