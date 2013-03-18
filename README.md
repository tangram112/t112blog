# Szablon Bloga dla generatora Jekyll

> „Computer class” can’t be about teaching to use today’s software;<br>
> it must be about teaching kids to make tomorrow’s software.
>
> *Douglas Rushkoff*


## Instalacja szablonu

- Rejestrujemy się na serverze *github.com*
  (wybieramy *Free Plan*) i logujemy się na swoim koncie.
- Tworzymy nowe repozytorium o nazwie *TWÓJ_LOGIN.github.com*.
- Wchodzimy na stronę [wb://blog](http://wbzyl.github.com/)
  skąd pobieramy archiwum ZIP lub TAR.
- Rozpakowujemy archiwum, przechodzimy do utworzonego katalogu.
  Przykładowo:

```sh
unzip wbzyl-jekyll-template-96be463.zip        # dla ZIP
tar zxvf wbzyl-jekyll-template-96be463.tar.gz  # dla TAR
cd wbzyl-jekyll-template-96be463
```

- Edytujemy te dwa *tasks* z pliku *Rakefile*
  (zamieniasz *wbzyl* na *TWÓJ_LOGIN*):

```ruby
desc "Add wbzyl/wbzyl.github.com.git as remote"
task :setup do
  sh "git remote add github git@github.com:wbzyl/wbzyl.github.com.git"
end

desc "Deploy master branch to wbzyl.github.com master branch"
task :deploy do
  sh "git push github master"
end
```

Po kilku minutach znajdziesz swój blog tutaj:

```sh
http://TWÓJ_LOGIN.github.com/
```


## Piszemy pierwszy post

Posty umieszczamy w katalogu `_posts`.
Nazwy plików z postami tworzymy według schematu:

    rok-miesiąc-dzień-tytuł.md

Przykładowo:

    2013-02-29-jekyll-howto.md

Po napisaniu posta generujemy statyczną wersję bloga wykonując
z katalogu z blogiem polecenie:

*Uwaga:* Dla *repository pages*, dopisujemy w *_config.yml*:

```yaml
baseurl: /nazwa_repozytorium
```

Testujemy strony *user/organization/repository*:

```sh
jekyll --server PORT --auto # testowanie, localhost:PORT
```

Jeśli wszystko jest OK, to wdrażamy bloga na Githubie:

```sh
rake deploy
```


## Różne rzeczy…

* wdrażanie bloga na Githubie, [Creating Project Pages manually](https://help.github.com/articles/creating-project-pages-manually)
* korzystanie z rozszerzeń, [Template Data](https://github.com/mojombo/jekyll/wiki/template-data);
  jak? opisane jest to [README](http://github.com/rfelix/jekyll_ext) *jekyll_ext*
