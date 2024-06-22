# AutomobileAnalytics

Schema:

1. Vehicles Table
Schema:
vehicle_id: INT, Primary Key, Unique identifier for each vehicle
make: VARCHAR(50), Brand of the vehicle
model: VARCHAR(50), Model of the vehicle
year: INT, Year of manufacture
battery_capacity: FLOAT, Capacity of the battery in kWh
mileage: FLOAT, Total miles driven
Example:
vehicle_id	make	model	year	battery_capacity	mileage
1	Tesla	Model S	2020	100	15000
2	Nissan	Leaf	2019	40	22000
3	Chevrolet	Bolt EV	2021	66	8000

2. Sensors Data Table
Schema:
sensor_id: INT, Primary Key, Unique identifier for each sensor reading
vehicle_id: INT, Foreign Key, References Vehicles(vehicle_id)
timestamp: DATETIME, Timestamp of the sensor reading
battery_health: FLOAT, Health percentage of the battery
motor_temperature: FLOAT, Temperature of the motor in degrees Celsius
tire_pressure: FLOAT, Tire pressure in PSI
odometer_reading: FLOAT, Current odometer reading in miles
Example:
sensor_id	vehicle_id	timestamp	battery_health	motor_temperature	tire_pressure	odometer_reading
101	1	2023-06-01 08:00:00	95	75	32	15000
102	2	2023-06-01 08:05:00	85	80	30	22000
103	3	2023-06-01 08:10:00	90	70	35	8000

3. Maintenance Logs Table
Schema:
maintenance_id: INT, Primary Key, Unique identifier for each maintenance record
vehicle_id: INT, Foreign Key, References Vehicles(vehicle_id)
maintenance_date: DATE, Date of the maintenance
maintenance_type: VARCHAR(100), Type of maintenance performed
description: TEXT, Detailed description of the maintenance work
cost: FLOAT, Cost of the maintenance
Example:
maintenance_id	vehicle_id	maintenance_date	maintenance_type	description	cost
201	1	2023-05-15	Battery Check	Routine battery health check	150
202	2	2023-05-20	Tire Replacement	Replaced front tires	300
203	3	2023-06-01	Motor Service	Motor temperature issue	500
   
5. Predictive Maintenance Table
Schema:
prediction_id: INT, Primary Key, Unique identifier for each prediction
vehicle_id: INT, Foreign Key, References Vehicles(vehicle_id)
prediction_date: DATE, Date when the prediction was made
predicted_failure_date: DATE, Predicted date of component failure
component: VARCHAR(100), Component predicted to fail
failure_probability: FLOAT, Probability of failure

Example:
prediction_id	vehicle_id	prediction_date	predicted_failure_date	component	failure_probability
301	1	2023-06-01	2023-08-01	Battery	0.85
302	2	2023-06-01	2023-09-15	Tire	0.70
303	3	2023-06-01	2023-07-20	Motor	0.90
