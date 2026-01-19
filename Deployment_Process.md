# Deployment Web Hosting
## Hostinger Apache2 Frontend dist Hosting
## PROCESS 1: SFTP File Transfer

1. Upload dist/ Files (SFTP)
   
   ```
   sftp root@www.locatetutor.com
   ```
   Enter password
   
   
3. Move to directory 
   ```
   cd /var/www
   ```
   

4. (optional) copy dist file location and paste
   ```
   put -r K:/Sajeed/LOCATETUTOR/LocateTutor/dist
   ```
   Files Added.

## PROCESS 2: Restart Apache
1. Root login
   ```
   ssh root@www.locatetutor.com
   ```
   Enter password

2. Go to www directory
   ```
   cd /var/wwww
   ```

3. Restart apache2
   ```
   sudo service apache2 restart
   ```

   Finished...


## Changing .env or proxy
1. Root login
   ```
   ssh root@www.locatetutor.com
   ```
   Enter password

2. Go to available site directory you will find yourdomain.conf file
   ```
   cd /etc/apache2/sites-available/
   ```
   
3. Edit yourdomain.conf file
   ```
   nano yourdomain.conf
   ```

4. Add Correct config
   ```
   <VirtualHost *:80>
    ServerName yourdomain.com
    ServerAlias www.yourdomain.com

    DocumentRoot /var/www/yourdomain

    <Directory /var/www/yourdomain>
        AllowOverride All
        Require all granted
    </Directory>

    ErrorLog ${APACHE_LOG_DIR}/yourdomain_error.log
    CustomLog ${APACHE_LOG_DIR}/yourdomain_access.log combined
   </VirtualHost>

5. Restart apache2
   ```
   sudo service apache2 restart
   ```

   Finished...

