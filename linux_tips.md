**tip1: Zip files:**
```bash
tar -czvf file.tar.gz HW1
```

**tip2: detach screen, refer to [screen command](https://blog.csdn.net/C_chuxin/article/details/84328644) and [screen back](https://blog.csdn.net/hejunqing14/article/details/50338161)**

*Detach step:*

a. Give a screen a name:

```bash
screen -S test # case sensitive
```
b. In the current screen. Hold control, then a+d orderly. It succeed when showing below:

```bash
[detached from 12306.test]
```

*Check whether it's successful step:*

a.

```bash
screen -ls
(base) pelican03 ~ 1001$ screen -ls
There are screens on:
        12939.TRain     (Detached)
        12306.tst       (Detached)
        28967.pts-42.pelican03  (Detached)
        14755.pts-17.pelican03  (Detached)
4 Sockets in /var/run/screen/S-yuanqi.
```
b. 

```bash
screen -r test # Retach 
```

**Note:**

```bash
Kill -9 12306 # kill thread
screen -wipe # clean screen
sh train_Copy1.sh>>out16_5.txt # output into a new file, since sometimes one screen is not big enough
```
