# Домашнее задание  
## Оглавление  
1. Установка Git на ПК  
2. Основы работы с командной строкой  
3. Настройка Git  
4. Регистрация на GitHub  
5. Защита данных с помощью SSH ключа    
6. Связывание локального и удалённого репозитория    
7. Синхронизация данных  
---
### 1. Установка Git на ПК  

Сначала нужно установить программу Git на ПК. Скачать её можно по ссылке [Git](https://git-scm.com/download/win).  
  
### 2. Основы работы с командной строкой  
После уставновки необходимо открыть коммандную строку Git Bash.  
В ней мы и будем работать, задавая необходимые комманды.  
Список комманд для коммандной строки:  
'''*pwd* - print work directory - вывести текущую директорию  
*cd (имя папки)* - change directory - сменить дирректорию  
*cd ~* - перейти в домашнюю дирректорию (символ домашней директории)  
*cd ..* - перейти на уровень выше (назад)  
*ls* - list - вывести список файлов и папок  
*ls -a* - вывести полный список файлов и папк (в т.ч. скрытые)  
*touch (имя файла)* - создать файл  
*mkdir (имя папки)* - создать папку  
*mkdir -p (путь к папке)* - создать несколько папок (одна в другой)  
*cp (имя файла -ов) (имя папки)* - copy - копировать указанный файл (или несколько) в указанную папку  
*mv (имя файла -ов) (имя папки)* - move - переместить указанный файл (или несколько) в указанную папку  
*cat* - прочитать файл - выведет содержимое файла (только для текстовых файлов)  
*rm  (имя файла)* - remove - удаление указанного файла  
*rmdir (имя папки)* - remove dirrectory - удаление папки (только для пустых папок)  
*rmdir -r (имя папки)* - удаление папки (включая всё её содержимое)  
*&&* - суммирование нескольиких комманд  
*(Tab)* - автозаполнение - подскажет возможные окончания начала камманды  
'''  

В коммандной строке также существуют и другие комманды но для текущих целей они не нужны. Необходимыве комманды будут введены по мере необходимости.  
  
### 3. Настройка Git  
Для проверки корректности установки Git необходимо ввести следующую комманду:  
'''git version'''  

После успешного выполнения данной команды отобразится версия программы Git.  
Далее необходимо указать программе своё имя и электронную почту.  
Сделать это можно с помощью двух комманд:  
'''  
git config --global user.name "имя пользователя"  
git config --global user.email "электронная почта"  
'''  

После данных действий необходимо создать папку с любым именем, которая в дальнейшем станет репозиторием.  
Далее в папке необходимо создать файлы, которые в будущем будут отслеживаемыми.  
  
После создания файлов необходимо инициализировать репозиторий коммандой:
'''  
git init  
'''  
«Разгитить» папку, если что-то пошло не так, — rm -rf .git
Если вы случайно сделали Git-репозиторием не ту папку, её можно «разгитить». Для этого нужно удалить скрытую подпапку .git.
$ cd <папка с репозиторием> # перешли в папку

$ rm -rf .git # удалили подпапку .git 
Разберём подробнее, что такое -rf:
ключ -r (от англ. recursive — «рекурсивно») позволяет удалять папки вместе с их содержимым;
ключ -f (от англ. force — «заставить») избавит вас от вопросов вроде «Вы точно хотите удалить этот файл? А этот? И этот тоже?».  
Будьте осторожны: в подпапке .git хранится история изменений. Если удалить .git, то вся история проекта будет стёрта без возможности восстановления — останется только последняя версия файлов.  
После инициализации можно проверить статус коммандой:  
'''  
git status  
'''  
Вы увидите именя соданых файлов красным цветом, это означает, что они не отселживаются.  
Для того чтобы сделать их отслеживаемыми их необходимо "добавить", коммандой:  
'''  
git add (имя файла) - добавить к сохранению указанный файл  
git add --all - добавить к сохранению все файлы в дирректории  
git add . - добавляет к сохранению всю текущую папку  
'''  
После выполнения данной команды система начинает "следить" за этими файлами, это значит что если внести какие-либо изменения, то Git об этом узнает.  
Можете открыть в блокноте свой созданный файл и написать в нем что-угодно и проверить статус. Вы увидите, что файл был изменен.  
Если изменённую версию файла нужно сохранить, то необходимо повторить комманду "добавление" и после чего сделать коммит:
'''  
git commit -m "Комментарий к комиту"  
'''  
В кавычках обычно пишут комментарий к комиту, то есть краткое описание внесённых изменений.  
Всё, теперь наш файл сохранён.  

ВАЖНО: Комментарий к коммиту должен быть информативным, т.е. лаокнично и кратко описывать суть внесённых изменений, место где были внесены изменения а также решаемую задачу или устраняемую проблему. Также у оргинзаций могут быть свои жесткие требования к оформлению комментариев, напимер указание номера выполненной задачи и т.д.  

Когда коммитов станет много то можно посмотреть историю коммитов, следющей коммандой:  
git log - выведет полный список коммитов  
git log --oneline - выведет краткий список коммитов  
  
### 4.Регистрация на GitHub.  
GitHub это платформа, позволяющая делится своими комитами со своей коммандой и всем миром. Это своего рода соц.сеть для программистов.  
Зарегестрироваться на ней можно перейдя по ссылке [GitHub](https://github.com/). 
 
  
### 5. Защита данных с помощью SSH ключа  
Для того чтобы защитить данные нужно создать SSH ключ.  
Для этого ввести комманду:  
'''  
ssh-keygen -t rsa -b 4096 -C "электронная почта, к которой привязан ваш аккаунт на GitHub"  
'''  
Это создаст да вашем компьютере папку SSH и в ней два файла: один публичный с разширением .pub, второй приватный - без расширения.  
Нужно скопировать содержимое публичного ключа коммандой скопировать содержимое ключа в буфер обмена:  
'''  
$ clip < ~/.ssh/id_rsa.pub  
'''  
Далее зайти в настройки своего профиля на GitHub в раздел SSH и там создать новый ключ, присвоить ему имя и в тело ключа вставить скопированное коммандой Ctrl + V. 
Проверьте правильность ключа с помощью следующей команды.  
$ ssh -T git@github.com  
Если всё сделил правильно, выйдет сообщение о том, что вы авторизированы.  

### 6. Связывание локального и удалённого репозитория  
После создания SSH ключа необходимо создать новый репозиторий. Названия репозитория рекомендуется делать такое же как и название папки на вашем компьютере.  
После создания нужно зайти в созданный репозиторий и связать локальный репозиторий с удалённым. Для этого нажать на кнопку SSH и скопировать появившуюся ссылку.  
Далее в коммандной строке написать комманду:  

  Откройте консоль, перейдите в каталог локального репозитория и введите команду git remote add (от англ. remote — «удалённый» и add — «добавить»).
$ cd ~/dev/first-project
$ git remote add origin git@github.com:%ИМЯ_АККАУНТА%/first-project.git 
Команде необходимо передать два параметра: имя удалённого репозитория и его URL. В качестве имени используйте слово origin. А URL вы скопировали со страницы удалённого репозитория.

Это действие свяжет вашу папку на копьютере с удалённым репозиторием. 
Убедиться, что репозитории связаны, — git remote -v
Отлично: вы связали локальный репозиторий с удалённым. Осталось убедиться, что всё работает, с помощью следующей команды.
$ git remote -v
origin    git@github.com:%ИМЯ_АККАУНТА%/%ИМЯ-ПРОЕКТА%.git (fetch)
origin    git@github.com:%ИМЯ_АККАУНТА%/%ИМЯ-ПРОЕКТА%.git (push) 
В выводе вы должны увидеть две строчки, аналогичные тем, что показаны выше.
Флаг -v — короткая форма флага --verbose (англ. «подробный»). Он позволяет показать больше информации в выводе.

  
### 7. Синхронизация данных.  
Теперь всё готово для синхронизации. Для этого нужно выполнить комманду push, от слова "толкать".  
Первый раз необходимо выполнить её с флагом -u и добавлением origin main.  
'''  
git push -u origin main  
'''  
После можно будет писать только git push.  
Заходим в свой репозиторий через GitHub и увидим свой файл.
