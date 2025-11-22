# Viikkotehtävä 4

## Streamlit-sovellus
http://86.50.23.156/data-analysis

Nginx on konfiguroitu reverse proxyna ohjaamaan `/data-analysis` suoraan Streamlit-palvelulle (portti 8501).

## Cron-tehtävä (datan päivitys 15 min välein)

Data päivittyy automaattisesti 15 minuutin välein seuraavalla cron-ajolla:
*/15 * * * * /home/ubuntu/lemp-app/venv/bin/python /home/ubuntu/lemp-app/update_data.py >> /home/ubuntu/lemp-app/cron.log 2>&1

- `*/15` = suorita 15 minuutin välein
- Suorittaa Python-skriptin `update_data.py`
- Tallentaa tuloksen lokiin `cron.log`
- Skripti hakee API-datan ja tallentaa sen tietokantaa

## MySQL ja LEMP-tarkistukset

MySQL toimii ja tietokannat listattu komennolla:
SHOW DATABASES;

PHP-FPM testattu luomalla tiedosto:
/var/www/html/info.php

Nginx toimii ja ohjaa Streamlitin reverse-proxyn kautta.

## Lokitiedosto

Cronin loki sijaitsee täällä:
/home/ubuntu/lemp-app/cron.log




