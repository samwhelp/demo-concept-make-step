
# demo-basic-make-step

## 緣起

此專案是因為要[回覆](https://www.ubuntu-tw.org/modules/newbb/viewtopic.php?post_id=358966#forumpost358966)這篇[討論](https://www.ubuntu-tw.org/modules/newbb/viewtopic.php?post_id=358962#forumpost358962)，所產生的靈感，
用意只是要輔助理解一些概念。


## 常見編譯的參考步驟

* $ `./configure`
* $ `make`
* $ `sudo make install`


## 正常操作步驟


### configure

執行下面指令

``` sh
$ ./configure
```

註：上面這個動作，請參考「[configure](configure)」裡面的實作。

會先檢查「build-essential」這個套件是否已經安裝，
若尚未安裝，會提示請您先安裝。

若已經「build-essential」這個套件了，

接下來則會產生一個檔案「msg.h」，檔案內容類似如下

```
#define MSG_DEMO "4.13.0-16-generic"
```


### make

執行下面指令，執行編譯的動作

``` sh
$ make
```

註：上面這個動作，請參考「[Makefile](Makefile)」裡的「[demo:](Makefile#L4)」那個「Rule」。

若編譯成功，則會產生「demo」這個檔案。

執行

``` sh
$ ./demo
```

則會顯示類似如下的訊息

```
Test Message: 4.13.0-16-generic
```


### make install

執行下面指令，將「demo」這個檔案，安裝到「/usr/local/bin/」這個資料夾，
也就是將「demo」這個檔案，安裝到「/usr/local/bin/demo」這個路徑。

``` sh
$ sudo make install
```

註：上面這個動作，請參考「[Makefile](Makefile)」裡的「[install:](Makefile#L7)」那個「Rule」。

假設是在一般使用者的帳號下操作，所以需要加上「sudo」。


## 額外操作步驟


### make clean

執行下面指令，則會將剛剛產生的「dmeo」和「msg.h」刪除。

``` sh
$ make clean
```

註：上面這個動作，請參考「[Makefile](Makefile)」裡的「[clean:](Makefile#L13))」那個「Rule」。


### make uninstall

執行下面指令，則會將「/usr/local/bin/demo」這個檔案刪除。

``` sh
$ sudo make uninstall
```

註：上面這個動作，請參考「[Makefile](Makefile)」裡的「[uninstall:](Makefile#L10)」那個「Rule」。

假設是在一般使用者的帳號下操作，所以需要加上「sudo」。
