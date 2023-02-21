# Die-Laboraufgabe-1.
# Лабораторная работа посвящена освоению консольного редактора в ОС Linux и его команд.

## Работа выполнена студентом МГТУ имени Н.Э. Баумана группы ИУ8-23 Рыбалтовским Денисом.

### 1. Чтобы скачать библиотеку *boost*, нужно: 
`wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz`

### 2. Для разархивации:
`tar xvzf boost_1_69_0.tar.gz`

### 3. Для подсчета файлов без "заглядывания" вглубь директории (В сумме 6 директорий и 12 файлов)
`tree -a -L 1`

### 4. Для подсчета всех файлов (вывод дерева) (В сумме 61191 файл)
`tree -a`

### 5.1. Для подсчета файлов *.cpp* (В сумме 13774 файла)
`find -name "*.cpp" -not -type d|wc -l`

### 5.2. Для подсчета файлов заголовочных (*.hpp*, *.h*) (В сумме 15208 файла)
`find -name "*.hpp" -o -name "*.h" -not -type d|wc -l`

### 5.3 Для подсчета остальных файлов (В сумме 32209 файла)
`find -not -name "*.cpp" -not -name "*.hpp" -not -name "*.h" -not -type d|wc -l`

### 6. Для получения пути до файла *any.hpp*
`find $(pwd) -name any.hpp`

### 7. Для получения списка файлов, в которых упоминается последовательность *boost::asio*
`grep  -rl 'boost::asio'`

### 8. Для компиляции библиотеки *boost*
`cd /home/luzio/boost_1_69_0/tools/build`
`sudo ./bootstrap.sh`
`./b2 install --prefix=test`

### 9. Для переноса скомпилированных библиотек в *boost-lib*
`mkdir ~/boost-lib`
`mv -i test /home/luzio/boost-lib`

### 10. Подсчитать размер каждого файла в директории
`du ah`

### 11. Для вывода десяти самых тяжелых файлов
`find . -xdev -type f -not -type d -print | xargs ls -lh | sort -k5,5 -h -r | head`
