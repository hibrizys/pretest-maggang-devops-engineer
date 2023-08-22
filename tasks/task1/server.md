# Server Nginx

Im using VueJs to making Web profile, here is the steps Deploy to WebServer nginx:

## Step 1: Build your Vue App
Let say u have done pull repository or make project on Ubuntu. Now you need to build your app. Make sure you install all the dependiencies before you build it.

```
npm install
npm run build
```
remember always check your path of `dist` to point your web root

## Step 2: Install and Configure Nginx
Once your app build is ready you ned to install `Nginx`.

```
sudo apt install nginx
```

Double check to make sure the `Nginx` service is running with command `service nginx status`, then open your browser and enter url `http://{server_ip}` or `http://localhost`. You should see some welcome message from `Nginx`.

## Step 3: Configure Nginx
you can configure file Nginx vue project name by yourself.

```
sudo touch /etc/nginx/sites-available/{{Your project file name}}
sudo ln -s /etc/nginx/sites-available/{{Your project file name}} /etc/nginx/sites-enabled/{{Your project file name}}
sudo vim /etc/nginx/sites-available/{{Your project file name}}
```

here is my configuration:
```
server {
    listen      5173;
    server_name hibrizys.gmail.com;
    
    charset utf-8;
    root    /home/hibriys/Documents/Hibrizy-Web/dist;
    index   index.html;
   
    location / {
        root /home/hibriys/Documents/Hibrizy-Web/dist;
        try_files $uri  /index.html;
    }    
    error_log  /var/log/nginx/vue-app-error.log;
    access_log /var/log/nginx/vue-app-access.log;
}
```

check configuration, then restart `Nginx`:

```
sudo nginx -t
sudo service nginx restart
```

Now, you should access your api through port 5173 with your domain name: 
```
http://hibrizys.gmail.com.
```