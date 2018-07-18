# I2C bus setting up and usage for linux on RPi device and respective clones
This library written in Go programming language intended to activate and interact with the I2C bus by reading and writing data.


Forked from
------------
https://github.com/d2r2/go-i2c.git 
with logging part removed.


Golang usage
------------

```go
func main() {
  // Create new connection to I2C bus on 2 line with address 0x27
  i2c, err := i2c.NewI2C(0x27, 2)
  if err != nil { log.Fatal(err) }
  // Free I2C connection on exit
  defer i2c.Close()
  ....
  // Here goes code specific for sending and reading data
  // to and from device connected via I2C bus, like:
  _, err := i2c.Write([]byte{0x1, 0xF3})
  if err != nil { log.Fatal(err) }
  ....
}
```
