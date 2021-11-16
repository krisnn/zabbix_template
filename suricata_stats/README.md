suricata_stats
==============
Parsing Statistik Suricata untuk Zabbix Monitoring

Sumber detail penggunaan : http://christophe.vandeplas.com/2013/11/suricata-monitoring-with-zabbix-or-other.html

berjalan pada: zabbix_agentd 5.0.17 dan zabbix_sender 5.0.17

Update & Edited : krisnn norman.kristiono@gmail.com
Copyleft GPLv3 - Christophe Vandeplas - christophe@vandeplas.com

Instalasi
-----
```
aktifkan stats.log pada /etc/suricata/suricata.yaml dan setting:
  - stats:
      enabled: yes
      filename: stats.log
      append: no
      interval: 60

kemudian setting melalui crontab:
*/1 * * * * sudo /usr/bin/python /source/file/suricata_stats.py -q -z


format : suricata.py [-h] [-z] [-q] [-v]

opsional:
  -h, --help     show this help message and exit
  -z, --zabbix   Send output to zabbix
  -q, --quiet    Be quiet (do not print to stdout)
  -v, --verbose  be more verbose
```