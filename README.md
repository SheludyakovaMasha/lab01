# lab01
1. Скачайте библиотеку boost с помощью утилиты wget
$ wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
2. Разархивируйте скаченный файл в директорию ~/boost_1_69_0

$ tar -xvf boost_1_69_0.tar.gz
![image](https://github.com/SheludyakovaMasha/lab01/assets/113375463/6299d868-9349-46bd-82c8-664a0408738d)
3. Подсчитайте количество файлов в директории ~/boost_1_69_0 не включая вложенные директории

$ ls -l | grep "^-" | wc -l

![image](https://github.com/SheludyakovaMasha/lab01/assets/113375463/80fa49b4-41f5-43e7-9e1f-93ae77828e79)

4. Подсчитайте количество файлов в директории ~/boost_1_69_0 включая вложенные директории

$ ls -l -R | wc -l

![image](https://github.com/SheludyakovaMasha/lab01/assets/113375463/12bd118b-89f3-4e6c-9d7d-5fa621d2a305)

5. Подсчитайте количество заголовочных файлов, файлов с расширением .cpp, сколько остальных файлов (не заголовочных и не .cpp)

$ ls -l -R | grep -c *.hpp
$ ls -l -R | grep -c *.cpp
$ ls -l -R | grep -v *.hpp | grep -v *.cpp | grep -v 'итого' | wc -l

![image](https://github.com/SheludyakovaMasha/lab01/assets/113375463/1d7df7c1-8f0d-4aa6-a276-b5eb18b1a193)


6. Найдите полный пусть до файла any.hpp внутри библиотеки boost

$ find $PWD -type f -name any.hpp

![image](https://github.com/SheludyakovaMasha/lab01/assets/113375463/173f9662-4268-4e15-8425-5568323b6aba)


7. Выведите в консоль все файлы, где упоминается последовательность boost::asio

$ grep -R -l "boost::asio"

![image](https://github.com/SheludyakovaMasha/lab01/assets/113375463/72e9aeb6-f43a-4243-8a66-1e17b0030f0e)


8. Скомпилирутйе boost

$ ./bootstrap.sh --prefix=boost_output
$ ./b2 install

![image](https://github.com/SheludyakovaMasha/lab01/assets/113375463/763b0485-226d-44a6-a9bc-fdd33014eed1)



9. Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию ~/boost-libs

$ mv ~/boost_1_69_0/boost_output/lib ~/boost-libs

![image](https://github.com/SheludyakovaMasha/lab01/assets/113375463/5ac5f2f8-41ed-45ad-80ae-b1f38e7c9521)


10. Подсчитайте сколько занимает дискового пространства каждый файл в этой директории

$ du -h -a 

![image](https://github.com/SheludyakovaMasha/lab01/assets/113375463/049be2e4-9287-4fb1-b7ae-2833f4902651)


11. Найдите топ 10 самых "тяжёлых"

![image](https://github.com/SheludyakovaMasha/lab01/assets/113375463/e7239b4d-b16a-408a-b6af-0d1cb05ad662)
