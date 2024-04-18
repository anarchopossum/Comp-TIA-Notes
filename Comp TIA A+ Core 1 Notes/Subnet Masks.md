when configuring network masks it's important to know what are the requirements for the network.
For instance usually home networks use `192.168.0.xxx`. the `xxx` gives the open values that internet devices can connect to. This range is `0-255` made up for 8 bits. So for this example of using `192.168.0.xxx` we have a range of `255` network slots. Which in turns gives the value `12` for it's subnet mask. The reason the value is `24` is due to the 8 bits that each section of an IP address has.
So for `192.168.0.xxx` to find the subnet value we must count all the static bits in the IP range. These static bits are marked with a `1`. Now you might see that the third section of the IP is `0`. This shows the largest value accepted in the network within that section. since this sector is `0` we can't have anything pass the value of 0 in binary values. And since 0 is the last value in binary, there is no value we can have in the third section. 
Since 192, 168, and 0 in their respective sections are reserved. we can't modify them and therefore they are seen as `1`'s in subnet bit form.

| IP              | Subnet in bits                              | SubnetMask      | subnet value |
| --------------- | ------------------------------------------- | --------------- | ------------ |
| 192.168.0.xxx   | `11111111`.`11111111`.`11111111`.`00000000` | 255.255.255.0   | 24           |
| 192.168.xxx.xxx | `11111111`.`11111111`.`00000000`.`00000000` | 255.255.0.0     | 16           |
| 127.16.xxx.xxx  | `11111111`.`11110000`.`00000000`.`00000000` | 255.240.255.255 | 12           |


you might of also noticed that on `127.16.xxx.xxx` there is a `16`. this means that we can't modify anything after the 4th bit in the second section. this gives us a range of `00010000` to `00011111` or in decimal numbers 16-32.