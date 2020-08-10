# Перевод книги Linux From Scratch на русский язык

## Подготовка

Для конвертирования необходимы пакеты `libxml2`, `libxlst`, `tidy`. Для генерации TXT также потребуется `lynx`.

#### Для Debian

```bash
sudo apt update
sudo apt install libxml2-utils xsltproc tidy lynx
```

## Сборка

Доступные опции:

`BASEDIR=/path/to/directory` &ndash; путь к папке с результатом сборки книги

`REV=systemd` &ndash; сборка `systemd`-версии

#### XML в XHTML

```
make [OPTIONS]

# Примеры

make BASEDIR=./output/
make BASEDIR=./output/ REV=systemd
```


#### XML в одностраничный XHTML (nochunks)

```bash
make [OPTIONS] nochunks
```


#### XML в PDF

```bash
make [OPTIONS] pdf
```


#### XML в TXT

Следуйте инструкциям для `nochunks` и затем введите:

```bash
lynx -dump /path/to/nochunks > /path/to/output
```
