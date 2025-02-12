---
title: "Konversi Datetime ke String"
summary: ""
date: 2023-09-07T16:04:48+02:00
lastmod: 2023-09-07T16:04:48+02:00
draft: false
weight: 811
toc: true
---

Saat coding dengan Python, terkadang kita akan membutuhkan sebuah nilai Datetime/Timestamp yang perlu disimpan dalam tipe data `string`. Selain mungkin kita akan menggunakannya untuk debugging/print, kita dapat mengguanak skema ini untuk menamai file output kita. Di tutorial kali ini, akan dijelaskan langkah-langkah untuk melakukan konversi tipe data Datetime ke String di Python.

## 1.  Apa yang harus dilakukan sebelum mengikuti tutorial ini?
1. Pastikan kalian memiliki bahasa pemrograman Python yang terinstall di komputer kalian.
2. Pastikan Python sudah _include_ di path Comman Line kalian.

{{< callout context="tip" title="For Your Info?" icon="outline/rocket" >}}
Jika kalian tidak ingin menginstall Python di komputer, kalian bisa gunakan __Google Colaboratory__ dan _coding_ dimanapun di _browser_ kalian.
{{< /callout >}}

## 2. Cara Konversi Datetime ke String di Python
Pada part ini, akan dijleaskan mengenai langkah-langkah melakukan konversi tipe data datetime ke tipe data string di Python. Datetime yang digunakan di Python akan memiliki tipe data `struct`. Bagi beberapa orang, tipe data `struct` terbilang susah untuk diubah bentuk/digunakan pada beberapa skenario. Alih-alih tetap menggunakannya, biasanya tipe data ini akan lebih mudah jika dikonversi ke dalam tipe data `string`. Di bawah ini adalah langkah-langkah untuk mengkonversikan datetime dengan tipe data `struct` ke tipe data `string` :

### 2.1 Import Datetime Library
Pertama-tama, kita perlu untuk melakukan import _library_ Datetime. Biasanya, _library_ ini sudah terinstall saat kita melakukan instalasi Python. Jika tidak, kalian bisa menggunakan _command_ `pip install datetime` di command line/terminal komputer kalian. Akan tetapi, jika kalian memilih Google Colaboratory, kalian tidak perlu kesusahan untuk melakukan instalasi ini. Kode di bawah ini diperlukan untuk melakukan import _library_ `datetime`.

```python
# TODO : Import Datetime Library
from datetime import datetime
```

### 2.2 Me-_assign_ ke sebuah Variable
Setelah melakukan import, nilai datetime tersebut perlu di-_assign_ ke sebuah variable karena kemungkinan besar nantinya nilai tersebut akan digunakan beberapa kali. Dengan kode di bawah ini, kita meng-_assign_ nilai `datetime` tersebut ke variable dengan nama `datetoday` yang didapat menggunakan fungsi `datetime.today()`.

```python
# TODO : Assign to a Variable
datetoday = datetime.today()
```

### 2.3 Menggunakan fungsi `strftime()` di Datetime Class
Disinilah fungsi yang ditunggu-tunggu. Fungsi `strftime()` dapat melakukan konversi `datetime` dengan tipe data `struct` ke tipe data `string` di Python. Terdapat pula beberapa format untuk merepresentasikan `datetime` tersebut.

```python
# TODO : Assign to Variable with varying Format
fulltimestamp = datetoday.strftime("%Y-%m-%d %H:%M:%S")
dateformat = datetoday.strftime("%d/%m/%y")
otherdateformat = datetoday.strftime("%A, %B %d %Y")
time24hour = datetoday.strftime("%H:%M:%S")
time12hour = datetoday.strftime("%I:%M:%S %p")

# TODO : Print each variable format
print('1. Full Timestamp Format :', fulltimestamp)
print('2. Date Format :', dateformat)
print('3. Other Date Format :', otherdateformat)
print('4. 24-Hour Format :', time24hour)
print('5. 12-Hour Format :', time12hour)
```
Keluarannya adalah :
```text
1. Full Timestamp Format : 2023-02-11 09:53:20
2. Date Format : 11/02/23
3. Other Date Format : Saturday, February 11 2023
4. 24-Hour Format : 09:53:20
5. 12-Hour Format : 09:53:20 AM
```

### 2.4 Beberapa Format Code
Berikut merupakan daftar format `strftime` di Python yang biasanya digunakan.

| __Format__ | __Description__                        | __Result__              |
|--------|------------------------------------|---------------------|
| %d     | Menampilkan hari sebagai zero-padded desimal    | 01,02…,31           |
| %A     | Menampilkan weekday lengkap             | Sunday, Monday,…    |
| %m     | Menampilkan bulan sebagai zero-padded desimal  | 01,02…,12           |
| %B     | Menampilakn nama bulan               | January, February,… |
| %y     | Menampilkan tahun sebagai zero-padded decimal   | 97,98,…,07,13,23    |
| %Y     | Menampilkan nomor tahun lengkap              | 1998,2010,…,2023    |
| %H     | Menampilkan 24-Hour Format                | 01,02,…,23          |
| %I     | Menampilkan 12-Hour Format                | 01,02,…,12          |
| %M     | Menampilkan menit sebagai zero-padded desimal | 01,02,…,59          |
| %S     | Menampilkan detik sebagai zero-padded desimal | 01,02,…,59          |
| %p     | Menampilkan tanda 12-Hour              | AM,PM               |

---
## 3. Kode
Berikut merupakan kode lengkap cara melakukan konvert nilai `datetime` ke tipe data `string` di Python.

```py {lineNos=True, title="tutorial.py"}
# TODO : Import Datetime Library
from datetime import datetime

# TODO : Assign to a Variable
datetoday = datetime.today()

# TODO : Assign to Variable with varying Format
fulltimestamp = datetoday.strftime("%Y-%m-%d %H:%M:%S")
dateformat = datetoday.strftime("%d/%m/%y")
otherdateformat = datetoday.strftime("%A, %B %d %Y")
time24hour = datetoday.strftime("%H:%M:%S")
time12hour = datetoday.strftime("%I:%M:%S %p")

# TODO : Print each variable format
print('1. Full Timestamp Format :', fulltimestamp)
print('2. Date Format :', dateformat)
print('3. Other Date Format :', otherdateformat)
print('4. 24-Hour Format :', time24hour)
print('5. 12-Hour Format :', time12hour)
```
