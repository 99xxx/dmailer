# Dmailer

### Важно!

Данный скрипт предназначен исключительно для отправки дешевых транзакций в zkSync Era, используя контракт Dmail. Важно отметить, что скрипт не предполагает взаимодействия с сайтом или сервером Dmail.

### Конфиг:

1. `GAS_MULTIPLIER`: Эта переменная представляет собой множитель для расчета стоимости газа при отправке транзакций. Установка значения `GAS_MULTIPLIER` на 1.0 означает, что вы используете стандартную стоимость газа, определенную сетью. Изменение этого значения может увеличить или уменьшить стоимость газа, что влияет на приоритет и скорость обработки ваших транзакций.
2. `USE_PROXY`: Эта переменная определяет, используются ли прокси при отправке транзакций. Если установлено значение `True`, то программа будет использовать прокси из файла `proxies.txt`. Если установлено значение `False`, прокси не будут использоваться.
3. `GAS_THRESHOLD`: Это переменная, которая задает пороговое значение стоимости газа в гигавей (GWEI). Если текущая стоимость газа превышает установленное значение `GAS_THRESHOLD`, то выполнение скрипта приостанавливается и ожидает, пока стоимость газа не уменьшится до уровня, допустимого порогового значения.
4. `GAS_DELAY_RANGE`: Это интервал времени в секундах между проверками стоимости газа. Программа периодически проверяет стоимость газа перед отправкой транзакций, чтобы определить, установлена ли она выше `GAS_THRESHOLD`. Интервал задержки позволяет программе ожидать, чтобы избежать частых запросов и нагрузки на сеть.
5. `PRIVATE_KEYS_PATH`: Это путь к файлу `private_keys.txt`, где хранятся приватные ключи.
6. `PROXIES_PATH`: Это путь к файлу `proxies.txt`, в котором содержатся прокси. Если `USE_PROXY` установлено в `True`, программа будет выбирать прокси из этого файла.
7. `TX_COUNT`: Это список, содержащий два значения - минимальное и максимальное количество транзакций, которые будут отправлены с одного аккаунта. Программа будет выбирать случайное число транзакций из этого диапазона.
8. `TX_DELAY_RANGE`: Это интервал времени в секундах между отправкой каждой транзакции с одного аккаунта. Программа будет выбирать случайное значение из этого диапазона задержки перед отправкой каждой следующей транзакции.
9. `MIN_BALANCE`: Это минимальный баланс, при котором будет происходить отправка транзакций. Если баланс меньше указанного, кошелек пропускается.

### Запуск:

Шаг 1: Установка зависимостей

1. Создайте виртуальное окружение (рекомендуется) или установите зависимости глобально.
2. Откройте командную строку или терминал и перейдите в директорию с вашим проектом.
3. Установите зависимости, перечисленные в requirements.txt, выполнив следующую команду: `pip install -r requirements.txt`

Шаг 2: Подготовка данных

1. В файле `private_keys.txt` запишите приватные ключи для каждого кошелька. Каждый приватный ключ должен быть на отдельной строке.
2. Если вы планируете использовать прокси, в файле `proxies.txt` запишите прокси в формате username:password@ip:port. Каждый адрес прокси должен быть на отдельной строке.

Шаг 3: Запуск программы

1. Откройте командную строку или терминал.
2. Перейдите в директорию, где находится файл `main.py`.
3. Запустите программу, выполнив следующую команду: `python main.py`
4. После запуска `main.py`, программа отобразит приветственное сообщение и будет ожидать ввода от пользователя.
5. Чтобы запустить выполнение программы и начать отправку транзакций, просто нажмите клавишу "Enter" в командной строке или терминале.
6. После нажатия клавиши "Enter", программа начнет выполнять отправку транзакций в соответствии с заданными параметрами и прокси (если они указаны в `proxies.txt`).
7. Чтобы остановить выполнение программы в процессе работы, просто нажмите клавишу "Ctrl + C" в командной строке или терминале.

P.S. README написан через GPT
