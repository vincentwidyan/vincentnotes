---
title: "Konversi String ke Datetime"
summary: ""
date: 2023-09-07T16:04:48+02:00
lastmod: 2023-09-07T16:04:48+02:00
draft: false
weight: 810
toc: true
---
Seringkali ketika sedang melakukan _coding_ dengan Python, terdapat waktu yang direpresentasikan dengan tipe data string dan dibutuhkan konversi kembali ke nilai `datetime` dengan tipe data struct untuk tujuan tertentu. Di tutorial kali ini, akan dijelaskan mengenai cara konversi tipe data string ke `datetime` di Python.

## 1. Apa yang harus dilakukan sebelum mengikuti tutorial ini?
1. Pastikan kalian memiliki bahasa pemrograman Python yang terinstall di komputer kalian.
2. Pastikan Python sudah _include_ di path Comman Line kalian.

{{< callout context="tip" title="For Your Info?" icon="outline/rocket" >}}
Jika kalian tidak ingin menginstall Python di komputer, kalian bisa gunakan __Google Colaboratory__ dan _coding_ dimanapun di _browser_ kalian.
{{< /callout >}}

---
## 2. Bagaimana cara konversi String ke Datetime di Python?
Pada bagian ini, akan dijlelaskan mengenai cara konversi tipe data String ke Datetime di Python. Berikut adalah langkah-langkahnya.

### 2.1 Import Datetime Library
Pertama-tama, kita perlu melakukan _importing_ library `datetime`. Library biasanya sudah terinstall bersamaan dengan instalasi Python. Akan tetapi, jika nantinya terdapat error, maka dapat dilakukan instalasi manual dengan _command_ `pip install datetime`.

```py
# TODO : Import Datetime Libary
from datetime import datetime
```

### 2.2 Cara Konversi String ke Datetime menggunakan fungsi strptime()
Pada bagian ini, akan digunakan fungsi `strptime()` di _class_ `datetime` yang dapat melakukan konversi string ke datetime di Python. Karena tipe data String dapat bervariasi, di sini akan diberikan 4 (empat) contoh format string yang berbeda-beda yang akan dikonversi ke datetime. Lihat banner dibawah untuk melihat daftar lengkap format datetime.

{{< callout context="note" title="Note" icon="outline/info-circle" >}}
Semua format datetime dapat dilihat pada laman ...
{{< /callout >}}


#### 2.2.1 Contoh #1
Pada contoh 1, terdapat beberapa variable string yang dapat diformat sebagai `%d $B, %Y`
```python
date1 = '14 February, 2023'
date1_converted = datetime.strptime(date1,'%d %B, %Y')

print('1. Date #1 Before Converted : ',date1)
print('2. Type Date #1 Before Converted : ', type(date1))
print('3. Date #1 After Converted : ',date1_converted.date())
print('4. Type Date #1 After Converted : ', type(date1_converted))
```
Keluarannya adalah :
```text
1. Date #1 Before Converted : 14 February, 2023
2. Type Date #1 Before Converted : <class 'str'>
3. Date #1 After Converted : 2023-02-14
4. Type Date #1 After Converted : <class 'datetime.datetime'>
```
#### 2.2.2 Contoh #2
Pada contoh 2, terdapat beberapa variable string yang dapat diformat sebagai `%Y%m%d`
```Python
date2 = '20230214'
date2_converted = datetime.strptime(date2,'%Y%m%d')

print('1. Date #2 Before Converted : ',date2)
print('2. Type Date #2 Before Converted : ', type(date2))
print('3. Date #2 After Converted : ',date2_converted.date())
print('4. Type Date #2 After Converted : ', type(date2_converted))
```
Keluarannya adalah :
```text
1. Date #2 Before Converted : 20230214
2. Type Date #2 Before Converted : <class 'str'>
3. Date #2 After Converted : 2023-02-14
4. Type Date #2 After Converted : <class 'datetime.datetime'>
```
#### 2.2.3 Contoh #3
Di contoh 3, terdapat beberapa variable string yang dapat diformat sebagai  `%Y-%m-%d %H:%M:%S`
```python
date3 = '2023-02-14 13:44:55'
date3_converted = datetime.strptime(date3,'%Y-%m-%d %H:%M:%S')

print('1. Date #3 Before Converted : ',date3)
print('2. Type Date #3 Before Converted : ', type(date3))
print('3. Date #3 After Converted : ',date3_converted)
print('4. Type Date #3 After Converted : ', type(date3_converted))
```
Keluarannya adalah :
```text
1. Date #3 Before Converted : 2023-02-14 13:44:55
2. Type Date #3 Before Converted : <class 'str'>
3. Date #3 After Converted : 2023-02-14 13:44:55
4. Type Date #3 After Converted : <class 'datetime.datetime'>
```

#### 2.2.4 Contoh #4
Pada contoh 4, terdapat beberapa variable string yang dapat diformat sebagai `%A %d %b %H:%M:%S %Y`
```python
date4 = 'Tuesday 14 Feb 13:44:55 2023'
date4_converted = datetime.strptime(date4,'%A %d %b %H:%M:%S %Y')

print('1. Date #4 Before Converted : ',date4)
print('2. Type Date #4 Before Converted : ', type(date4))
print('3. Date #4 After Converted : ',date4_converted)
print('4. Type Date #4 After Converted : ', type(date4_converted))
```
Keluarannya adalah :
```text
1. Date #4 Before Converted : Tuesday 14 Feb 13:44:55 2023
2. Type Date #4 Before Converted : <class 'str'>
3. Date #4 After Converted : 2023-02-14 13:44:55
4. Type Date #4 After Converted : <class 'datetime.datetime'>
```

---
## 3. Kode
Berikut adalah kode lengkap pada tutorial ini tentang cara melakukan konversi String ke Datetime di Python.

```py {lineNos=True, title="tutorial.py"}
# TODO : Import Datetime Libary
from datetime import datetime

# TODO : Example 1
date1 = '14 February, 2023'
date1_converted = datetime.strptime(date1,'%d %B, %Y')

print('1. Date #1 Before Converted : ',date1)
print('2. Type Date #1 Before Converted : ', type(date1))
print('3. Date #1 After Converted : ',date1_converted.date())
print('4. Type Date #1 After Converted : ', type(date1_converted))
print('\n')

# TODO : Example 2
date2 = '20230214'
date2_converted = datetime.strptime(date2,'%Y%m%d')

print('1. Date #2 Before Converted : ',date2)
print('2. Type Date #2 Before Converted : ', type(date2))
print('3. Date #2 After Converted : ',date2_converted.date())
print('4. Type Date #2 After Converted : ', type(date2_converted))
print('\n')

# TODO : Example 3
date3 = '2023-02-14 13:44:55'
date3_converted = datetime.strptime(date3,'%Y-%m-%d %H:%M:%S')

print('1. Date #3 Before Converted : ',date3)
print('2. Type Date #3 Before Converted : ', type(date3))
print('3. Date #3 After Converted : ',date3_converted)
print('4. Type Date #3 After Converted : ', type(date3_converted))
print('\n')

# TODO : Example 4
date4 = 'Tuesday 14 Feb 13:44:55 2023'
date4_converted = datetime.strptime(date4,'%A %d %b %H:%M:%S %Y')

print('1. Date #4 Before Converted : ',date4)
print('2. Type Date #4 Before Converted : ', type(date4))
print('3. Date #4 After Converted : ',date4_converted)
print('4. Type Date #4 After Converted : ', type(date4_converted))

```
