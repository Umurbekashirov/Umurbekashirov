<img src="https://github.com/AlexeyShpavda/alexeyshpavda/blob/master/assets/the_unlimited.png" alt="Umurbek Ashirov" width="180"/>
В кавычках src="" указывается ссылка на желаемую вами картинку. В данном примере картинка загружена в репозиторий на GitHub. В width="" указывается ширина картинки. Аналогично можно использовать атрибут heigth="", который используется для обозначения высоты.

Если есть необходимость сделать изображение кликабельным, подойдет следующий синтаксис:

<a href="https://the-unl.com" target="_blank">
  <img src="https://github.com/AlexeyShpavda/alexeyshpavda/blob/master/assets/the_unlimited.png" alt="The Unlimited" width="180"/>
</a>
В данном случае, тэг <img> оборачивается тэгом <а> - ссылкой.

В href="" между кавычек вставляем ссылку, по которой будет осуществляться переход при нажатии на картинку.

target="_blank" откроет ссылку в новой вкладке.

Также картинку можно добавить следующим способом:

[![Header](https://github.com/AlexeyShpavda/alexeyshpavda/blob/master/assets/header.png)](https://www.shpavda.com/)
Использование иконок
С добавлением изображений все понятно, но при добавлении различных инструментов, которые вы используете: языков, фреймворков и т.д., - стоит использовать уже готовые иконки вместо того, чтобы "изобретать колесо" в фотошопе.

Сервисы, которые предоставят вам такие иконки:

Simple Icons - на момент написания данной статьи имеется более 2 000 иконок популярных брендов.

Icons8 - имеет большое количество иконок, иллюстраций и фотографий. Использование некоторых возможностей не бесплатно.

Flaticon - огромное количество векторных картинок и целых коллекций этих картинок. За многие также придется заплатить денюжку.



Добавление бейджей
Добавление бейджей в файлы README тоже довольно распространено не только в файлах профиля, но и в файлах различных проектов. Для создания бейджей можно использовать Shields.io.

В целом, для добавления бейджа используется следующий синтаксис:

https://img.shields.io/badge/<LABEL>-<MESSAGE>-<COLOR>
Вместо <LABEL>, <MESSAGE>, <COLOR> добавляются соответствующие значения. После чего получается стандартный бейдж. Для создания также доступны бейджи и других стилей. Для этого в конце вышеприведенной записи необходимо добавить один из следующих сегментов в зависимости от необходимого стиля:



Также можно добавлять и различные логотипы, как показана в примере ниже.



Вот так могут выглядеть бейджи, сделанные на shields.io:



Исходный код:

### Languages and Tools:
![Flutter](https://img.shields.io/badge/-Flutter-090909?style=for-the-badge&logo=flutter&logoColor=47C5FB)
![Dart](https://img.shields.io/badge/-Dart-090909?style=for-the-badge&logo=dart&logoColor=097CDB)
![Firebase](https://img.shields.io/badge/-Firebase-090909?style=for-the-badge&logo=firebase&logoColor=F8C52C)
![TensorFlow](https://img.shields.io/badge/-TensorFlow-090909?style=for-the-badge&logo=tensorflow&logoColor=F88C00)
![JavaScript](https://img.shields.io/badge/-JavaScript-090909?style=for-the-badge&logo=JavaScript&logoColor=E9D54D)
![.Net](https://img.shields.io/badge/-Framework-090909?style=for-the-badge&logo=.net&logoColor=E5D3FF)
![C++](https://img.shields.io/badge/-C++-090909?style=for-the-badge&logo=C%2b%2b&logoColor=6296CC)

### Socials:
[![Telegram](https://img.shields.io/badge/-Telegram-090909?style=for-the-badge&logo=telegram&logoColor=27A0D9)](https://t.me/the_cybermania)
[![YouTube](https://img.shields.io/badge/-YouTube-090909?style=for-the-badge&logo=YouTube&logoColor=FF0000)](https://www.youtube.com/alexeyshpavdaMain)
[![Instagram](https://img.shields.io/badge/-Instagram-090909?style=for-the-badge&logo=instagram&logoColor=B4068E)](https://www.instagram.com/alexeyshpavda)
[![Twitter](https://img.shields.io/badge/-Twitter-090909?style=for-the-badge&logo=Twitter&logoColor=1C9DEB)](https://twitter.com/alexeyshpavda)
[![LinkedIn](https://img.shields.io/badge/-LinkedIn-090909?style=for-the-badge&logo=linkedin&logoColor=007BB6)](https://www.linkedin.com/in/alexeyshpavda)
[![Vkontakte](https://img.shields.io/badge/-Vkontakte-090909?style=for-the-badge&logo=Vk&logoColor=4F7DB3)](https://vk.com/alexeyshpavda)
[![Facebook](https://img.shields.io/badge/-Facebook-090909?style=for-the-badge&logo=Facebook&logoColor=1195F5)](https://www.facebook.com/alexeyshpavda)
Примечание: как вы видите, в вышеприведенном примере в конструкции https://img.shields.io/badge/<LABEL>-<MESSAGE>-<COLOR> отсутствует лейбл, то есть запись принимает следующий вид https://img.shields.io/badge/-<MESSAGE>-<COLOR>. Как следствие, в итоговом варианте у бейджа отсутствует левая часть.

Для полного ознакомления с тем, как использовать Shield.io, рекомендуется перейти по ссылке.

Как добавить WorkFlow на GitHub
С помощью workflow мы можем добавить последние записи из блога или, например, ваши последние видео на youtube. Выглядит это следующим образом:



Для этого нужно:

1. Добавить следующий фрагмент кода:

<!-- BLOG-POST-LIST:START -->
<!-- BLOG-POST-LIST:END -->
2. Создать папку .github и внутри неё еще одну папку workflows, если она не существует.



3. В этой папке создать файл blog-post-workflow.yml 



(в примере я выводил последние видео с youtube, поэтому выбрал другое название)

4. Добавить в файл следующий код:

name: Latest blog post workflow
on:
  schedule: # Run workflow automatically
    - cron: '0 * * * *' # Runs every hour, on the hour
  workflow_dispatch: # Run workflow manually (without waiting for the cron to be called), through the GitHub Actions Workflow page directly

jobs:
  update-readme-with-blog:
    name: Update this repo's README with latest blog posts
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v2
      - name: Pull in dev.to posts
        uses: gautamkrishnar/blog-post-workflow@v1
        with:
          feed_list: "https://dev.to/feed/gautamkrishnar,https://www.gautamkrishnar.com/feed/"
5. Заменить приведенный выше список URL-адресов собственными адресами. Для этого будет полезна ссылка, перейдя по которой, вы найдете необходимые ссылки для подгрузки ваших постов из популярных источников: Youtube, Medium, Reddit, Dev.to, Wordpress и т.д.



6. Теперь нужно коммитнуть изменения и подождать, пока код отработает, либо же запустить его в ручную.

Для того чтобы узнать, как это сделать, лучше всего посмотреть сегмент в данном видео, в нем мы проходим по каждому из вышеперечисленных шагов и меняем все необходимое.

Также информация на английском языке из уст автора: https://github.com/gautamkrishnar/blog-post-workflow

Как отобразить статистику GitHub профиля
Напоследок, осталось разобраться с выводом статистики в GitHub Profile Readme. Для этого мы воспользуемся следующим репозиторием: https://github.com/anuraghazra/github-readme-stats

Добавление статистики профиля может быть произведено всего одной строчкой кода:

[![Anurag's GitHub stats](https://github-readme-stats.vercel.app/api?username=alexeyshpavda)](https://github.com/anuraghazra/github-readme-stats)
Единственное, что нужно сделать - это указать в ?username= имя вашего пользователя.



Для настройки и стилизации бейджа со статистикой рекомендуется перейти в вышеуказанный репозиторий и найти необходимые вам настройки.

Полезные ссылки:

Профиль на GitHub: https://github.com/AlexeyShpavda
Иконки: https://simpleicons.org
Бейджи: https://shields.io
Workflow: https://github.com/gautamkrishnar/blog-post-workflow
Полезное дополнение к Worflow: https://en.wikipedia.org/wiki/Cron 
Stats: https://github.com/anuraghazra/github-readme-stats

Телеграм: https://t.me/the_cybermania
Видео: https://www.youtube.com/watch?v=1yELlB39TvY



GitHub
README.md
GitHub Profile Readme
Как создать GitHub Profile Readme
Как добавить Profile Readme в Профиль
Как оформить профиль на GitHub
Статистика GitHub профиля
