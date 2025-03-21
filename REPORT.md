<!--- Шаблон к оформлению домашней работы -->

## Домашнее задание

**Студентки группы ИУ8-22**

**Ивановой Влады**


1. Скачайте библиотеку *boost* с помощью утилиты **wget**. Адрес для скачивания `https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz`.
```sh
$ wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
Resolving sourceforge.net (sourceforge.net)... 104.18.12.149, 104.18.13.149, 2606:4700::6812:c95, ...
Connecting to sourceforge.net (sourceforge.net)|104.18.12.149|:443... connected.
HTTP request sent, awaiting response... 301 Moved Permanently
Location: https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/ [following]
--2025-02-28 02:58:35--  https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/
Reusing existing connection to sourceforge.net:443.
HTTP request sent, awaiting response... 301 Moved Permanently
Location: https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/download [following]
--2025-02-28 02:58:35--  https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/download
Reusing existing connection to sourceforge.net:443.
HTTP request sent, awaiting response... 302 Found
Location: https://downloads.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?ts=gAAAAABnwWysqnR86m6AViLwmzLbgLpyGPk0KvmRkY5yTJL8zxChk482KYFQBQ9t8Rr26ZsbMGMoOdDD-sBnayQOwugcx2366g%3D%3D&use_mirror=deac-fra&r= [following]
--2025-02-28 02:58:35--  https://downloads.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?ts=gAAAAABnwWysqnR86m6AViLwmzLbgLpyGPk0KvmRkY5yTJL8zxChk482KYFQBQ9t8Rr26ZsbMGMoOdDD-sBnayQOwugcx2366g%3D%3D&use_mirror=deac-fra&r=
Resolving downloads.sourceforge.net (downloads.sourceforge.net)... 104.18.12.149, 104.18.13.149, 2606:4700::6812:d95, ...
Connecting to downloads.sourceforge.net (downloads.sourceforge.net)|104.18.12.149|:443... connected.
HTTP request sent, awaiting response... 302 Found
Location: https://deac-fra.dl.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?viasf=1 [following]
--2025-02-28 02:58:36--  https://deac-fra.dl.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?viasf=1
Resolving deac-fra.dl.sourceforge.net (deac-fra.dl.sourceforge.net)... 37.203.33.33
Connecting to deac-fra.dl.sourceforge.net (deac-fra.dl.sourceforge.net)|37.203.33.33|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 111710205 (107M) [application/x-gzip]
Saving to: ‘boost_1_69_0.tar.gz’

boost_1_69_0.tar.gz       100%[===================================>] 106.53M  7.05MB/s    in 19s     
                                                                                                      
2025-02-28 02:58:56 (5.67 MB/s) - ‘boost_1_69_0.tar.gz’ saved [111710205/111710205]

```
2. Разархивируйте скаченный файл в директорию `~/boost_1_69_0`
```sh
$ tar -xf boost_1_69_0.tar.gzq
```
3. Подсчитайте количество файлов в директории `~/boost_1_69_0` **не включая** вложенные директории.
```sh
$ find boost_1_69_0 -maxdepth 1 -type f | wc -l
12
```
4. Подсчитайте количество файлов в директории `~/boost_1_69_0` **включая** вложенные директории.
```sh
$ find boost_1_69_0 -type f | wc -l
61191
```
5. Подсчитайте количество заголовочных файлов, файлов с расширением `.cpp`, сколько остальных файлов (не заголовочных и не `.cpp`).
```sh
$ find boost_1_69_0 -type f -name "*.hpp" -o -name "*.cpp" -o -name "*.h" | wc -l
28982
$ find boost_1_69_0 -type f ! -name "*.hpp" ! -name "*.cpp" ! -name "*.h" | wc -l
32209
```
6. Найдите полный пусть до файла `any.hpp` внутри библиотеки *boost*.
```sh
$ find -name "any.hpp" 
./boost_1_69_0/boost/type_erasure/any.hpp
./boost_1_69_0/boost/proto/detail/any.hpp
./boost_1_69_0/boost/xpressive/detail/utility/any.hpp
./boost_1_69_0/boost/hana/fwd/any.hpp
./boost_1_69_0/boost/hana/any.hpp
./boost_1_69_0/boost/spirit/home/support/algorithm/any.hpp
./boost_1_69_0/boost/any.hpp
./boost_1_69_0/boost/fusion/include/any.hpp
./boost_1_69_0/boost/fusion/algorithm/query/any.hpp
./boost_1_69_0/boost/fusion/algorithm/query/detail/any.hpp
```
7. Выведите в консоль все файлы, где упоминается последовательность `boost::asio`.
```sh
$ grep -r "boost::asio" boost_1_69_0 >number7
```
[number7](https://github.com/Dayinu/lab01/blob/main/number7.txt)

8. Скомпилирутйе *boost*. Можно воспользоваться [инструкцией](https://www.boost.org/doc/libs/1_61_0/more/getting_started/unix-variants.html#or-build-custom-binaries) или [ссылкой](https://codeyarns.com/2017/01/24/how-to-build-boost-on-linux/).
```sh
$ ./bootstrap.sh
$ ./b2 >number8
$ sudo ./b2 install >number8_2
$ ./b2 install -j 8 >number8_3

Building Boost.Build engine with toolset gcc... tools/build/src/engine/bin.linuxx86_64/b2
Detecting Python version... 3.13
Detecting Python root... /usr
Unicode/ICU support for Boost.Regex?... /usr
Generating Boost.Build configuration in project-config.jam...

Bootstrapping is done. To build, run:

    ./b2
    
To adjust configuration, edit 'project-config.jam'.
Further information:

   - Command line help:
     ./b2 --help
     
   - Getting started guide: 
     http://www.boost.org/more/getting_started/unix-variants.html
     
   - Boost.Build documentation:
     http://www.boost.org/build/doc/html/index.html
```
Вывод каждой из достаточно больших команд:
[number8](https://github.com/Dayinu/lab01/blob/main/number8.txt)
[number8_2](https://github.com/Dayinu/lab01/blob/main/number8_2.txt)
[number8_3](https://github.com/Dayinu/lab01/blob/main/number8_3.txt)

9. Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию `~/boost-libs`.
```sh
$ mkdir ~/boost-libs
$ cp ~/boost_1_69_0/stage/lib/*.a ~/boost-libs/
```
10. Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.
```sh
$ du -s *                              
4       libboost_atomic.a
232     libboost_chrono.a
152     libboost_container.a
20      libboost_context.a
320     libboost_contract.a
152     libboost_date_time.a
4       libboost_exception.a
232     libboost_fiber.a
404     libboost_filesystem.a
828     libboost_graph.a
344     libboost_iostreams.a
208     libboost_prg_exec_monitor.a
1520    libboost_program_options.a
80      libboost_random.a
3148    libboost_regex.a
1172    libboost_serialization.a
36      libboost_stacktrace_addr2line.a
20      libboost_stacktrace_backtrace.a
16      libboost_stacktrace_basic.a
4       libboost_stacktrace_noop.a
4       libboost_system.a
2244    libboost_test_exec_monitor.a
52      libboost_timer.a
2228    libboost_unit_test_framework.a
4540    libboost_wave.a
776     libboost_wserialization.a

```
11. Найдите *топ10* самых "тяжёлых".
```sh
$ du -s * | sort -rh | head -10 
4540    libboost_wave.a
3148    libboost_regex.a
2244    libboost_test_exec_monitor.a
2228    libboost_unit_test_framework.a
1520    libboost_program_options.a
1172    libboost_serialization.a
828     libboost_graph.a
776     libboost_wserialization.a
404     libboost_filesystem.a
344     libboost_iostreams.a

```
