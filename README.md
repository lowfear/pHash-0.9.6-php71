# pHash-0.9.6 patched version for php71

pHash-0.9.6 was released at 2013-04-23, but there are serveral problems for certain usage

Based on [hszcg's work](https://github.com/hszcg/pHash-0.9.6).

## Fixes
### "For images with all pixels of the same RGB value..."
https://github.com/nsant061/pHash/commit/0dd9d1dbcd3ac0488586d9a29a80540d5763e415

### "For new PNG..."
https://github.com/charlizesmith/pHash-0.9.6-patches/commit/89979ba6da1566c92ea8fc256836aa258cc69ab8

!Without Video Hash

## Installation

### CentOS 7

#### 1. pHash

```
$ yum install -y libsndfile-devel libtool-libs gcc gcc-c++ unzip wget
$ yum install ImageMagick ImageMagick-devel
```

```
$ cd ~
$ mkdir x
$ cd x

$ wget https://github.com/lowfear/pHash-0.9.6-php71/blob/master/libs/CImg_2.5.0_pre011819.zip
$ wget https://github.com/lowfear/pHash-0.9.6-php71/blob/master/libs/libsamplerate-0.1.9.tar.gz
$ wget https://github.com/lowfear/pHash-0.9.6-php71/blob/master/libs/mpg123-1.25.10.tar.bz2

$ unzip CImg_2.5.0_pre011819.zip
$ cp CImg*/CImg.h /usr/local/include

$ tar xvf libsamplerate-0.1.9.tar.gz
$ cd libsamplerate-0.1.9
$ ./configure
$ make && make install

$ cd ..

$ tar xvf mpg123-1.25.10.tar.bz2
$ cd mpg123-1.25.10
$ ./configure
$ make && make install

$ cd ..

$ wget https://github.com/lowfear/pHash-0.9.6/archive/master.zip

$ unzip master.zip
$ cd pHash-0.9.6-master/pHash-0.9.6/
$ ./configure --enable-video-hash=no LDFLAGS='-lpthread'
$ make && make install
```

```
$ cd pHash-0.9.6
$ ./configure
$ make && sudo make install
```

#### 2. PHP binding

If don't have PHP 7.1

```
$ yum install epel-release
$ yum install http://rpms.remirepo.net/enterprise/remi-release-7.rpm
$ yum --enablerepo=remi-php71 install php-cli php-devel php-xml php-soap php-xmlrpc php-mbstring php-json php-gd php-mcrypt
```

```
$ cd bindings/php
$ phpize
$ ./configure LIBS="-lpthread"
$ make && sudo make install
```

PHP 7.0-7.1:
```
$ echo "extension=pHash.so" | sudo tee /etc/php.d/20-phash.ini
$ php -m
# you should see pHash in the list
```



## Reference

1. https://github.com/hszcg/pHash-0.9.6


## License

Same as [pHash](http://www.phash.org/), [GPL-3.0](http://www.gnu.org/licenses/gpl-3.0.html).
