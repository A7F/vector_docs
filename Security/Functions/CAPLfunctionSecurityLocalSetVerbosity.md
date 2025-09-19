[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalSetVerbosity.md)

**CAPL Functions** » **Security** » **SecurityLocalSetVerbosity**

# SecurityLocalSetVerbosity

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
Replaces `LocalSecuritySetVerbosity`.

## Function Syntax

`void SecurityLocalSetVerbosity(dword level)`

## Description

Configures the notification level for a node from low (0) to high (5).

## Parameters

- **dword level**  
  Desired notification level. Range: 0-5
  - 0: Only critical errors are printed.
  - 1: All errors are printed
  - 2: Additionally warnings are printed
  - 3: Information messages are printed too.
  - 4-5: Debug messages are active.

## Return Values

—

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
