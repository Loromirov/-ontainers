Проверяем установку Docker
docker run docker/whalesay cowsay Hello, Docker!

![2023-08-25_13-02-34](https://github.com/Loromirov/-ontainers/assets/117039676/8f8ea772-9a26-4523-957b-e63ff07d25d0)

Запустим контейнер из образа Ubuntu и войдем в него:
docker run -it -h GB --name gb-test ubuntu:22.10
Создадим новую директорию в корне:

mkdir /example
Создадим файл "passwords.txt" и добавим в него какие-либо данные

touch /example/passwords.txt
echo "123test" >> /example/passwords.txt
exit
![Снимок экрана 2023-08-25 133024](https://github.com/Loromirov/-ontainers/assets/117039676/b000cd61-dd0d-4f61-abe6-d9c49b1f14a0)


Остановим контейнер и запустим его снова.
docker stop gb-test
docker start gb-test
docker exec -it gb-test bash
cat /example/passwords.txt
exit

![Снимок экрана 2023-08-25 133537](https://github.com/Loromirov/-ontainers/assets/117039676/b77e3186-9652-45be-9479-6162f81149f4)


Наши данные сохранятся, так как мы не пересоздавали контейнер.

Удалим контейнер и создадим его заново, используя те же команды.
docker stop gb-test
docker rm gb-test
docker run -it -h GB --name gb-test ubuntu:22.10
ls -l
exit
docker stop gb-test

docker rm gb-test

![Снимок экрана 2023-08-25 133034](https://github.com/Loromirov/-ontainers/assets/117039676/06a7b4a8-6de5-44e7-bf69-5cdf532050a2)
