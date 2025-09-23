[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Selectors/CAPLSelectorTIME.md)

## Example Selector TIME (time stamp of message in units of 10 microseconds)

In this example it is checked whether the message is received always in the same distance **sendDist**. At measurement start **lastTime** is set to zero.

```plaintext
const dword sendDist = 10000; // *10 us = 100ms

on message CP24TX {
  int delta;
  dword lastTime;
  delta = (this.TIME - lastTime - sendDist); // in 10 us
  lastTime = this.TIME;
  if (delta != 0)
  {
    write("deviation of send distance: %d us",10*delta);
  }
}
```

•  Technical References are only available in English
