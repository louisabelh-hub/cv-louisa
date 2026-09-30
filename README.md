# CV de Louisa

CV interactif en HTML, servi par Apache et accessible via le nom de domaine local louisa.local.

## Configuration réalisée

1. Installation et démarrage d'Apache et MariaDB :
   sudo systemctl enable --now apache2 mariadb

2. Creation du site dans /var/www/html/louisa contenant index.html

3. Configuration du VirtualHost dans /etc/apache2/sites-available/louisa.conf :
   <VirtualHost *:80>
       ServerName louisa.local
       DocumentRoot /var/www/html/louisa
       <Directory /var/www/html/louisa>
           Require all granted
       </Directory>
   </VirtualHost>

4. Activation du site :
   sudo a2ensite louisa.conf
   sudo systemctl reload apache2

5. Ajout de la resolution du nom de domaine local dans /etc/hosts :
   127.0.0.1   louisa.local

6. Test d'acces via http://louisa.local
