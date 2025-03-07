[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANstress/CAPLfunctionsCANstressMainTestFunctionExample.md)

**CAPL Functions** » [CANstress](CAPLfunctionsCANstressOverview.md) » Main Test Function Example

# Main Test Function Example

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE

### Example

```plaintext
MainTest ()
{
    dword ret = 0;
    dword numDisturbances = 0;

    // Create a CANstress Instance
    CANstressCreateServer();

    // Test if we could establish a connection to the CANstress hardware.
    CANstressConnect();

    // Load a prepared CANstress configuration, which disturbs the message 0x100
    // 31 times in the RTR-bit.
    CANstressOpen( "F:\\Develop\\usr\\addons\\CANstress-NL\\Disturb_100_RTR.cst" );

    // Now activate the CANstress hardware.
    CANstressStart();

    // Now, wait until the CANstress has been finished or the timeout has been elapsed
    ret = CANstressWaitForFinished( 5000 );
    if (ret == 0)
    {
        Write( "All disturbances of the configuration has been performed." );
    }
    else
    {
        numDisturbances = CANstressGetPerformedDisturbances();
        Write( "Disturb_100_RTR.cst : Not all disturbances has been performed:" );
        Write( "Performed Disturbances: %d", numDisturbances );
    }

    // Stop CANstress ...
    CANstressStop();

    // ... and load the next test-configuration
    // CANstressOpen(...);
    // .... and start the next test
    // CANstressStart();
    // ...
}
```

- Technical References are only available in English

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)