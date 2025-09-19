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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
