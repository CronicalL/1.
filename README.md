import os, sys

s=sys.argv[1]
d=sys.argv[2]

f1=os.open(s,os.O_RDONLY)
f2=os.open(d,os.O_CREAT|os.O_WRONLY|os.O_TRUNC,0o644)

while True:
    data=os.read(f1,1024)
    if not data:
        break
    os.write(f2,data)

os.close(f1)
os.close(f2)

print("File copied successfully")
