[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Selectors/CAPLSelectorCAN.md)

## Example Selector CAN (controller number)

```plaintext
message 0x100 msg = {dlc = 2, word(0) = 0x1234};

on key '1' {
  write("sende via CAN 1");
  msg.CAN = 1;
  output(msg);
}
on key '2' {
  write("sende via CAN 2");
  msg.CAN = 2;
  output(msg);
}
```

•  Technical References are only available in English
