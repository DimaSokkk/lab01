# lab01
## Laboratory work I

Данная лабораторная работа посвещена изучению утилит для разработки проектов

## Tasks

- [ ] 1. Ознакомиться со ссылками учебного материала
- [ ] 2. Выполнить инструкцию учебного материала
- [ ] 3. Составить отчет и отправить ссылку личным сообщением в **Slack**

## Tutorial

```bash
$ export GITHUB_USERNAME=<имя_пользователя>
$ export GIST_TOKEN=<сохраненный_токен>
$ alias edit=<nano|vi|vim|subl>
```

```sh
$ mkdir -p ${GITHUB_USERNAME}/workspace
$ cd ${GITHUB_USERNAME}/workspace
$ pwd
$ cd ..
$ pwd
```

```sh
$ mkdir -p workspace/tasks/
$ mkdir -p workspace/projects/
$ mkdir -p workspace/reports/
$ cd workspace
```

```sh
# Debian
$ wget https://nodejs.org/dist/v6.11.5/node-v6.11.5-linux-x64.tar.xz
$ tar -xf node-v6.11.5-linux-x64.tar.xz
$ rm -rf node-v6.11.5-linux-x64.tar.xz
$ mv node-v6.11.5-linux-x64 node
```

```sh
$ ls node/bin
$ echo ${PATH}
$ export PATH=${PATH}:`pwd`/node/bin
$ echo ${PATH}
$ mkdir scripts
$ cat > scripts/activate<<EOF
export PATH=\${PATH}:`pwd`/node/bin
EOF
$ source scripts/activate
```

```sh
$ gem install gist
```

```sh
$ (umask 0077 && echo ${GIST_TOKEN} > ~/.gist)
```

## Report

```sh
$ export LAB_NUMBER=01
$ git clone https://github.com/tp-labs/lab${LAB_NUMBER} tasks/lab${LAB_NUMBER}
$ mkdir reports/lab${LAB_NUMBER}
$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md
$ cd reports/lab${LAB_NUMBER}
$ edit REPORT.md
$ gist REPORT.md
```

## Links

### Unix commands

- [ar](https://en.wikipedia.org/wiki/Ar_(Unix))
- [cat](https://en.wikipedia.org/wiki/Cat_(Unix))
- [cd](https://en.wikipedia.org/wiki/Cd_(command))
- [cp](https://en.wikipedia.org/wiki/Cp_(Unix))
- [cut](https://en.wikipedia.org/wiki/Cut_(Unix))
- [echo](https://en.wikipedia.org/wiki/Echo_(command))
- [env](https://en.wikipedia.org/wiki/Env_(shell))
- [ex](https://en.wikipedia.org/wiki/Ex_(editor))
- [file](https://en.wikipedia.org/wiki/File_(command))
- [find](https://en.wikipedia.org/wiki/Find)
- [ls](https://en.wikipedia.org/wiki/Ls)
- [man](https://en.wikipedia.org/wiki/Man_page)
- [mkdir](https://en.wikipedia.org/wiki/Mkdir)
- [mv](https://en.wikipedia.org/wiki/Mv)
- [nm](https://en.wikipedia.org/wiki/Nm_(Unix))
- [ps](https://en.wikipedia.org/wiki/Ps_(Unix))
- [pwd](https://en.wikipedia.org/wiki/Pwd)
- [rm](https://en.wikipedia.org/wiki/Rm_(Unix))
- [sed](https://en.wikipedia.org/wiki/Sed)
- [touch](https://en.wikipedia.org/wiki/Touch_(Unix))

### Package Managers

- [apt](http://help.ubuntu.ru/wiki/apt) | [dnf](https://en.wikipedia.org/wiki/DNF_(software)) | [yum](https://fedoraproject.org/wiki/Yum/ru)
- [brew](https://brew.sh) | [linuxbrew](http://linuxbrew.sh)
- [npm](https://docs.npmjs.com)

### Software

- [curl](https://www.gitbook.com/book/bagder/everything-curl/details)
- [wget](https://www.gnu.org/software/wget/manual/wget.pdf)
- [clang](https://clang.llvm.org)
- [g++](https://gcc.gnu.org/onlinedocs/gcc-4.0.2/gcc/G_002b_002b-and-GCC.html)
- [make](https://en.wikipedia.org/wiki/Make_(software))
- [open](https://developer.apple.com/legacy/library/documentation/Darwin/Reference/ManPages/man1/open.1.html)
- [openssl](https://www.openssl.org)
- [nano](https://www.nano-editor.org)
- [tree](https://linux.die.net/man/1/tree)
- [vim](http://www.vim.org)

## Homework

1. Скачайте библиотеку *boost* с помощью утилиты **wget**. Адрес для скачивания `https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz`.
```sh
$ wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
```
2. Разархивируйте скаченный файл в директорию `~/boost_1_69_0`
```sh
$ tar -xvf boost_1_69_0.tar.gz
```
3. Подсчитайте количество файлов в директории `~/boost_1_69_0` **не включая** вложенные директории.
```sh
$ cd boost_1_69_0
tree -a -L 1
.
├── boost
├── boost-build.jam
├── boostcpp.jam
├── boost.css
├── boost.png
├── bootstrap.bat
├── bootstrap.sh
├── doc
├── index.htm
├── index.html
├── INSTALL
├── Jamroot
├── libs
├── LICENSE_1_0.txt
├── more
├── rst.css
├── status
└── tools

- 6 directories, 12 files
```
4. Подсчитайте количество файлов в директории `~/boost_1_69_0` **включая** вложенные директории.
```sh
$ find -type f | wc -l
61191

```
5. Подсчитайте количество заголовочных файлов, файлов с расширением `.cpp`, сколько остальных файлов (не заголовочных и не `.cpp`).
```sh
$ find -name '*.h' | wc -l
296
$ find -name '*.cpp' | wc -l
13774
$ find '!' -name '*.h' -a '!' -name '*.cpp' | wc -l
52759
```
6. Найдите полный пусть до файла `any.hpp` внутри библиотеки *boost*.
```sh
$ find $(pwd) -name any.hpp
 /home/nejelia/boost_1_69_0/boost/hana/any.hpp
 /home/nejelia/boost_1_69_0/boost/hana/fwd/any.hpp
 /home/nejelia/boost_1_69_0/boost/spirit/home/support/algorithm/any.hpp
 /home/nejelia/boost_1_69_0/boost/any.hpp
 /home/nejelia/boost_1_69_0/boost/xpressive/detail/utility/any.hpp
 /home/nejelia/boost_1_69_0/boost/proto/detail/any.hpp
 /home/nejelia/boost_1_69_0/boost/fusion/include/any.hpp
 /home/nejelia/boost_1_69_0/boost/fusion/algorithm/query/detail/any.hpp
 /home/nejelia/boost_1_69_0/boost/fusion/algorithm/query/any.hpp
 /home/nejelia/boost_1_69_0/boost/type_erasure/any.hpp
```
7. Выведите в консоль все файлы, где упоминается последовательность `boost::asio`.
```sh
$ grep -R -l "boost::asio"
```
8. Скомпилирутйе *boost*. Можно воспользоваться [инструкцией](https://www.boost.org/doc/libs/1_61_0/more/getting_started/unix-variants.html#or-build-custom-binaries) или [ссылкой](https://codeyarns.com/2017/01/24/how-to-build-boost-on-linux/).
```sh
$ sudo apt install libicu-dev
$ ./bootstrap.sh --prefix=boost_output
$ ./b2 install
```
9. Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию `~/boost-libs`.
```sh
$ mkdir \boost-libs
$ mv ~/boost_1_69_0/boost_output/lib/ ~/boost-libs/

```
10. Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.
```sh
$ du -h -a | sort -h
8,0K	./test/railsys/program/include
12K	./test/railsys/program/main
12K	./test/railsys/program/liba
44K	./test/railsys/program
8,0K	./test/railsys/libx/include
12K	./test/railsys/libx/src
28K	./test/railsys/libx
76K	./test/railsys
96K	./test/qt4
16K	./test/boostbook
184K	./test/qt5
12K	./test/test2
48K	./test/core-language
16K	./test/project-test3/lib3
12K	./test/project-test3/lib
12K	./test/project-test3/lib2/helper
28K	./test/project-test3/lib2
76K	./test/project-test3
24K	./test/project-test4/lib
12K	./test/project-test4/lib2
72K	./test/project-test4
8,0K	./test/prebuilt/ext/debug
8,0K	./test/prebuilt/ext/release
40K	./test/prebuilt/ext
56K	./test/prebuilt
100K	./test/toolset-mock/src
120K	./test/toolset-mock
12K	./test/startup/boost-root/build
20K	./test/startup/boost-root
8,0K	./test/startup/no-bootstrap3
8,0K	./test/startup/bootstrap-explicit
8,0K	./test/startup/bootstrap-env
8,0K	./test/startup/no-bootstrap1/subdir
16K	./test/startup/no-bootstrap1
8,0K	./test/startup/bootstrap-implicit
8,0K	./test/startup/no-bootstrap2
80K	./test/startup
1,9M	./test
36K	./notes
580K	./boost_output/bin
20K	./boost_output/share/boost-build/example/make
16K	./boost_output/share/boost-build/example/time
24K	./boost_output/share/boost-build/example/complex-testing
24K	./boost_output/share/boost-build/example/gettext
16K	./boost_output/share/boost-build/example/hello
16K	./boost_output/share/boost-build/example/try_compile
20K	./boost_output/share/boost-build/example/testing
20K	./boost_output/share/boost-build/example/qt/qt4/hello
12K	./boost_output/share/boost-build/example/qt/qt4/moccable-cpp
16K	./boost_output/share/boost-build/example/qt/qt4/uic
52K	./boost_output/share/boost-build/example/qt/qt4
20K	./boost_output/share/boost-build/example/qt/qt3/hello
12K	./boost_output/share/boost-build/example/qt/qt3/moccable-cpp
16K	./boost_output/share/boost-build/example/qt/qt3/uic
52K	./boost_output/share/boost-build/example/qt/qt3
112K	./boost_output/share/boost-build/example/qt
16K	./boost_output/share/boost-build/example/asciidoctor
20K	./boost_output/share/boost-build/example/python_modules
40K	./boost_output/share/boost-build/example/customization
12K	./boost_output/share/boost-build/example/libraries/app
8,0K	./boost_output/share/boost-build/example/libraries/util/foo/include
20K	./boost_output/share/boost-build/example/libraries/util/foo
24K	./boost_output/share/boost-build/example/libraries/util
44K	./boost_output/share/boost-build/example/libraries
8,0K	./boost_output/share/boost-build/example/pch/source
8,0K	./boost_output/share/boost-build/example/pch/include
24K	./boost_output/share/boost-build/example/pch
12K	./boost_output/share/boost-build/example/built_tool/core
12K	./boost_output/share/boost-build/example/built_tool/tblgen
36K	./boost_output/share/boost-build/example/built_tool
8,0K	./boost_output/share/boost-build/example/sass/include
28K	./boost_output/share/boost-build/example/sass
12K	./boost_output/share/boost-build/example/variant/libs
32K	./boost_output/share/boost-build/example/variant
20K	./boost_output/share/boost-build/example/generator
24K	./boost_output/share/boost-build/example/generate
548K	./boost_output/share/boost-build/example
56K	./boost_output/share/boost-build/src/contrib
16K	./boost_output/share/boost-build/src/tools/xsltproc
208K	./boost_output/share/boost-build/src/tools/features
120K	./boost_output/share/boost-build/src/tools/types
8,0K	./boost_output/share/boost-build/src/tools/doxygen
44K	./boost_output/share/boost-build/src/tools/generators
1,7M	./boost_output/share/boost-build/src/tools
56K	./boost_output/share/boost-build/src/kernel
268K	./boost_output/share/boost-build/src/util
12K	./boost_output/share/boost-build/src/options
760K	./boost_output/share/boost-build/src/build
2,9M	./boost_output/share/boost-build/src
3,4M	./boost_output/share/boost-build
3,4M	./boost_output/share
4,0M	./boost_output
656K	./doc/html
8,0K	./doc/src/pygments
8,0K	./doc/src/hljs/styles
28K	./doc/src/hljs
416K	./doc/src
1,1M	./doc
20K	./example/make
16K	./example/time
24K	./example/complex-testing
24K	./example/gettext
16K	./example/hello
16K	./example/try_compile
20K	./example/testing
20K	./example/qt/qt4/hello
12K	./example/qt/qt4/moccable-cpp
16K	./example/qt/qt4/uic
52K	./example/qt/qt4
20K	./example/qt/qt3/hello
12K	./example/qt/qt3/moccable-cpp
16K	./example/qt/qt3/uic
52K	./example/qt/qt3
112K	./example/qt
16K	./example/asciidoctor
20K	./example/python_modules
40K	./example/customization
12K	./example/libraries/app
8,0K	./example/libraries/util/foo/include
20K	./example/libraries/util/foo
24K	./example/libraries/util
44K	./example/libraries
8,0K	./example/pch/source
8,0K	./example/pch/include
24K	./example/pch
12K	./example/built_tool/core
12K	./example/built_tool/tblgen
36K	./example/built_tool
8,0K	./example/sass/include
28K	./example/sass
12K	./example/variant/libs
32K	./example/variant
20K	./example/generator
24K	./example/generate
548K	./example
12K	./bin
56K	./src/contrib
16K	./src/tools/xsltproc
208K	./src/tools/features
120K	./src/tools/types
8,0K	./src/tools/doxygen
44K	./src/tools/generators
1,7M	./src/tools
56K	./src/kernel
268K	./src/util
12K	./src/options
764K	./src/build
300K	./src/engine/bootstrap
236K	./src/engine/boehm_gc/include/private
432K	./src/engine/boehm_gc/include
476K	./src/engine/boehm_gc/doc
28K	./src/engine/boehm_gc/Mac_files
124K	./src/engine/boehm_gc/cord
72K	./src/engine/boehm_gc/tests
3,6M	./src/engine/boehm_gc
580K	./src/engine/bin.linuxx86_64
48K	./src/engine/modules
28K	./src/engine/debian
5,9M	./src/engine
8,7M	./src
17M	.

```
11. Найдите *топ10* самых "тяжёлых".
```sh
$ du -h -a | sort -r -h | head -n 10
8904	./src
5952	./src/engine
4052	./boost_output
3684	./src/engine/boehm_gc
3468	./boost_output/share
3464	./boost_output/share/boost-build
2908	./boost_output/share/boost-build/src
1908	./test
1712	./src/tools
```
```
Copyright (c) 2015-2021 The ISC Authors
```
