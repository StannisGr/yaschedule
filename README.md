# yaschedule

Lib for getting schedule data from Yandex Schedule API:
https://yandex.ru/dev/rasp/doc/concepts/about.html

<a target="new" href="https://pypi.python.org/pypi/yaschedule"><img border=0 src="https://img.shields.io/badge/python-3.9+-blue.svg?style=flat" alt="Python version"></a>
<a target="new" href="https://pypi.python.org/pypi/yaschedule"><img border=0 src="https://img.shields.io/pypi/v/yaschedule.svg?maxAge=60%" alt="PyPi version"></a>
## Quick Start
```python
from yaschedule.core import YaSchedule

#TO GET TOKEN - https://yandex.ru/dev/rasp/doc/concepts/access.html
TOKEN = 'some string' 

# init 
yaschedule = YaSchedule(TOKEN)

# get all stations info 
yaschedule.get_all_stations() # !!! The size of the returned data is about 40 MB

# get schedule between two stations
station_1 = 's9600366' # pulkovo
station_2 = 's9600213' # sheremetevo
yaschedule.get_stations_schedule(station_1, station_2)
```