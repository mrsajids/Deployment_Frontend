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

## PROCESS 2: SFTP File Transfer
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

