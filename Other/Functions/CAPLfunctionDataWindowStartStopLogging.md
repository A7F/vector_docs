[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionDataWindowStartStopLogging.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » dataWindowStartLogging, dataWindowStopLogging

# dataWindowStartLogging, dataWindowStopLogging

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void dataWindowStartLogging(char[] windowName);
void dataWindowStopLogging(char[] windowName);
```

## Description

Starts or stops logging in a specified [Data Window](../../../CANoeCANalyzer/Windows/Data/DataWindow.md).

## Parameters

- **windowName**: Name of the Data Window.

## Return Values

—

## Example

```plaintext
dataWindowStartLogging("MyDataWindow");
...
dataWindowStopLogging("MyDataWindow");
```
