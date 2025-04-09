# Травицкий Сергей
# Домашнее задание к занятию  «Защита хоста»

### Инструкция по выполнению домашнего задания

1. Сделайте fork [репозитория c шаблоном решения](https://github.com/netology-code/sys-pattern-homework) к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/gitlab-hw или https://github.com/имя-вашего-репозитория/8-03-hw).
2. Выполните клонирование этого репозитория к себе на ПК с помощью команды `git clone`.
3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
   - впишите вверху название занятия и ваши фамилию и имя;
   - в каждом задании добавьте решение в требуемом виде: текст/код/скриншоты/ссылка;
   - для корректного добавления скриншотов воспользуйтесь инструкцией [«Как вставить скриншот в шаблон с решением»](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md);
   - при оформлении используйте возможности языка разметки md. Коротко об этом можно посмотреть в [инструкции по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md).
4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`).
5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
6. Любые вопросы задавайте в чате учебной группы и/или в разделе «Вопросы по заданию» в личном кабинете.

Желаем успехов в выполнении домашнего задания.

------

### Задание 1

1. Установите **eCryptfs**.
2. Добавьте пользователя cryptouser.
3. Зашифруйте домашний каталог пользователя с помощью eCryptfs.


*В качестве ответа  пришлите снимки экрана домашнего каталога пользователя с исходными и зашифрованными данными.*  

<details>
<summary>ОТВЕТ</summary>  

*Устанавливаем eCryptfs*

` sudo apt install ecryptfs-utils`

![img](https://github.com/travickiy67/Host-protection/blob/main/img/1.1.png)  

*Добавляем пользователя и шифруем каталог и заходим от имени cryptouser*

`sudo adduser --encrypt-home cryptouser`

![img](https://github.com/travickiy67/Host-protection/blob/main/img/1.2.png)   

*Создаем несколько каталогов и завершаем сесию, и пытаемся просмотреть каталог из под sudo*

![img](https://github.com/travickiy67/Host-protection/blob/main/img/1.3.png)   

*Попытка просмотра зашифрованого каталога из под root, не увенчалась успехом*

![img](https://github.com/travickiy67/Host-protection/blob/main/img/1.4.png)  

</details>  

### Задание 2

1. Установите поддержку **LUKS**.
2. Создайте небольшой раздел, например, 100 Мб.
3. Зашифруйте созданный раздел с помощью LUKS.

*В качестве ответа пришлите снимки экрана с поэтапным выполнением задания.*

<details>
<summary>ОТВЕТ</summary>  

*Создаем раздел 200M утилитой fdisk*

![img](https://github.com/travickiy67/Host-protection/blob/main/img/2.1.png)  

*Устанввливаем поддержку LUKS*

`sudo apt-get install cryptsetup`

![img](https://github.com/travickiy67/Host-protection/blob/main/img/2.2.png)  

*Шифруем раздел*

![img](https://github.com/travickiy67/Host-protection/blob/main/img/2.3.png)  

![img](https://github.com/travickiy67/Host-protection/blob/main/img/2.4.png)  

*Форматируем раздел*

`sudo dd if=/dev/zero of=/dev/mapper/box`  
`sudo mkfs.ext4 /dev/mapper/box`  

![img](https://github.com/travickiy67/Host-protection/blob/main/img/2.5.png)  

`Монтируем и проверяем`

![img](https://github.com/travickiy67/Host-protection/blob/main/img/2.6.png)  

</details>  

## Дополнительные задания (со звёздочкой*)

Эти задания дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже шире разобраться в материале

### Задание 3 *

1. Установите **apparmor**.
2. Повторите эксперимент, указанный в лекции.
3. Отключите (удалите) apparmor.


*В качестве ответа пришлите снимки экрана с поэтапным выполнением задания.*

<details>
<summary>ОТВЕТ</summary>  

*Устанавливем apparmor*

![img](https://github.com/travickiy67/Host-protection/blob/main/img/3.1.png)  

*Статус*

![img](https://github.com/travickiy67/Host-protection/blob/main/img/3.2.png)  

*Повторяем экспиремент*

![img](https://github.com/travickiy67/Host-protection/blob/main/img/3.3.png)  

</details>
