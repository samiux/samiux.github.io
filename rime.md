|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# How to install Chinese Input Method in Ubuntu 22.04 LTS with RIME

RIME (Rime Input Method Engine, 中州韻輸入法引擎) is a cross platform Chinese Input Method Engine.  You can even use it in English environment.  You can even type traditional Chinese and displays it as simplified Chinese and vice verse.  The following setup is for ```cangjie5 (倉頡五代)```, ```cangjie5 express (倉頡 快打模式)``` and ```quick5 (速成)```.

Install RIME in Ubuntu 22.04 LTS with ibus.

```
sudo apt update
sudo apt install ibus-rime rime-data-quick5
```

Select ```Settings``` at the right top corner of Ubuntu Desktop.  Then select ```Region and Language``` and ```Manage Installed Languages``` as well as ```Install / Remove Languages...```.  After that, select both ```Chinese (simplified)``` and ```Chinese (traditional)```.

Reboot your box.

Select ```Settings``` at the right top corner of Ubuntu Desktop.  Then select ```Keyboard``` and ```+``` as well as ```Chinese (Hong Kong)``` and ```Chinese (Rime)```.

```
wget https://raw.githubusercontent.com/samiux/update-scripts/master/default.custom.yaml -O ~/.config/ibus/rime/default.custom.yaml
```

```[Windows] + [Space]``` to toggle between English and Chinese.  Select ```部署``` to reload the setting.

```[Ctrl] + [`]``` or ```[F4]``` to popup a menu in order to select your input method.

```[Space]``` to select the word.

```[.]``` for page down when the words list menu is on.

```[,]``` for page up when the words list menu is on.

You can even change the number of words to be displayed in the words list menu at ```schema.yaml```, such as ```quick5.schema.yaml```.

```
nano ~/.config/ibus/rime/build/quick5.schema.yaml
```

## REFERENCE

- [RIME／中州韵输入法引擎（Rime Input Method Engine）](https://rime.im/)  
- [RIME Wiki](https://github.com/rime/home/wiki)  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

