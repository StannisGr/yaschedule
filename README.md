# yaschedule

Lib for getting schedule data from Yandex.Rasp API:
https://yandex.ru/dev/rasp/doc/concepts/about.html

<a target="new" href="https://pypi.python.org/pypi/yaschedule"><img border=0 src="https://img.shields.io/badge/python-3.9+-blue.svg?style=flat" alt="Python version"></a>
<a target="new" href="https://pypi.python.org/pypi/yaschedule"><img border=0 src="https://img.shields.io/pypi/v/yaschedule.svg?maxAge=60%" alt="PyPi version"></a>
## Quick Start
```python
from yaschedule.core import YaSchedule

# TO GET TOKEN - https://yandex.ru/dev/rasp/doc/concepts/access.html
TOKEN = 'some string' 

# init 
yaschedule = YaSchedule(TOKEN)

# get all stations in json 
yaschedule.get_all_stations() # !!! The size of the returned data is about 40 MB

# cities and stations codes from yaschedule.get_all_stations()
city_1 = 'c213' # Moscow
city_2 = 'c2' # Saint-Petersburg
station_1 = 's9600366' # Pulkovo
station_2 = 's9600213' # Sheremetevo

# get schedule between two stations
yaschedule.get_schedule(from_station=station_1, to_station=station_2)

# get schedule between two cities
yaschedule.get_schedule(from_station=city_1, to_station=city_2)

# get schedule between city and station
yaschedule.get_schedule(from_station=city_1, to_station=station_1)

# u can also specify other request params of request
# transport_type by default get all transport types
yaschedule.get_schedule(from_station=city_1, to_station=city_2, transport_types='train')
yaschedule.get_schedule(from_station=city_1, to_station=city_2, transport_types='plane')
# transfers by default: False
yaschedule.get_schedule(from_station=city_1, to_station=city_2, transfers=True)
```
