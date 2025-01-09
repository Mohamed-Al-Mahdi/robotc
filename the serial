import serial
import time

# Open the serial port
ser = serial.Serial(port='COM6', baudrate=9600, timeout=1)

# Wait for the Arduino to initialize
time.sleep(2)
data = [10, 20, 30, 40, 50, 60, 70, 80, 90, 100, 110, 120, 130, 140, 150, 160]

# Send the byte 10
ser.write(data)
print(f"Sent: {data}")

# Read the raw data from Arduino
received_data = ser.readline()  # Adjust size if necessary
print(f"Raw Received Data: {received_data.decode()}")



# Close the serial port
ser.close()
