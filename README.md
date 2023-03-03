#### hw1_binary_hex_converter

# 10進位制轉換為2進位和16進位




## 專案程式碼
* [程式碼github網址:](https://github.com/max1nehour/hw1_binary_hex_converter)

## 程式碼解析：

```py
#2023.03.02 max1n
#Decimal Converter

decimal = int(input("Decimal Number(0~255):"))
if decimal <= 255 and decimal >= 0:
  print("Decimal Number :",decimal)
else:
  print("ERROR: PLS enter numbers in the range of 0~255")
```

### 10進位->16進位
  * 首先利用字典將16進位制的轉換定義出來。
  
```py
#DECIMAL TO HEXADECIMAL#
print("(Converting to Hexadecimal Number....)")
hexa_dict = {10 :"a", 11:"b", 12:"c", 13:"d", 14:"e", 15: "f"}
```
  * 將進位制除以16，得出需進位幾次；其餘數即是個位數的數字。
```py
hexa1 = (int(decimal/16))
hexa2 = decimal%16 
```
  * 用if迴圈篩選，如果數字大於9，代表要轉換為英文字母，用dict.get從字典取回。
  * 若個位數為英文字母，直接列印字串；若為數字，則列印數字。
```py
#hexa1 convert
if hexa1 > 9 :
    hexa1 = hexa_dict.get(hexa1)
    
#hexa2 convert
if hexa2 > 9 :
    hexa2 = hexa_dict.get(hexa2)
    print("Hexadecimal Number :",hexa1,hexa2)

else:
    print("Hexadecimal Number :",hexa1*10+hexa2)
```

### 10進位->2進位

 * 定義n=8，因為最大不超過256；定義binary=0，以便遞加數字上去。
```py
#DECIMAL TO BINARY#
print("(Converting to Binary Number....)")
n = 8
binary = 0
```
 * 利用while迴圈，如果十進位數字落在2的n次方和n-1次方之間，則二進位制表示為10^(n-1)。
 * 承上，將十進位數字減去已經被轉換的部分，即2^(n-1)。
 * 並且使n=n-1，讓迴圈去檢測下一個n，直到0為止。
 * 最後印出binary，就是轉換完成的數字。

```py
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
