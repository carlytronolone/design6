# Lab 3 - Python
## Files will be sotred here for Lab 3
# Procedure
#### Before starting the lab, I downloaded the required packages from the Lesson 3 folder on the IoT GitHub repository.

## Given Commands:
```
$ cd ~/iot
$ cd *3
$ python3 julian.py
$ python3 date_example.py
$ python3 datetime_example.py
$ python3 time_example.py
$ python3 sun.py 'New York'
$ python3 moon.py
$ python3 coordinates.py 'SC Williams Library'
$ python3 address.py '40.74480675, -74.02532862031404'
$ python3 cpu.py
$ python3 battery.py
$ python3 documentstats.py document.txt
```
#### The command 'python3' does not work, but the command 'python' works, so that is what I used for this lab.

# Results

### julian.py
```
carly@MSI MINGW32 ~/iot/lesson3 (master)
$ python julian.py
Calendar Date: 2023-05-04
Julian Date: 2460068.5
Modified Julian Date: 60068.0
```

### date_example.py
```
carly@MSI MINGW32 ~/iot/lesson3 (master)
$ python date_example.py
Date: 2023-05-04
Date: 05-04-23
Day of Week: Thursday
Month: May
Year: 2023
106 days after the first day of classes
0 days before the last day of classes
```

### datetime_example.py
```
carly@MSI MINGW32 ~/iot/lesson3 (master)
$ python datetime_example.py
2023-05-04 17:06:04.034609
2023-05-04 17:06:04.034608
2023-05-04 21:06:04.034608
1683234364.0346088
Thu May  4 17:06:04 2023
2023-05-04 17:06:04.034609
2023-05-04 21:06:04.034609
```

### time_example.py
```
$ python time_example.py
Thu May  4 17:06:30 2023
Thu May  4 17:06:40 2023
Thu May  4 17:06:50 2023
Thu May  4 17:07:00 2023
```

### sun.py 'New York'
```
carly@MSI MINGW32 ~/iot/lesson3 (master)
$ python sun.py 'New York'
Information for New York/USA

Timezone: US/Eastern
Latitude: 40.72; Longitude: -74.00

Dawn:    2023-05-04 05:20:51.847465-04:00
Sunrise: 2023-05-04 05:51:23.621438-04:00
Noon:    2023-05-04 12:52:51-04:00
Sunset:  2023-05-04 19:54:51.125457-04:00
Dusk:    2023-05-04 20:25:29.490557-04:00
```

### moon.py
```
carly@MSI MINGW32 ~/iot/lesson3 (master)
$ python moon.py
2023-05-04 Moon Phase: 12
2023-05-05 Moon Phase: 13
2023-05-06 Moon Phase: 14
2023-05-07 Moon Phase: 15
2023-05-08 Moon Phase: 16
2023-05-09 Moon Phase: 17
2023-05-10 Moon Phase: 18
2023-05-11 Moon Phase: 19
2023-05-12 Moon Phase: 20
2023-05-13 Moon Phase: 21
2023-05-14 Moon Phase: 22
2023-05-15 Moon Phase: 23
2023-05-16 Moon Phase: 24
2023-05-17 Moon Phase: 25
2023-05-18 Moon Phase: 26
2023-05-19 Moon Phase: 27
2023-05-20 Moon Phase: 0
2023-05-21 Moon Phase: 1
2023-05-22 Moon Phase: 2
2023-05-23 Moon Phase: 3
2023-05-24 Moon Phase: 4
2023-05-25 Moon Phase: 5
2023-05-26 Moon Phase: 6
2023-05-27 Moon Phase: 6
2023-05-28 Moon Phase: 7
2023-05-29 Moon Phase: 8
2023-05-30 Moon Phase: 9
2023-05-31 Moon Phase: 10
2023-06-01 Moon Phase: 11
2023-06-02 Moon Phase: 12
```

### coordinates.py 'SC Williams Library'
```
carly@MSI MINGW32 ~/iot/lesson3 (master)
$ python coordinates.py 'SC Williams Library'
Library Parking, Williams Lake, Cariboo Regional District, British Columbia, Canada
(52.130143399999994, -122.14187089155848)
```

### address.py '40.74480675, -74.02532862031404'
```
carly@MSI MINGW32 ~/iot/lesson3 (master)
$ python address.py '40.74480675, -74.02532862031404'
Samuel C. Williams Library, Field House Road, Hoboken, Hudson County, New Jersey, 07030, United States
(40.74480675, -74.02532861159351)
```

### cpu.py
```
carly@MSI MINGW32 ~/iot/lesson3 (master)
$ python cpu.py
The number of physical cores =  6
The number of logical CPUs =  12
The utilization per second as a percentage for each CPU
[0.0, 0.0, 0.0, 3.1, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
[6.2, 0.0, 3.1, 7.7, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 1.6]
[0.0, 0.0, 0.0, 7.8, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 1.6]
[0.0, 0.0, 0.0, 3.1, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
[3.1, 1.6, 4.7, 4.7, 1.6, 1.6, 1.6, 1.6, 1.6, 3.1, 9.4, 1.6]
[4.6, 0.0, 1.6, 3.1, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
[1.6, 0.0, 0.0, 4.7, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
[6.1, 0.0, 1.6, 4.7, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
[6.2, 3.1, 4.6, 6.2, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
Traceback (most recent call last):
  File "C:\Users\carly\iot\lesson3\cpu.py", line 15, in <module>
    cpu = psutil.cpu_percent(interval=1, percpu=True)
          ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "C:\Python311\Lib\site-packages\psutil\__init__.py", line 1764, in cpu_percent
    time.sleep(interval)
KeyboardInterrupt
```

### battery.py
```
carly@MSI MINGW32 ~/iot/lesson3 (master)
$ python battery.py
sbattery(percent=41, secsleft=<BatteryTime.POWER_TIME_UNLIMITED: -2>, power_plugged=True)
```

### documentstats.py document.txt
```
carly@MSI MINGW32 ~/iot/lesson3 (master)
$ python documentstats.py document.txt
Word Count: 1343
Top Ten Words: [('our', 26), ('their', 20), ('has', 20), ('he', 19), ('them', 15), ('these', 13), ('have', 11), ('we', 11), ('us', 11), ('people', 10)]
```

