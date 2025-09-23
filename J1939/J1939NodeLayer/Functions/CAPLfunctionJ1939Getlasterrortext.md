[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939Getlasterrortext.md)

# J1939GetLastErrorText

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 NL](../CAPLfunctionsJ1939NLOverview.md) » J1939GetLastErrorText

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword J1939GetLastErrorText( dword bufferSize, char buffer[] );
```

## Description

This function gets the description of the last occurred error.

## Parameters

- **bufferSize**: size of buffer for error description
- **buffer**: contains the error description

## Return Values

Number of characters that are copied to `buffer`

## Example

```c
dword size = 100;
char errText[size];

J1939GetLastErrorText(size, errText);
```
