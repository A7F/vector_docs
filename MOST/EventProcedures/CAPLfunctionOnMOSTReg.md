[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTReg.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostReg

# OnMostReg

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
OnMostReg();
```

## Description

OnMostReg() is called in response to read or write requests to registers of a MOST network interface chip.

The following functions are available for evaluating the event:

- `long mostRegChip()`
  - Returns the identifier of the chip whose registers are transported with this event (see [mostReadReg](../Functions/CAPLfunctionMOSTReadReg.md))
- `long mostRegOffset()`
  - Returns the start address of the register.
- `long mostRegDataLen()`
  - Returns the number of bytes transported with this event (maximum of 16).
- `void mostRegGetData(byte buffer[], long buffersize)`
  - The register values may be copied to a byte buffer with the function `mostRegGetData()`. It must be assured that the buffer has the specified size (buffersize). A maximum of 16 bytes are transported with the MostReg event.
- `long mostRegGetByteAbs(long chip, long adr)`
- `long mostRegGetWordAbs(long chip, long adr)`
  - Returns the contents of the register 'adr' in the chip 'chip'. If the MostReg event does not contain this register kMostParameterOutOfRange = -9 is returned.

For further information on this event see **Supplemental Information on Event Procedures for MOST Controller Events**.

## Parameters

—

## Return Values

—

## Example

```plaintext
OnMostReg()
{
  byte regData[16];
  long i, offset;
  // get register contents
  mostRegGetData(regData, 16);
  // get offset
  offset = mostRegOffset();
  // output register contents to Write Window
  write("OnMostReg() called for chip %d on channel %d", mostRegChip(), mostEventChannel());
  write("Map   Value");
  for(i = 0; i < mostRegDataLen(); i++)
  {
    write("%04X   %02X", offset + i, regData[i]);
  }
}
```

**Output in the Write Window**

```plaintext
OnMostReg() called for chip 1 on channel 1
Map   Value
0080  E2
0081  42
0082  16
...
```

[mostReadReg](../Functions/CAPLfunctionMOSTReadReg.md) • [mostWriteReg](../Functions/CAPLfunctionMOSTWriteReg.md)
