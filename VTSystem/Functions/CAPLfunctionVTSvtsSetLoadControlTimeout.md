[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSvtsSetLoadControlTimeout.md)

## vtsSetLoadControlTimeout

[CAPL Functions](../../CAPLfunctions.md) » [VT System](../CAPLfunctionsVTSystemOverview.md) » vtsSetLoadControlTimeout

**Valid for**: CANoe DE • CANoe:lite DE

### Function Syntax

```plaintext
long vtsSetLoadControlTimeout (char Target[], double Timeout);
```

### Description

When signals with brief interruptions are created (especially PWM signals), it is possible to set a hold time (a control timeout) so that the electronic load does not have to be corrected again on every signal edge. Thus, if the input voltage rises again before the timeout expires, the electronic load is still adjusted to the old value and only has to be corrected minimally, if at all. Because the settling time is eliminated, very rapidly changing PWM signals can also be operated with the electronic load.

The timeout time selected should be approximately 10 to 100 times higher than the frequency of the control unit output signal. For a PWM signal with a frequency starting from 10 Hz, a timeout time of 1 to 10 seconds is sufficient. If this functionality is not required, the timeout time should be set to 0, because it slows down the corrections.

### Parameters

- **Target**: Name of the system variable/namespace that will be affected by this function call.
- **Timeout**: Defines the timeout time for the internal load in seconds. Permissible range of values: 1...255 s, resolution 1 s, 0: no timeout (default). If an invalid value is specified, the command will fail.

### Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-3**: The specified timeout is not valid.
- **-4**: The function wasn't called in the context of the main method of a test module. So it is not possible to wait until the setting will be taken over from the VT System. Otherwise, the call was successful but it is not sure if the settings have been taken over already when the call returns.

### Example

```plaintext
vtsSetLoadControlTimeout (sysvar::VTS::LowBeamRight, 10.0);
```

The following figure illustrates the control response using an example:

A timeout of 2 s was set here. The input voltage (yellow) and the current flowing at the input (red) are presented qualitatively. At the first pulse, the input voltage is not applied for only approximately 1 s. In this case, a timeout does not occur and the set current continues flowing when the input voltage is applied again. At the second pulse, a timeout occurs. In this case, the input voltage is not applied for a period lasting more than 2 s. The internal load is then connected with high resistance. If the input voltage is restored, the internal load must first adjust to the set current, which is apparent from the slow rise in the current.

[SetLoadControlTimeout](CAPLfunctionVTSSetLoadControlTimeout.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
