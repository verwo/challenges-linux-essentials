Je leert hoe je cronjobs instelt, interpreteert en gebruikt voor automatisatie op een Linux-systeem.

Gebruik geen Google. Raadpleeg man crontab, man 5 crontab, man mosquitto_pub, enz.

Markeer voltooide opdrachten met een ✅.

🔧 Deel 1: Praktische cron-jobs (± 40 minuten)
❌ I am Alive
Maak een cronjob die elke 15 minuten een bericht stuurt naar de MQTT-broker mqtt.devbit.be op het topic linux/alive/<jouwnaam> met een bericht zoals Still alive.

```
mosquitto_pub -h mqtt.devbit.be -t linux/alive/<jouwnaam> -m "Still alive"
```
❌ My IP
Maak een cronjob die elke minuut het IP-adres van je Raspberry Pi publiceert op het topic linux/ip/<jouwnaam>.

```
hostname -I | awk '{print $1}'
```
❌ Daily Disk Usage Report
Log dagelijks om 07:00 de uitvoer van df -h naar ~/disk_usage.log. De output moet worden toegevoegd aan het logbestand (niet overschreven!).

❌ Temperature Monitor
Controleer elke 10 minuten de CPU-temperatuur met dit commando:

```
cat /sys/class/thermal/thermal_zone0/temp
```
De waarde moet gedeeld worden door 1000 om Celsius te krijgen. Stuur het resultaat naar linux/temp/<jouwnaam> via MQTT.

❌ Reboot Notifier
Maak een cronjob die bij elke reboot een bericht stuurt naar linux/reboot/<jouwnaam> met de tekst Rebooted at <timestamp>. Gebruik date voor de timestamp.

❌ Clean Up Logs
Verwijder elke zondag om 03:30 logbestanden ouder dan 7 dagen uit de map ~/oldlogs/.

```
find ~/oldlogs/ -type f -mtime +7 -delete
```
❌ Weekly Uptime
Stuur elke maandag om 08:00 de output van uptime naar linux/uptime/<jouwnaam> via MQTT.

🧠 Deel 2: Cron-syntax quiz (± 20 minuten)
Vul onderstaande opdrachten in op papier of via een online formulier.

✅ 1. Wat betekent deze cronregel?
```
*/5 * * * 1-5 /home/student/backup.sh
```
A. Elke 5 minuten op maandag en vrijdag
B. Elke maandag tot vrijdag, elke 5 minuten
C. Elke 5 minuten op de eerste vijf dagen van de maand
D. Elke 5 minuten op de 1ste en 5de van de maand

✅ 2. Wat doet @reboot in crontab?
A. Voert een opdracht uit bij elke herstart van de computer
B. Start de cron-dienst opnieuw op
C. Voert een opdracht uit om middernacht
D. Verwijdert oude cronjobs

✅ 3. Wat is het verschil tussen deze twee regels?
```
0 12 * * * echo "Hello"
@daily echo "Hello"
```
A. De eerste draait om middernacht, de tweede om 12 uur
B. Ze doen exact hetzelfde
C. De eerste draait om 12:00, de tweede om 00:00
D. De tweede draait elk uur

✅ 4. Vul aan: een cronregel die elke 30 minuten draait
```
_____/30 * * * * somecommand
```
✅ 5. Cronjobs worden opgeslagen in bestanden. Welk bestand bewerk je met crontab -e?
A. /etc/crontab
B. /etc/cron.daily
C. De persoonlijke crontab in /var/spool/cron/crontabs/
D. /home/<gebruiker>/.cron

