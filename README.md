# Backup
Backup

Настроить стенд с двумя виртуальными машинами: backup_server и client.

Настроить удаленный бекап каталога /etc c сервера client при помощи borgbackup. Резервные копии должны соответствовать следующим критериям:

- директория для резервных копий /var/backup. Это должна быть отдельная точка монтирования. В данном случае для демонстрации размер не принципиален, достаточно будет и 2GB;

- репозиторий дле резервных копий должен быть зашифрован ключом или паролем - на ваше усмотрение;

- имя бекапа должно содержать информацию о времени снятия бекапа;

- глубина бекапа должна быть год, хранить можно по последней копии на конец месяца, кроме последних трех.

- Последние три месяца должны содержать копии на каждый день. Т.е. должна быть правильно настроена политика удаления старых бэкапов;

- резервная копия снимается каждые 5 минут. Такой частый запуск в целях демонстрации;

- написан скрипт для снятия резервных копий. Скрипт запускается из соответствующей Cron джобы, либо systemd timer-а - на ваше усмотрение;

- настроено логирование процесса бекапа. Для упрощения можно весь вывод перенаправлять в logger с соответствующим тегом. Если настроите не в syslog, то обязательна ротация логов.

Запустите стенд на 30 минут.

Убедитесь что резервные копии снимаются.

Остановите бекап, удалите (или переместите) директорию /etc и восстановите ее из бекапа.

Для сдачи домашнего задания ожидаем настроенные стенд, логи процесса бэкапа и описание процесса восстановления.

---

Дано:

![image](https://github.com/user-attachments/assets/19e60939-869a-4103-84ab-a0b1a5b79ac6)


Выполняем подготовленный плейбук:

https://github.com/spbsupprt/Backup/blob/main/backup.yaml

![image](https://github.com/user-attachments/assets/1b535ac3-1164-436e-a3e0-06ff954a9ba0)


Делаем проверки:

