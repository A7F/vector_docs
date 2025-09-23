[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetLocalTimeString.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » getLocalTimeString

# getLocalTimeString

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```c
void getLocalTimeString(char timeBuffer[]);
```

## Description

Copies a printed representation of the current date and time into the supplied character buffer. The format of the string is ddd mmm dd hh:mm:ss jjjj (e.g. "Fri Aug 21 15:22:24 1998").

**Note for use in distributed mode**

- This function always returns the local time of the user computer.

## Parameters

- **timeBuffer**: The buffer the string will be written in.  
  This buffer must be at least 26 characters long.

## Return Values

—

## Example

```c
...
char timeBuffer[64];

getLocalTimeString(timeBuffer);
// now timeBuffer contains for example. "Fri Aug 21 15:22:24 1998"
...
```

[getLocalTime](CAPLfunctionGetLocalTime.md)
