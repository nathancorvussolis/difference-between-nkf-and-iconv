# difference-between-nkf-and-iconv

## Version

* nkf 2.1.3
* libiconv 1.14

nkf Network Kanji Filter

http://sourceforge.jp/projects/nkf/

libiconv

http://www.gnu.org/software/libiconv/

---

## Build

### nkf

    $ tar zxf nkf-2.1.3.tar.gz

    $ cd nkf-2.1.3

    $ make

### iconv

    $ tar zxf libiconv-1.14.tar.gz

    $ cd libiconv-1.14

    $ ./configure --enable-extra-encodings

    $ make

---

## EUC-JIS-2004

    $ nkf-2.1.3/nkf -x --ic=EUC-JIS-2004 --oc=UTF-8 euc-jis-2004-with-char.txt > euc-jis-2004-nkf.txt

    $ libiconv-1.14/src/iconv_no_i18n -f EUC-JIS-2004 -t UTF-8  euc-jis-2004-with-char.txt > euc-jis-2004-iconv.txt
    
    $ diff  euc-jis-2004-nkf.txt euc-jis-2004-iconv.txt > diff-euc-jis-2004.txt
    
## Shift_JIS-2004

    $ nkf-2.1.3/nkf -x --ic=Shit_JIS-2004 --oc=UTF-8 sjis-0213-2004-with-char.txt > sjis-0213-2004-nkf.txt
    
    $ libiconv-1.14/src/iconv_no_i18n -f Shift_JIS-2004 -t UTF-8  sjis-0213-2004-with-char.txt > sjis-0213-2004-iconv.txt
    
    $ diff sjis-0213-2004-nkf.txt sjis-0213-2004-iconv.txt > diff-sjis-0213-2004.txt
