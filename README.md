Практическая работа 2

Тема: Управление потоками ввода/вывода, работа с интерпретаторами, алиасами, 
переменными окружения и конвейерами команд

Цель работы: Изучить и освоить на практике механизмы перенаправления стандартных 
потоков ввода/вывода, работу с несколькими командными интерпретаторами (bash, sh, zsh, 
fish), создание временных и постоянных алиасов, управление временными и постоянными 
переменными окружения, а также способы объединения команд в одной строке и передачи 
вывода одной команды на вход другой (конвейеры). 

Выполнил: студент группы СА-1-25 Кораблев Антон

2.1. Подготовка
![src1]="https://github.com/user-attachments/assets/20497f3f-f5cc-448c-b043-5b6d8f3e8071" />

2.2. Перенаправление потоков ввода/вывода

2.2.1. Создайте текстовый файл data.txt со строками:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/14da12b2-c06e-4340-b4c8-e5fbb099dd28" />

2.2.2. Выведите содержимое data.txt на экран с помощью cat. 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e05c4666-2182-4909-8d34-c79c72f21ff1" />

2.2.3. Запишите вывод команды ls -l в файл list.txt
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/2f309658-37fd-4c3a-b818-fd4067435768" />

2.2.4. Выполните команду ls /nonexistent. Перенаправьте только stdout в out.txt, а 
stderr – в err.txt: 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e7d9592e-4f7a-41d3-9456-ee047eddd385" />

2.2.5. Используя grep, отфильтруйте из data.txt строки, содержащие "a", и запишите 
результат в filtered.txt: 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/07b8169e-5c67-4df3-a4df-db06501c0942" />

2.2.6. С помощью >> добавьте в filtered.txt строку "grape 15":
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ceef2c63-d9de-4128-a241-45ebb9e4812e" />

2.3. Работа с разными интерпретаторами 

2.3.1. Запустите оболочку sh (sh). Выполните echo $SHELL. Попробуйте 
перенаправить ошибки, как в задании 1.4 (в sh синтаксис &> может не 
работать – используйте 2>). Выйдите из sh (exit). 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c4dd1c62-0bab-4128-94d6-8605c2fef240" />

2.3.2. Запустите zsh. Выполните echo $SHELL.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/58ff2b69-6fe8-4e3f-9f3c-41a681bac605" />

2.3.2.1. Создайте временный алиас ll='ls -la' и проверьте его. 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/7f7a25de-50b0-4838-b973-b59b17b15bb0" />

2.3.2.2. Создайте переменную окружения export MY_VAR="hello from zsh". 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/61b94341-5c7b-4a42-b689-56635282b975" />

2.3.2.3. Запустите bash из zsh и проверьте видимость переменной (echo $MY_VAR). Выйдите из bash и из zsh. 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/43b0f6c1-c636-4d10-bbd3-c9820ea4835d" />

2.3.3. Запустите fish. 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/988ddbba-d9e2-41ae-af0b-4db8fc65eef0" />

2.3.3.1. Создайте алиас: alias ll 'ls -la'.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/143423c6-a30e-418e-8cc1-4a0fc8fa7aa1" />

2.3.3.2. Создайте переменную окружения: set -x MY_VAR "hello from fish". 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/94c67f06-67b7-47fc-86d9-6e22ae1e3852" />

2.3.4. Проверьте: echo $MY_VAR. Выйдите из fish.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/eeac9f13-fba0-48ec-b786-12ed7d7e105f" />

2.3.5. Сделайте вывод: в чём основные отличия синтаксиса алиасов и переменных 
в bash vs fish? Запишите в отчёт.
Отчет: в fish синтаксис алиасов и переменных принципиально другой, когда в bash/zsh используют POSIX-подобный синтаксис

2.4. Объединение команд и конвейеры 

2.4.1. Выполните последовательно три команды через ;:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f8f89f43-2f24-4bc7-8983-eb63ac2f2437" />

2.4.2 Используя &&, создайте файл test.txt и только в случае успеха запишите в него "OK": 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6ec15f1e-8b71-4e41-a6b7-64d9ff31c1d1" />

2.4.3. Сымитируйте ошибку: rm notexist.txt || echo "File not found". 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/496a094b-ad80-4bcd-b550-dceac5a5bc16" />

2.4.4. Постройте конвейер из трёх команд: 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/dbee49dc-6cbb-4dc4-b052-363c51d0f3a7" />

2.4.5. Вычислите количество процессов вашего пользователя: 
 <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/dec46a60-0527-4c0f-a91e-7d1b55ef0c54" />

2.5. Создание временных алиасов 

2.5.1. В текущей сессии bash создайте алиас lll='ls -l | grep "^d"'. 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/4bdefe9c-4f3d-4ccf-a9f1-f736af233bee" />

2.5.2. Выполните lll в каталоге lab2. 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/dff84c24-66cf-4f73-b9c7-3c23d6777fd4" />

2.5.3. Создайте алиас myip='curl ifconfig.me 2> /dev/null'. 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/76bd2247-3a49-48d7-a532-2e25d5b2bb25" />

2.5.4. Убедитесь, что после закрытия терминала алиасы пропадут.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5ba22874-7688-4c63-b6ca-187ef6dc89d8" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f9c8987a-c756-4777-bb50-1485ea3bbb59" />

2.6. Создание постоянных алиасов 

2.6.1. Отредактируйте файл ~/.bashrc. Добавьте в конец: alias up='sudo apt update && sudo apt upgrade -y' ; alias myip='curl ifconfig.me' 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/12daaa0d-2445-4c1f-916c-21e8809b7d48" />

2.6.2. Примените изменения: source ~/.bashrc. 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d6b96308-1fdb-4f2c-86d9-3c3612d50d14" />

2.6.3. Проверьте работу алиасов: up (можно отменить Ctrl+C), myip. 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a3a48300-e3d9-44c4-ba92-532bf3a58f33" />

2.6.4. (Для zsh пропишите аналогичные алиасы в ~/.zshrc, для fish – в ~/.config/fish/config.fish с синтаксисом alias up "sudo apt update && sudo apt upgrade -y"). 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/66084fd1-364f-4a2d-8485-548e07570098" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a18a6f82-a8d5-4353-abb1-4ac359d2f904" />

2.7. Временные переменные окружения 

2.7.1. В bash создайте локальную переменную TEMP_VAR="temporary". 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6e7e835d-69a2-4c7e-bb65-963780146e1e" />

2.7.2. Выполните echo $TEMP_VAR. 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c72a9f08-862d-48d7-91b7-906b8460dde6" />

2.7.3. Запустите bash (дочерняя оболочка) и попробуйте вывести echo $TEMP_VAR. 
Объясните результат. : в дочернем bash переменная не видна
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/3cf1ffd5-137c-4bce-99c5-3e023891a5a3" />

2.7.4. Выйдите из дочерней оболочки (exit). Создайте экспортируемую 
переменную: export GLOBAL_VAR="exported" 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5697eefd-b0be-4e5e-aa59-9b092fa3ea00" />

2.7.5. Запустите bash и проверьте echo $GLOBAL_VAR. 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f865df68-f417-4cea-a270-7a774f3b5de8" />

2.7.6. Удалите переменную: unset GLOBAL_VAR. 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/0087bae0-f3c6-42cf-931a-eda9d7bcfe6d" />

2.8. Постоянные переменные окружения 

2.8.1. Добавьте в ~/.bashrc строку: export EDITOR="nano" 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e8c75d74-1b3d-4ebc-bd7b-ae7b4e024214" />

2.8.2. Выполните source ~/.bashrc. 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/0309a2fe-a630-45e6-91a4-84f2886f4b20" />

2.8.3. Проверьте: echo $EDITOR. 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c3294e26-d38e-4ef3-8670-5d3238a0aeca" />

2.8.4. Добавьте также export WORKSPACE="$HOME/lab2". 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/bf95f56d-d5f3-4478-a775-3065bc7d5559" />

2.8.5. Проверьте, что после перезапуска терминала эти переменные остаются. 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ca748c7c-d856-4c5e-a3ee-02eebfdd6444" />

2.9. Комплексный скрипт (закрепление) 
Напишите скрипт на bash (файл lab2_script.sh) со следующим функционалом: 

2.9.1. Скрипт принимает один аргумент – имя файла. 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/74f0573b-57b2-4f6a-920b-37168cc8dae8" />

2.9.2. Проверяет, передан ли аргумент; если нет – выводит сообщение об ошибке в stderr и завершается с кодом 1. 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6c203b0d-20df-4072-945f-e5c687c12327" />

2.9.3. Создаёт временную переменную окружения BACKUP_TIME с текущей датой. 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/fdfd32fb-fae2-4f21-96ce-48583fba6bd6" />

2.9.4. Создаёт каталог backup в $HOME/lab2, если его нет. 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d0e6dc6d-77ea-4bd3-83f1-7fe8e8f28ff8" />

2.9.5. Копирует переданный файл в каталог backup с добавлением суффикса .bak. 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/3d0ca9ff-21c7-4f30-8e0b-72be72665c2e" />

2.9.6. Записывает в файл backup/log.txt строку вида: YYYY-MM-DD HH:MM:SS - скопирован файл <имя> в <путь к бэкапу> (использовать echo и 
перенаправление >>). 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/67dae1f5-73cd-4e29-ad0f-9607f1c16302" />

2.9.7. Выводит сообщение об успехе в stdout. 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5a9c27ab-af11-4d77-849e-ce01a6c146f7" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/20889613-3700-4afd-8efb-6d7e418c33b3" />

КОНТРОЛЬНЫЕ ВОПРОСЫ:
4.1. > перезаписывает файл, >> дописывает в конец.
4.2. ; — выполняет обе команды подряд; && — вторую только при успехе первой.
4.3. Объединить stdout и stderr: &> file или > file 2>&1.
4.4. Алиас — сокращение для команды.
Постоянно: bash/zsh — в ~/.bashrc/~/.zshrc (alias ll='ls -l'); fish — в ~/.config/fish/aliases.fish.
4.5. export делает переменную видимой в дочерних процессах.
4.6. Посмотреть переменные окружения: printenv или env.
4.7. Передача вывода на ввод: через канал |.
4.8. Fish vs bash: алиасы в fish часто ведут себя как функции; работа с переменными отличается (например, set вместо прямого присваивания, разные флаги области видимости).
4.9. Перенаправить stdin из файла и stdout в другой: cmd < in.txt > out.txt.
