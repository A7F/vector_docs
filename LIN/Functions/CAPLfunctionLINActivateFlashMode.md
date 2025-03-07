[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINActivateFlashMode.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linActivateFlashMode

# linActivateFlashMode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
dword linActivateFlashMode(byte activate);
```

## Description

This function activates flash mode on high-speed capable transceivers. Note that in flash mode such a transceiver will use faster rising and falling edges and will disregard the EMC limitations of the LIN network. Note also, that the activation of the flash mode cannot be done while the channel is transmitting or the scheduler is running.

## Parameters

- **activate**: 1 will activate the flash mode, 0 will deactivate it.

## Return Values

On successful request returns 1, otherwise 0.

## Example

```c
// test case for disturbing parts of a bit
// note, that test cases can only be used in the context of test module nodes

testcase tcDisturbPartialBit()
{
    dword flashModeActive;

    flashModeActive = 0;

    do
    {
        if (!linActivateFlashMode(1)) // request activation of flash mode
        {
            break; // if the request has been denied, either the cab/piggy is incapable of
                   // flash mode or the scheduler is still running
        }
        testWaitForTimeout(10); // give the hardware time to activate the flash mode
        flashModeActive = linIsFlashModeActive(); // check if flash mode has been
                                                  // activated successfully
    } while (!flashModeActive);

    if (!flashModeActive)
    {
        testStepFail("tcDisturbPartialBit", "Flash mode could not be activated because of active scheduler or because the cab/piggy does not support flash mode.");
        return;
    }

    linInvertRespBitEx(0, 0, 8, 4, 8, 0); // invert the middle part of the stop bit of the
                                          // first byte of the response to id 0

    ...
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)