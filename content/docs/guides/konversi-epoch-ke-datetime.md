---
title: Konversi Epoch ke Time Format
summary: ""
date: 2023-09-07T16:04:48+02:00
lastmod: 2023-09-07T16:04:48+02:00
draft: false
weight: 812
toc: true
---
## 1. Apa itu Epoch Time?
Epoch Time adalah standardisasi representasi waktu yang digunakan di Unix timestamp yang setiap digit nomornya merepresentasikan setiap detik dari 1 Januari 1970. Epoch time mengandung 10 digit dan dapat merepresentasikan semua zona waktu dengan menambah 3600 detik setiap zonanya. Karena kegunaan standarnya digunakan di dalam database atau log, kita akan seringkali bersentuhan dengan Epoch format ini untuk melakukan konversi ke standar waktu biasa atau sebaliknya.

## 2. Tutorial
Di dalam tutorial ini, akan dijelaskan cara melakukan konversi Epoch ke `datetime` dan sebaliknya.

### 2.1 Import Datetime Library
Pertama-tama kita perlu melakukan import library `datetime` sehinga kita dapat mengguakan _class_ `datetime` dan fungsi-fungsinya.

```python
# TODO : Import datetime library
from datetime import datetime
```

### 2.2 Cara konversi Epoch ke Datetime?
Jika kita diberikan sebuah Epoch standar time, kita dapat menggunakan fungsi `fromtimestamp()` dan mengkonversi ke standar `datetime`. Kode di bawah ini menampilikan konversi Epoch time di sebuah variable dengan nama `currentTime`.

```python
# TODO : Convert Epoch to Datetime
epochTime = 1676106378
currentTime = datetime.fromtimestamp(epochTime)
print('1. Current Epoch to Datetime : ',currentTime)
```
Keluarannya adalah :
```text
1. Current Epoch to Datetime : 2023-02-11 09:06:18
```

### 2.2 Cara Konversi Datetime ke Epoch?
Jika kita diberikan sebuah `dateime` standar time dan kita ingin mengkonversi ke Epoch, kita dapat menggunakan kode di bawah ini. Berikut kode untuk mendapatkan `datetime` hari ini dengan `datetime.today()` library kemudian dikonversi menggunakan fungsi  `timestamp()`.

```python
# TODO : Convert Datetime to Epocj
todaydate = datetime.today()
epoch_convert = todaydate.timestamp()
print('2. Current Full Epoch Timestamp : ',epoch_convert)
print('3. Current Only Date Epoch Timestamp : ',str(epoch_convert)[0:10])
```
Keluarannya adalah :
```text
2. Current Full Epoch Timestamp : 1676365612.225573
3. Current Only Date Epoch Timestamp : 1676365612
```
---
## 3. Kode
Berikut kode untuk melakukan konversi Epoch ke `datetime` dan konversi `datetime` ke Epoch di Python.

```python
# TODO : Import datetime library
from datetime import datetime

# TODO : Convert Epoch to Datetime
epochTime = 1676106378
currentTime = datetime.fromtimestamp(epochTime)
print('1. Current Epoch to Datetime : ',currentTime

# TODO : Convert Datetime to Epoch
todaydate = datetime.today()
epoch_convert = todaydate.timestamp()
print('2. Current Full Epoch Timestamp : ',epoch_convert)
print('3. Current Only Date Epoch Timestamp : ',str(epoch_convert)[0:10])
```
