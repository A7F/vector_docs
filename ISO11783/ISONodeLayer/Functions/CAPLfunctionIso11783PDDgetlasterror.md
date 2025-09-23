[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783PDDgetlasterror.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783PDDGetLastError

# Iso11783PDDGetLastError

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783PDDGetLastError();
```

## Description

Supplies the last error code.

## Parameters

—

## Return Values

Error code of the function most recently executed

## Example

```plaintext
char text[256];

value = Iso11783PDDGetValue(ecuHandle, PD::AppRateSignal, 0);

if (Iso11783PDDGetLastError() != 0) {
    Iso11783PDDGetLastErrorText(elCount(text), text);
    write("ERROR: %s", text);
}
```
