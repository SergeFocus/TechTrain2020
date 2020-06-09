# TechTrain Issue#4

## description

Используйте docker image из предыдущих задач. Добавьте четвертый Rest-сервис — напишите его на языке программирования, который вы еще не использовали в задачах 1, 2 и 3.

Этот Rest-сервис должен:
* вызывать сервис из третий задачи;
* проверять, что получает строку "Мы сломали твой";
* прибавлять к этой строке пробел и строку "код,"
* выдавать при вызове GET результат, т.е. строку "Мы сломали твой код,"

## build

docker build -t issue4 .

## run

docker run --rm -p 5004:80 issue4

**Важно**: для указания адреса предыдущего сервиса используется переменная среды `SERVICE_ENDPOINT`. Например:

docker run --rm -p 5004:80 -e SERVICE_ENDPOINT=http://localhost:5003 issue4

## check

wget -qO- http://localhost:5004