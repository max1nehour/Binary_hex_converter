# hw1_binary_hex_converter

##<10進位制轉換為2進位和16進位>
  
```py
#2023.03.02 max1n
#Decimal Converter

decimal = int(input("Decimal Number(0~255):"))
if decimal <= 255 and decimal >= 0:
  print("Decimal Number :",decimal)
else:
  print("ERROR: PLS enter numbers in the range of 0~255")


#DECIMAL TO HEXADECIMAL#
print("(Converting to Hexadecimal Number....)")
hexa_dict = {10 :"a", 11:"b", 12:"c", 13:"d", 14:"e", 15: "f"}

hexa1 = (int(decimal/16))
hexa2 = decimal%16 

#hexa1 CONVERT
if hexa1 > 9 :
    hexa1 = hexa_dict.get(hexa1)
#hexa2 CONVERT
if hexa2 > 9 :
    hexa2 = hexa_dict.get(hexa2)
    print("Hexadecimal Number :",hexa1,hexa2)

else:
    print("Hexadecimal Number :",hexa1*10+hexa2)


#DECIMAL TO BINARY#
print("(Converting to Binary Number....)")

n = 8
binary = 0

while n>=0 :
  if decimal < 2**n and decimal >= 2**(n-1):
    binary += 10**(n-1)
    decimal -= 2**(n-1)
    n-=1 
  else:
    n-=1

print("Binary Number :",binary)

#end
```
