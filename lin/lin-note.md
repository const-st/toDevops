create 10 numeric file
touch file{1..10}.txt 
in cicle
for i in {1..10}; do touch "file$i.txt"; done
del
rm file{1..5}.txt
for i in {6..10}; do rm "file$i.txt"; done
copy and rename
cp for i in {1..5}; do cp "file$i.txt" "./backup/file${i}_backup.txt"; done

```
# Простое создание (система сама назначит GID)
sudo groupadd developers
# Создать с конкретным GID (например, 1234)
sudo groupadd -g 1234 admins
# Создать системную группу (обычно GID < 1000)
sudo groupadd -r system_group
# Из файла групп
grep developers /etc/group
# Вывод: developers:x:1002:

# Добавить пользователя john в группу developers (добавляет, не удаляя из других)
sudo usermod -aG developers john
# -a (append) обязательно, иначе удалятся все другие группы

# Сделать developers первичной группой для john
sudo usermod -g developers john
# Удалить john из группы developers
sudo gpasswd -d john developers
#rename group
sudo groupmod -n new_name old_name
#del goup
sudo groupdel project_x
```

|Действие|Команда|
|---|---|
|Создать группу|`sudo groupadd группа`|
|Добавить пользователя в группу|`sudo usermod -aG группа пользователь`|
|Удалить из группы|`sudo gpasswd -d пользователь группа`|
|Сменить первичную группу|`sudo usermod -g группа пользователь`|
|Удалить группу|`sudo groupdel группа`|
|Показать группы пользователя|`groups пользователь`|
|Поменять группу файла|`sudo chgrp группа файл`|
