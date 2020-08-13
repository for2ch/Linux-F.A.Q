# F.A.Q.

#### Какой дистрибутив Linux самый лучший?

Лучшего нет. Начни с [Linux Mint](http://mintlinux.ru/) или [Calculate](http://www.calculate-linux.org/ru).  Когда освоишь их, можешь попробовать [Void Linux](http://www.voidlinux.eu/), [ArchLinux](https://www.archlinux.org) или [Gentoo](https://gentoo.org/). ([Пояснение](https://github.com/for2ch/Linux-F.A.Q/blob/master/resources/documets/%D0%94%D0%B8%D1%81%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%82%D0%B8%D0%B2%D1%8B.md))

#### Какой дистрибутив самый быстрый?

Все примерно одинаковы. Можешь попробовать заменить DE или WM ([пояснение](https://github.com/for2ch/Linux-F.A.Q/blob/master/resources/documets/%D0%9E%20DE%20%D0%B8%20WM.md)). Если этого недостаточно, то попробуй собрать/скомпилировать программы под свою систему. Проще всего это делается в дистрибутиве [Gentoo](https://www.gentoo.org/) ([ман](https://github.com/for2ch/Linux-F.A.Q/blob/master/resources/documets/Gentoo.md)), но при желании, возможно в любом.

Для относительно слабых/старых ПК может подойти [Puppy Linux](http://puppylinux.org/main/Overview%20and%20Getting%20Started.htm) или [Void Linux](http://www.voidlinux.eu/).

#### Какой дистрибутив из часто рекомендуемых лучше НЕ ставить новичку (без веских причин)

OpenSUSE: требует значительно больше усилий, чтобы воспроизводить видео, баги интерфейса, потенциальные проблемы при обновлении.

Debian: самый забагованый установщик, потенциальные проблемы с железом, если специально не скачать nonfree образ, очень старые версии програм.

#### Что делать, если всё зависло?

Нажми `Alt+PrtScr+k`. Графическая оболочка перезапустится ([пояснение](https://github.com/for2ch/Linux-F.A.Q/blob/master/resources/documets/Magic%20in%20SysRQ.md)).

#### Как писать по-русски?

Введи в терминал `setxkbmap -layout us,ru -option grp:alt_shift_toggle`.

Теперь *alt+shift* переключает раскладку. Если не найдёшь в настройках DE, то добавь в автозагрузку.

#### Могу ли я поставить Linux на EFI?

Да. Рекомендуемые дистрибутивы могут сделать это автоматически.
Но лучше воспользоваться efibootmgr и сделать efi-stub, таким образом можно будет грузить ядро прямо из uefi без сторонних загрузчиков.
https://wiki.debian.org/EFIStub


Если хочешь сам, то ознакомься вот с этой [инструкцией](https://github.com/for2ch/Linux-F.A.Q/blob/master/resources/documets/%D0%98%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D1%8F%20%D0%BF%D0%BE%20%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B5%20%D1%81%20EFI.md).

#### Как разбить диск.

1. Автоматически;

2. Вручную. Например, так ([пояснение](https://github.com/for2ch/Linux-F.A.Q/blob/master/resources/documets/%D1%80%D0%B0%D0%B7%D0%BC%D0%B5%D1%82%D0%BA%D0%B0.md)):

| Раздел        | Размер        | ФС          |
| ------------- | ------------- | ----------- |
| `/boot/efi`  | 64Mb  | FAT32
| `/`  | 40Gb  | ext4
| `/home/`  | Оставшееся место  | ext4

#### Нужен ли swap (файл подкачки)?

Да, 4Гб ([пояснение](https://github.com/for2ch/Linux-F.A.Q/blob/master/resources/documets/swap.md)).
Если RAM 8Gb и больше, то ненужно. Если оконный менеджер легкий, то и 4Gb должно хватить.
Однако своп нужен для гибернации (suspend to disk), если вместо гибернации используете обычный suspend to RAM то swap не нужен.

#### Мало оперативной памяти?

Если из-за постоянного использования swap-файла страдает отзывчивость системы, то, возможно, стоит попробовать [zram](https://wiki.archlinux.org/index.php/ZRAM#Zram_or_zswap).
Zram создает сжатое блочное устройство в оперативной памяти, которое можно использовать как swap-файл, т.е.
выгружаемые страницы будут храниться не на "медленном" диске, а в оперативной памяти в сжатом виде, что требует некоторых затрат процессорного времени.

###### На что обратить внимание при использовании zram
* На параметр `--priority` у комманды `swapon`
* На [параметр](https://en.wikipedia.org/wiki/Swappiness) `vm.swappiness`

**Пример**: Для создания одного zram-устройства емкостью _2GiB_ с алгоритмом сжатия _lz4_:
```
# modprobe zram
# echo lz4 > /sys/block/zram0/comp_algorithm
# echo 2G > /sys/block/zram0/disksize
# mkswap --label zram0 /dev/zram0
# swapon --priority 100 /dev/zram0
```
_Примечание: # - означает выполнение под root_

#### Нужна программа.

Если кратко, то:

* Музыка:
  * `moc`, `cmus` для любителей терминала
  * `deadbeef` для любителей потыкать мышкой
* Фильмы, аниме:
  * `mpv` для любителей минимализма и клавиатуры
  * `smplayer` для любителей мыши

[Обширный список программ с описаниями на русском языке.](https://wiki.archlinux.org/index.php/List_of_applications_(%D0%A0%D1%83%D1%81%D1%81%D0%BA%D0%B8%D0%B9))

[Список альтернатив всяческому софту.](https://alternativeto.net/)

#### Нужна именно та программа.

Если не готов пользоваться аналогами, то попробуй запустить программу в [wine](https://ru.wikipedia.org/wiki/Wine) или [виртуальной машине](https://ru.wikipedia.org/wiki/Виртуальная_машина).

#### Нет звука, что делать?

1. Скорее всего у тебя [pulseaudio](https://ru.wikipedia.org/wiki/PulseAudio), тогда стоит открыть `pavucontrol` и посмотреть, какое устройство выводит звук;

2. Если `pavucontrol` отсутствует, вероятно, у тебя [alsa](https://ru.wikipedia.org/wiki/ALSA), выполни `alsamixer` и убедись, что выбрано правильное устройство, а так же нажми “m”, если видишь под графами “MM”.

![alsamixer](https://raw.githubusercontent.com/for2ch/Linux-F.A.Q/master/resources/pictures/alsamixer.png "alsamixer")

#### Здесь нет ответа.

Возможно, он найдётся на нашей [вики-страничке](https://github.com/for2ch/Linux-F.A.Q/wiki). Или пришло то самое время спросить в треде.
