# Cron jobs

Je leert hoe je cronjobs instelt, interpreteert en gebruikt voor automatisatie op een Linux-systeem.

Gebruik geen Google. Raadpleeg man crontab, man 5 crontab, man mosquitto\_pub, enz.

Markeer voltooide opdrachten met een ✅.

---

## ✅ I am Alive

```cron
*/15 * * * * mosquitto_pub -h emqx.veict.lan -t linux/alive/jouwnaam -m "Still alive" -u student -P Student123
```

## ✅ My IP

```cron
* * * * * hostname -I | awk '{print $1}' | xargs -I {} mosquitto_pub -h emqx.veict.lan -t linux/ip/jouwnaam -m {} -u student -P Student123
```

## ✅ Daily Disk Usage Report

```cron
0 7 * * * df -h >> /home/jouwnaam/disk_usage.log
```

## ✅ Temperature Monitor

```cron
*/10 * * * * temp=$(cat /sys/class/thermal/thermal_zone0/temp); celsius=$((temp / 1000)); mosquitto_pub -h emqx.veict.lan -t linux/temp/jouwnaam -m "$celsius°C" -u student -P Student123
```

## ✅ Reboot Notifier

```cron
@reboot mosquitto_pub -h emqx.veict.lan -t linux/reboot/jouwnaam -m "Rebooted at $(date)" -u student -P Student123
```

## ✅ Clean Up Logs

```cron
30 3 * * 0 find /home/jouwnaam/oldlogs/ -type f -mtime +7 -delete
```

## ✅ Weekly Uptime

```cron
0 8 * * 1 uptime | xargs -I {} mosquitto_pub -h emqx.veict.lan -t linux/uptime/jouwnaam -m "{}" -u student -P Student123
```

---

## Theorievragen

✅ 1. Wat betekent deze cronregel?

```
*/5 * * * 1-5 /home/student/backup.sh
```

**B. Elke maandag tot vrijdag, elke 5 minuten**

✅ 2. Wat doet @reboot in crontab?
**A. Voert een opdracht uit bij elke herstart van de computer**

✅ 3. Wat is het verschil tussen deze twee regels?

```
0 12 * * * echo "Hello"
@daily echo "Hello"
```

**C. De eerste draait om 12:00, de tweede om 00:00**

✅ 4. Vul aan: een cronregel die elke 30 minuten draait

```
*/30 * * * * somecommand
```

✅ 5. Cronjobs worden opgeslagen in bestanden. Welk bestand bewerk je met crontab -e?
**C. De persoonlijke crontab in /var/spool/cron/crontabs/**
