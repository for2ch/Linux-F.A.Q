# F.A.Q.

####Какой дистрибутив Linux самый лучший?

Лучшего нет. Начни с [Mint](https://linuxmint.com), [OpenSuse](https://ru.opensuse.org) или [Manjaro](https://manjaro.github.io).  Когда освоишь их, можешь попробовать [ArchLinux](https://www.archlinux.org).([пояснение](https://github.com/for2ch/Linux-F.A.Q/blob/master/resources/documets/%D0%94%D0%B8%D1%81%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%82%D0%B8%D0%B2%D1%8B.md))

![never forget](https://github.com/for2ch/Linux-F.A.Q/blob/master/resources/pictures/pnier.png)

####Какой дистрибутив самый быстрый?

Все примерно одинаковы. Можешь попробовать заменить DE или WM ([пояснение](https://github.com/for2ch/Linux-F.A.Q/blob/master/resources/documets/%D0%9E%20DE%20%D0%B8%20WM.md)). Если этого недостаточно, то попробуй собрать/скомпиллировать программы под свою систему. Проще всего это делается в дистрибутиве [Gentoo](https://www.gentoo.org/)([ман](https://github.com/for2ch/Linux-F.A.Q/blob/master/resources/documets/Gentoo.md)), но при желании, возможно в любом.

####Что делать, если всё зависло?

Нажми `Alt+PrtScr+k`. Графическая оболочка перезапустится ([пояснение](https://github.com/for2ch/Linux-F.A.Q/blob/master/resources/documets/Magic%20in%20SysRQ.md)).

####Как писать по-русски?

Введи в терминал `setxkbmap -model pc105 -layout us,ru -option grp:alt_shift_toggle`.

Теперь *alt+shift* переключает раскладку. Если не найдёшь в настройках DE, то добавь в автозагрузку.

####Могу ли я поставить Linux на EFI?

Да. Рекомендуемые дистрибутивы могут сделать это автоматически.

Если хочешь сам, то ознакомься вот с этой ([инструкцией](https://github.com/for2ch/Linux-F.A.Q/blob/master/resources/documets/%D0%98%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D1%8F%20%D0%BF%D0%BE%20%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B5%20%D1%81%20EFI.md)).

####Как разбить диск.

1. Автоматически

2. Вручную. Например так([пояснение](https://github.com/for2ch/Linux-F.A.Q/blob/master/resources/documets/%D1%80%D0%B0%D0%B7%D0%BC%D0%B5%D1%82%D0%BA%D0%B0.md)).

| Раздел        | Размер        | ФС          |
| ------------- | ------------- | ----------- |
| `/boot/efi`  | 256Mb  | FAT32
| `/`  | 40Gb  | ext4
| `/home/`  | Оставшееся место  | ext4

####Нужен ли swap (файл подкачки)

Да. 4Гб.([Пояснение](https://github.com/for2ch/Linux-F.A.Q/blob/master/resources/documets/swap.md))

####Нужна программа.

Если кратко, то

* Музыка:
  * `moc` для любителей терминала
  * `deadbeef` для любителей потыкать мышкой
* Фильмы, аниме:
  * `mpv` для любителей минимализма и клавиатуры
  * `smplayer` для любителей мыши

[Обширный список программ с описаниями на русском языке](https://wiki.archlinux.org/index.php/List_of_applications_(%D0%A0%D1%83%D1%81%D1%81%D0%BA%D0%B8%D0%B9))

[Список альтернатив всяческому софту](https://alternativeto.net/)

####Нужна именно та программа.

Если не готов пользоваться аналогами, то попробуй запустить программу в [wine](https://ru.wikipedia.org/wiki/Wine) или [виртуальной машине](https://ru.wikipedia.org/wiki/Виртуальная_машина).

####Нет звука, что делать?

1. Скорее всего у тебя [pulseaudio](https://ru.wikipedia.org/wiki/PulseAudio), тогда стоит открыть `pavucontrol` и посмотреть, какое устройство выводит звук

2. Если `pavucontrol` отсутствует, вероятно, у тебя [alsa](https://ru.wikipedia.org/wiki/ALSA), выполни `alsamixer` и убедись, что выбрано правильное устройство, а так же нажми “m”, если видишь под графами “MM”.

![alsamixer](https://raw.githubusercontent.com/for2ch/Linux-F.A.Q/master/resources/pictures/alsamixer.png "alsamixer")

####Здесь нет ответа.

Возможно, он найдётся на нашей [вики-страничке](https://github.com/for2ch/Linux-F.A.Q/wiki) или пришло то самое время спросить в треде.
