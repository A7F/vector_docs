[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/EventProcedures/CAPLfunctionOnFRSymbol.md)

**CAPL Functions** » **FlexRay** » **on frSymbol**

# on frSymbol

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

`on frSymbol;`

## Description

The event procedure is called whenever a symbol (wake-up, CAS, MTS) is received.

## Parameters

—

## Selectors

- **Time (data type dword)**
  - The symbol time stamp that has been synchronized with the global time base in the computer (CAN hardware or computer system clock).
  - The time stamp must be used if time relations should be regarded with events from other sources. This time stamp is also output in the Trace Window when receiving a symbol.
  - Unit: 10 microseconds
  - **Write-protected!**

- **msgChannel**
  - Channel in the tool that the FlexRay CC determines.
  - **Write-protected!**

- **FR_ChannelMask**
  - Identifies the FlexRay channel of the CC. With 1 the symbol was received on channel A, with 2 on channel B.
  - **Write-protected!**

- **FR_Symbol**
  - Identifies the symbol type (data type: WORD)
  - **Write-protected!**

  Symbol Types:
  - 0: unknown
  - 1: CAS
  - 2: MTS
  - 3: Wakeup
  - 4: Undefined (used with VN interfaces in asynchronous mode)

  **Note:** Any wake-up symbol will only be received if the wake-up was initiated externally. Thus, if your CANoe DE product initiates a wake-up procedure, use the handler [on frPocState](CAPLfunctionOnFRPocState.md) to observe the wake-up pattern transmission!

- **FR_Length**
  - Indicates the length (data type: WORD) of the symbol in bit times.
  - **Write-protected!**

- **FR_Cycle**
  - Current FlexRay cycle number.
  - **Write-protected!**

## Example

The following program reacts on received symbols and prints them in the Write Window, Trace Window, and logging.

```c
variables
{
    const int cWriteTextSize = 512;
    char writeTxt[cWriteTextSize];
    const int cWriteTextSize2 = 40;
    char writeTxt2[cWriteTextSize2];
    const int writeSink_Trace = -3;
    const int writeSink_Logging = -2;
    const int writeSeverity_Information = 1;
}

on frSymbol
{
    getFRSymbolName(this.FR_Symbol, cWriteTextSize2, writeTxt2);
    snprintf(writeTxt, cWriteTextSize, "%10.6f: on FRSymbol %2d (%-32s) in cycle %3d on channel %2d with Mask %d, Length %d.", getTime(0), this.FR_Symbol, writeTxt2, this.FR_Cycle, (int)this.MsgChannel, this.FR_ChannelMask, this.FR_Length);
    myprint(writeTxt);
    output(this); // only required in Measurement Setup
}

float getTime (float time)
{
    return TimeNowNS() / 1000000000.0;
}

void myprint(char text[])
{
    write("%s", text);
    writeLineEx(writeSink_Trace, writeSeverity_Information, "%s", text);
    writeLineEx(writeSink_Logging, writeSeverity_Information, "%s", text);
}

int getFRSymbolName (word symbol, word nameSize, char name[])
{
    int r = -1;
    if (symbol == 0) {
        snprintf(name, nameSize, "Unknown");
        r = symbol;
    } else if (symbol == 1) {
        snprintf(name, nameSize, "CAS");
        r = symbol;
    } else if (symbol == 2) {
        snprintf(name, nameSize, "MTS");
        r = symbol;
    } else if (symbol == 3) {
        snprintf(name, nameSize, "Wakeup Symbol");
        r = symbol;
    } else {
        snprintf(name, nameSize, "Unspecified");
        r = -1;
    }
    return r;
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)