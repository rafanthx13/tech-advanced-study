
# COnfigurar Cron

## Linkx

https://linuxconfig.org/linux-crontab-reference-guide
https://ostechnix.com/a-beginners-guide-to-cron-jobs/

facilitadtores com UI
https://crontab.guru/
https://crontab-generator.org/

Cron UI no linux via NPM PACKAGE
https://ostechnix.com/how-to-easily-and-safely-manage-cron-jobs-in-linux/

## O qu eé o cron


cron permite que agende tarefas para ser executada no linux

https://linuxconfig.org/linux-crontab-reference-guide

# editar
sudo crontab -e 

If it is the first time, you will be asked to choose an editor to edit the cron jobs.

no crontab for sk - using an empty one

Select an editor. To change later, run 'select-editor'.
 1. /bin/nano <---- easiest
 2. /usr/bin/vim.basic
 3. /usr/bin/vim.tiny
 4. /bin/ed

Choose 1-4 [1]:

# editar cornotab para outro usuário
crontab -u ostechnix -e

# lsitar tarefas agendads no cron
$ crontab -l 

# remover taredas agendadsa noc rom
$ crontab -r 

## Outros arquivos de cron 

System wide crontab scheduler
Many of the services use crontab automatically. They store their crontab scheduler configuration directly into /etc/cron.d directory. Any files located in this directory are automatically picked up and executed by the crontab scheduler.

Linux system administrators can also take an advantage of crontab preconfigured schedules directories /etc/cron.daily, /etc/cron.hourly, /etc/cron.monthly and /etc/cron.weekly.

The crontab files located within these directories are periodically traversed and execute by crontab scheduler. So for example crontab files found in /etc/cron.daily directory are executed every day. Furthermore, if root wishes to run eg. backup.sh script once a week he will place it into /etc/cron.weekly directory.

## Eschema dos caomdnos do crontab

* * * * * <command-to-execute>

Minute(0-59) Hour(0-24) Day_of_month(1-31) Month(1-12) Day_of_week(0-6) Command_to_execute

## Exemplos

Crontab Example 1
Crontab example to run the updatedb command 35 minutes past every hour.

35 * * * * updatedb 
Crontab Example 2
Crontab example to execute /usr/local/bin/diskusage.sh at 2:00 PM on 10th of March, June, September and December.

00 14 10 3,6,9,12 * /usr/local/bin/diskusage.sh 
Crontab Example 3
This crontab example runs /usr/local/bin/diskusage.sh at 1:25 AM, 1:50 AM every Tuesday and on 15th of every month.

25,50 1 15 * 2 /usr/local/bin/diskusage.sh 
Crontab Example 4
This crontab example runs /usr/local/bin/diskusage.sh at 9.00 PM every Monday, Wednesday, Friday. Please note that using names week days and month names is an extension for some crontab versions.

00 21 * * Mon,Wed,Fri /usr/local/bin/diskusage.sh
Crontab Example 5
The following crontab example executes /usr/local/bin/diskusage.sh every 5 minutes during the 5 working days (Monday – Friday), every week and month.

*/5 * * * 1-5 /usr/local/bin/diskusage.sh 
Crontab Example 6
This crontab example runs/usr/local/bin/diskusage.sh script at every minute past every 4th hour on Sunday.

* */4 * * sun /usr/local/bin/diskusage.sh 
