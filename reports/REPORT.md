# Лабораторная работа №17. Отчет.

## Задание на лабораторную работу:

- [x] 1. Ознакомиться со ссылками учебного материала
- [x] 2. Выполнить инструкцию учебного материала
- [x] 3. Составить отчет и отправить ссылку личным сообщением в **Slack**

## Выполнение работы.
	
В соответствии с последовательностью, определенной заданием на лабораторную работу, были выполнены следующие действия:
- [X] Для успешного выполнения задания создан новый пустой репозиторий lab17 с лицензией MIT.
- [X] 1. Проведено ознакомление по приведенным ссылкам со следующими материалами по [Tmux](https://raw.githubusercontent.com/tmux/tmux/master/README), [Libevent](http://libevent.org), [Ncurses](http://invisible-island.net/ncurses/).
- [X] 2. Выполнена следующая последовательность команд:

## Tutorial

```ShellSession
$ export GITHUB_USERNAME=woz91
```

```ShellSession
$ git clone https://github.com/${GITHUB_USERNAME}/lab16 lab17
$ cd lab17
$ git remote remove origin
$ git remote add origin git@github.com:${GITHUB_USERNAME}/lab17
```

```ShellSession
$ cd ~
$ mkdir install
$ mkdir tmp
$ export HOME_PREFIX=`pwd`/install
$ echo $HOME_PREFIX
$ export USERNAME=`whoami`
```

```ShellSession
$ cd tmp
```

```ShellSession
$ wget https://github.com/libevent/libevent/releases/download/release-2.1.8-stable/libevent-2.1.8-stable.tar.gz
$ tar -xvzf libevent-2.1.8-stable.tar.gz
$ cd libevent-2.1.8-stable
$ ./configure --prefix=${HOME_PREFIX}
$ make && make install 
$ cd ..
```

```ShellSession
$ wget http://invisible-island.net/datafiles/release/ncurses.tar.gz
$ tar -xvzf ncurses.tar.gz
$ cd ncurses-6.1
$ ./configure --prefix=${HOME_PREFIX}
$ make && make install 
$ cd ..
```

```ShellSession
$ wget https://bin.equinox.io/c/4VmDzA7iaHb/ngrok-stable-linux-i386.zip
$ unizp ngrok-stable-linux-i386.zip
$ mv ngrok ${HOME_PREFIX}/bin
```

```ShellSession
$ export LD_LIBRARY_PATH=${HOME_PREFIX}/lib
$ export PATH="${HOME_PREFIX}/bin:${PATH}"
$ tmux new -s session_with_group
```

```ShellSession
# Alisa:
$ open https://ngrok.com/signup
$ export NGROK_TOKEN=zmvpbxXEp47zctaoi8ro_4xvu9RB8Rbc5j5xK2kbFi
$ ngrok authtoken ${NGROK_TOKEN}
$ ngrok tcp 22
```

```ShellSession
# Bob:
$ ssh ${USERNAME}@0.tcp.ngrok.io -p22
iu8@iu8
$ tmux a -t session_with_group
$ <C-B>"
```

## Report

```ShellSession
$ cd ~/workspace/labs/
$ export LAB_NUMBER=16
$ git clone https://github.com/tp-labs/lab${LAB_NUMBER} tasks/lab${LAB_NUMBER}
$ mkdir reports/lab${LAB_NUMBER}
$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md
$ cd reports/lab${LAB_NUMBER}
$ edit REPORT.md
$ gistup -m "lab${LAB_NUMBER}"
```

- [X] 3. Составлен отчет о работе в формате MD, ссылка отправлена в **slack**.

	
>## Выводы:

>В ходе проделанной работы проведено ознакомление с инструментом cовместной работы **Ngrok**, для корректной работы которого в ходе данной работы были установлены необходимые компоненты.
>
>**Tmux** не устанавливался, т.к. был установлен при выполнении работы № 17.
>Установлена более новая версия **ncurses** и версия i386 **Ngrok**.
>С использованием **Ngrok**  была организована совместная работа **Alissa** и **Bob**.
