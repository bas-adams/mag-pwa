# mag-pwa -> nazwa hosta nie może zawierać znaku '_' 
magento pwa instalation
a) pobranie źródła https://devdocs.magento.com/guides/v2.3/install-gde/composer.html wersja magento opensource
b) stworzenie bazy danych 
c) konfiguracja nginx ( /etc/sites-available i symlink do sites-enabled ) po http  dla https inny port
server {
        listen 80;
        server_name pwamag.local;
        access_log file_name/logs/pwa_mag.local-access.log;
        error_log file_name/logs/pwa_mag.local-error.log;
        set $MAGE_ROOT file_name/projects/pwa_mag; //-> nazwa pliku gdzie znajdują się pliki magento
        include snippets/magento2.conf;
}

d) dodane doment do /etc/hosts (sudo nano /etc/hosts)
e) restart nginx: sevice nginx restart
f) Web Setup Wizard: http://<Magento-host-or-IP>/<path-to-magento-root>/setup   -> http://pwamag.local/setup
# mag-validation mage/validation
  
# magento validation

define(['mage/validation'], function(validation) {})

# adding css file to new moduls
web -> css -> source -> _module.less -> tu @import 'module/_nazwa.less';
web -> css -> source -> module -> _nazwa.less
