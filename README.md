# pHash-0.9.6 patched version for php71

pHash-0.9.6 was released at 2013-04-23, but there are serveral problems for certain usage

Based on [hszcg's work](https://github.com/hszcg/pHash-0.9.6) for two patches:


## Installation

### CentOS 7

#### 1. pHash

```
$ yum install -y libsndfile-devel libtool-libs gcc gcc-c++ unzip 
$ yum install ImageMagick ImageMagick-devel
```

If don't have PHP 7.1

```
$ yum install epel-release
$ yum install http://rpms.remirepo.net/enterprise/remi-release-7.rpm
$ yum --enablerepo=remi-php71 install php-cli php-devel php-xml php-soap php-xmlrpc php-mbstring php-json php-gd php-mcrypt
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
