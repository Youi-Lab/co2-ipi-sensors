# co2-ipi-sensors
Rest service to store and retrieve  co2 IPICYT´s sensor data.

1. Upload sensor id data into the database:

curl -X POST "http://192.168.6.61:8083/sensky/greetsensorpar" -F "serial=IPI-SENSOR-00000100" -F "mac=00:00:00:01" -F "type=CO2" -F "units=PPB"

Alternatively you can use json data format:

curl -X POST http://192.168.6.61:8080/sensky/greetsensorjson -H 'Content-type:application/json' -d '{"serial":"IPI-SENSOR-00000100", "mac":"00:00:00:01", "type":"CO2", "units":"PPB"}'

2. Upload a sensor measurement:

curl -X POST http://192.168.6.61:8080/sensky/uploadmeasurement -F "serial=IPI-SENSOR-00000100" -F "datetime=123456" -F "val=100.1"

3. Retrieve sensor´s measurements into a json string:

curl -X POST http://192.168.6.61:8080/sensky/downloadjson -F "serial=IPI-SENSOR-00000100" 

