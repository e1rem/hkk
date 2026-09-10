Цель работы: Освоить базовые приёмы работы в командной оболочке Linux, изучить 
структуру файловой системы, научиться управлять файлами и каталогами, получить навыки 
работы с текстовыми редакторами nano и vi/vim (с акцентом на vi/vim как обязательный 
инструмент системного администратора), а также приобрести умение использовать 
справочную систему.

Тема: Управление потоками ввода/вывода, работа с интерпретаторами, алиасами, 
переменными окружения и конвейерами команд

Цель работы: Изучить и освоить на практике механизмы перенаправления стандартных 
потоков ввода/вывода, работу с несколькими командными интерпретаторами (bash, sh, zsh, 
fish), создание временных и постоянных алиасов, управление временными и постоянными 
переменными окружения, а также способы объединения команд в одной строке и передачи 
вывода одной команды на вход другой (конвейеры). 

Выполнил: студент группы СА-1-25 Кораблев Антон

2.1. Подготовка
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/20497f3f-f5cc-448c-b043-5b6d8f3e8071" />

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

2.6.2. Примените изменения: source ~/.bashrc. 

2.6.3. Проверьте работу алиасов: up (можно отменить Ctrl+C), myip. 

2.6.4. (Для zsh пропишите аналогичные алиасы в ~/.zshrc, для fish – в ~/.config/fish/config.fish с синтаксисом alias up "sudo apt update && sudo apt upgrade -y"). 
