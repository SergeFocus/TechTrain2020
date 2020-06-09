# TechTrain Task#5

## description

Используйте docker image из предыдущих задач. Добавьте пятый Rest-сервис — напишите его на языке программирования, который вы еще не использовали в задачах 1, 2, 3 и 4.

Этот Rest-сервис должен:

* вызывать сервис из четвертой задачи;
* проверять, что получает строку "Мы сломали твой код,";
* прибавлять к этой строке пробел и строку "уронили"
* выдавать при вызове GET результат, т.е. строку "Мы сломали твой код, уронили"

## build

docker build -t issue5 .

## run

docker run --rm -p 5005:3000 issue5

**Важно**: для указания адреса предыдущего сервиса используется переменная среды `SERVICE_ENDPOINT`. Например:

docker run --rm -p 5005:3000 -e SERVICE_ENDPOINT=http://localhost:5004 issue5

## check

wget -qO- http://localhost:5005