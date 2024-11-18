# IoT

 http://localhost:1880/ui/ - For the Dashboards of Node Red
 hivemq.com/demos/websocket-client/  - HiveMQ 
                  -         -
 
GENERATING RANDOM VALUES:-
msg.payload=Math.floor(Math.random()*(High - Low + 1)) + low;
return msg;
                  -         -                  -         -
                  
Code to Generate Random Heart Rate and Blood Pressure Values:-
function getRandomInt(min, max) {
return Math.floor(Math.random() * (max - min + 1)) + min;
}
var heartRate = getRandomInt(60, 100);
var bloodPressure = getRandomInt(90, 140) + '/' + getRandomInt(60, 90);
msg.payload = {
heartRate: heartRate,
bloodPressure: bloodPressure
};
return msg;

                  -         -                  -         -
SMTP:
To:-.....................
Server:- smtp.gmail.com
Port:- 465
Auth Type:- Basic
Userid:- emailId
Password:- App Password
                  -         -                  -         -
                  
CODE to check the Conditions:-
function randomWeight() {
return Math.floor(Math.random() * 101); // Random weight between 0 and 100 kg
}
function randomTemperature() {
return Math.floor(Math.random() * 16) + 30; // Random temperature between 30°C and 45°C
}
let seats = [
{ seat: 1, weight: randomWeight(), temperature: randomTemperature() },
 { seat: 2, weight: randomWeight(), temperature: randomTemperature() },
{ seat: 3, weight: randomWeight(), temperature: randomTemperature() },
{ seat: 4, weight: randomWeight(), temperature: randomTemperature() },
{ seat: 5, weight: randomWeight(), temperature: randomTemperature() }
];
let fanStatus = false;
seats.forEach(seat => {
if (seat.weight > 20 && seat.temperature >= 34 && seat.temperature <= 42) {
seat.status = "Occupied";
fanStatus = true; // If any seat is occupied, the fan should be on
} else {
seat.status = "Vacant";
}
});
msg.seats = seats;
msg.fanStatus = fanStatus ? "ON" : "OFF";
return msg;
                  -         -                  -         -
                  
This flow will check and return the available parking slot 
Function Code
const now = new Date().toISOString();
msg.payload = {
 AvailableParkingSlot: Math.floor(Math.random() * 100) + 1, 
 vehicleId: msg.payload.vehicleId,
 vehicleType: msg.payload.vehicleType,
 timestamp: now
};
if (!msg.payload.vehicleId || !msg.payload.vehicleType) {
 node.error("Invalid payload: Missing vehicleId or vehicleType", msg);
 return null; // Stop processing
}
return msg;
                  -         -                  -         -
                  
