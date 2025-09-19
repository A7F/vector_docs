# Events of the CAN Controller

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE

These event procedures are called when the CAN controller's state or one of its error counters (errorCountRX, errorCountTX) changes. You would use this procedure to monitor the error counters (e.g. output of a warning) or to end the measurement or simulation.

Within these procedures the error counters of the CAN controller are made available by the **this** variable. They are accessed with the following syntax:

- `this.errorCountRX` (Receive error counter)
- `this.errorCountTX` (Transmit error counter)
- `this.can` (Assign the channel)

**Note**  
Error counters are supported and thus changed by the complete XL family.

**Example**

**on errorPassive procedure**

```plaintext
on errorPassive {
   ...
   write("CAN Controller is in errorPassive state")
   write(" errorCountTX = %d", this.errorCountTX);
   write(" errorCountRX = %d", this.errorCountRX);
};
```

**on busOff procedure**

```plaintext
on busOff
{
   int errRxCnt;
   int errTxCnt;
   int channel;
   double timestamp; // [seconds]

   timestamp = (double)timeNow() / (double)100000;
   channel = this.can;
   errRxCnt = this.errorCountRX;
   errTxCnt = this.errorCountTX;
   Write("Bus Off: time=%f channel=%d, errRxCnt=%d, errTxCnt=%d",
   timestamp, channel, errRxCnt, errTxCnt);

   resetCanEx(channel);
}
```
