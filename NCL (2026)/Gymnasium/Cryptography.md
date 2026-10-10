# Number Bases (Easy)
###### Our Analysts have obtained password dumps storing hacker passwords. After obtaining a few plaintext passwords, it appears that they are all simply encoded using different number bases.
### Tools used
* [Web-based Tools](https://rumkin.com/tools/)
* [Binary Hex Converter](https://www.binaryhexconverter.com/binary-to-ascii-text-converter)
* [Base64Decode](https://www.base64decode.org/)
* [CyberChef](https://cyberchef.cyberskyline.com/#recipe=From_Hex(%27Auto%27))
* [How Computers Store Data](https://trove.cyberskyline.com/8964d7b06a234684abffade642838140) 
### Questions and Solutions
1. 0x73636f7270696f6e : ```scorpion```
   * The text is encoded in hexadecimal
   * Text can be converted to ASCII by hand or by using an online tool (*Rapid Tables* or *Cyberchef*)
   * The *0X* is used to indicate that the value is a hexadecimal and should not be converted
2. c2NyaWJibGU= : ```scribble```
   * The text is encoded in base64
   * Can identify this by analyzing the range of character used in the message and recognizing that it falls within the range for base64 (A-Z, a-z, 0-9, +, /, and =)
   * Can be converted to ASCII by hand or by using an online tool (*Base64Decode* or *CyberChef*)
3. 01110011 01100101 01100011 01110101 01110010 01100101 01101100 01111001 : ```securely```
   * A this text is encoded in binary
   * Can be identified because there are only 1s and 0s in groups of 8
   * Can use and ASCII table or an online tool ([Binary to text](https://binarytotext.net/)
4. 01100010 01000111 00111001 01110011 01100010 01000111 01101100 01110111 01100010 00110011 01000001 00111101 : ```lollipop```
   * this text is double encoded
     * First with base64 and then with binary
   * to reverse the process, the message has to be converted from binary to ASCII, then base64
  
# Shift (Easy)

# Beep (Easy)

# French (Medium)

# XOR (Medium)

# Strings (Easy)

# RSA (Hard)
