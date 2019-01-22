# pHash-0.9.6 patched version for php71

pHash-0.9.6 was released at 2013-04-23, but there are serveral problems for certain usage

Based on [hszcg's work](https://github.com/hszcg/pHash-0.9.6) for two patches:


## Installation

### CentOS 7

#### 1. pHash

```
$ sudo apt-get install libavformat-dev libmpg123-dev libsamplerate-dev libsndfile-dev
$ sudo apt-get install cimg-dev libavcodec-dev ffmpeg libswscale-dev
```

```
$ cd pHash-0.9.6
$ ./configure
$ make && sudo make install
```

#### 2. PHP binding

```
$ cd bindings/php
$ phpize
$ ./configure LIBS="-lpthread"
$ make && sudo make install
```

PHP 7.0-7.1:
```
sudo echo "extension=pHash.so" | sudo tee /etc/php/7.0/mods-available/pHash.ini
php -m
# you should see pHash in the list
```



## Reference

1. https://github.com/hszcg/pHash-0.9.6


## License

Same as [pHash](http://www.phash.org/), [GPL-3.0](http://www.gnu.org/licenses/gpl-3.0.html).
