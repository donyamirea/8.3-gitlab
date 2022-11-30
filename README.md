# Домашнее задание к занятию "`8.3 Gitlab`" - `Балашов Денис`


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

### Задание 1


1. [установка gitlab-ce](https://ru.linuxcapable.com/how-to-install-configure-gitlab-on-debian-11-bullseye/) ставил не через вагрант, а ручками + в лекции и задании указана версия "*-ee" , а нам нужна бесплатная "*-ce"
2. [пустой проект](https://user-images.githubusercontent.com/117297288/204612258-d36350e8-9ece-4526-a12e-cf2407f4741d.png)
3. [установленный раннер](https://user-images.githubusercontent.com/117297288/204611813-fbdce6e8-dba3-40bd-aac6-79a63a8f8d2d.png)

---

### Задание 2

`Приведите ответ в свободной форме........`

1. ![image](https://user-images.githubusercontent.com/117297288/204618419-807fe958-cad3-449d-abfe-f5fe459bb2f5.png)
2. ![image](https://user-images.githubusercontent.com/117297288/204911701-12a6f1e0-0805-4e1a-b7bf-619c1d17f514.png)
```
Running with gitlab-runner 15.6.1 (133d7e76)
  on donya 6frjRyz5
Preparing the "docker" executor
00:03
Using Docker executor with image docker:latest ...
Pulling docker image docker:latest ...
Using docker image sha256:f71b1ffeed15dba6582544322d625b1e91ff4c45981cb50e88e6409d86668cf6 for docker:latest with digest docker@sha256:83b5f0a88fc82a724c1ffdc4220e49aed855e7db3f30ab0ac3d27c515346caca ...
Preparing environment
00:01
Running on runner-6frjryz5-project-3-concurrent-0 via donya...
Getting source from Git repository
00:00
Fetching changes with git depth set to 20...
Reinitialized existing Git repository in /builds/gitlab-instance-93e03083/my-wierdest-prj/.git/
Checking out 4b8aa7ce as main...
Skipping Git submodules setup
Executing "step_script" stage of the job script
00:48
Using docker image sha256:f71b1ffeed15dba6582544322d625b1e91ff4c45981cb50e88e6409d86668cf6 for docker:latest with digest docker@sha256:83b5f0a88fc82a724c1ffdc4220e49aed855e7db3f30ab0ac3d27c515346caca ...
$ docker build .
Step 1/8 : FROM golang:1.13 AS builder
1.13: Pulling from library/golang
d6ff36c9ec48: Pulling fs layer
c958d65b3090: Pulling fs layer
edaf0a6b092f: Pulling fs layer
80931cf68816: Pulling fs layer
813643441356: Pulling fs layer
799f41bb59c9: Pulling fs layer
16b5038bccc8: Pulling fs layer
80931cf68816: Waiting
813643441356: Waiting
799f41bb59c9: Waiting
16b5038bccc8: Waiting
c958d65b3090: Verifying Checksum
c958d65b3090: Download complete
edaf0a6b092f: Verifying Checksum
edaf0a6b092f: Download complete
813643441356: Download complete
d6ff36c9ec48: Verifying Checksum
d6ff36c9ec48: Download complete
16b5038bccc8: Verifying Checksum
16b5038bccc8: Download complete
80931cf68816: Verifying Checksum
80931cf68816: Download complete
d6ff36c9ec48: Pull complete
c958d65b3090: Pull complete
edaf0a6b092f: Pull complete
80931cf68816: Pull complete
813643441356: Pull complete
799f41bb59c9: Verifying Checksum
799f41bb59c9: Download complete
799f41bb59c9: Pull complete
16b5038bccc8: Pull complete
Digest: sha256:8ebb6d5a48deef738381b56b1d4cd33d99a5d608e0d03c5fe8dfa3f68d41a1f8
Status: Downloaded newer image for golang:1.13
 ---> d6f3656320fe
Step 2/8 : WORKDIR $GOPATH/src/netology-test/
 ---> Running in 0645af5d79df
Removing intermediate container 0645af5d79df
 ---> ccae2bcf2ce8
Step 3/8 : COPY . ./
 ---> 876ffc5fdf92
Step 4/8 : RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix nocgo -o /app .
 ---> Running in ab178a266e77
Removing intermediate container ab178a266e77
 ---> dcad5e686634
Step 5/8 : FROM alpine:latest
latest: Pulling from library/alpine
c158987b0551: Already exists
Digest: sha256:8914eb54f968791faf6a8638949e480fef81e697984fba772b3976835194c6d4
Status: Downloaded newer image for alpine:latest
 ---> 49176f190c7e
Step 6/8 : RUN apk -U add ca-certificates
 ---> Running in 9f5a22f89da0
fetch https://dl-cdn.alpinelinux.org/alpine/v3.17/main/x86_64/APKINDEX.tar.gz
fetch https://dl-cdn.alpinelinux.org/alpine/v3.17/community/x86_64/APKINDEX.tar.gz
(1/1) Installing ca-certificates (20220614-r2)
Executing busybox-1.35.0-r29.trigger
Executing ca-certificates-20220614-r2.trigger
OK: 8 MiB in 16 packages
Removing intermediate container 9f5a22f89da0
 ---> e7311f9b093e
Step 7/8 : COPY --from=builder /app /app
 ---> 297e548f134a
Step 8/8 : CMD ["/app"]
 ---> Running in 54c04228bc86
Removing intermediate container 54c04228bc86
 ---> 0833d1a7a926
Successfully built 0833d1a7a926
Job succeeded
```



---

