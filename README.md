# jenkins-simlink-buildNum

- Create a public_html dir in your ec2-user home directory
- Create a file with any name but extension should be .conf in /etc/nginx/conf.directory
- Copy the below content in that
```
server {
        listen 80;

        root /home/ec2-user/public_html;
        index index.html;
}
```
