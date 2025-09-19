[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForTimeout.md)

**CAPL Functions** » **Test Feature Set** » **TestWaitForTimeout**

# TestWaitForTimeout

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long TestWaitForTimeout(dword aTimeout);
```

## Description

Waits until the expiration of the specified timeout time.

## Parameters

- **aTimeout**: Maximum time that should be waited [ms].  
  (Transmission of 0: no timeout controlling. In this function this results in a hang up of the test module)

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout

## Example

```c
// waits for 3000 ms
long result;
result = TestWaitForTimeout(3000);
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
