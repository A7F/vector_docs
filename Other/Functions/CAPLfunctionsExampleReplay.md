[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionsExampleReplay.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » Example: ReplayStart, ReplayStop, ReplaySuspend, ReplayResume, ReplayState

# Example: ReplayStart, ReplayStop, ReplaySuspend, ReplayResume, ReplayState

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

```plaintext
variables
{
    char replayName[32] = "ibus_data";
}

on key 'b'
{
    replayStart( replayName);
}

on key 'e'
{
    replayStop( replayName);
}

on key 's'
{
    replaySuspend( replayName);
}

on key 'r'
{
    replayResume( replayName);
}

on key 'w'
{
    writeReplayState( replayName);
}

void writeReplayState( char name[])
{
    switch ( replayState( name))
    {
        case 0:
            write( "Replay Block %s is stopped", replayName);
            break;
        case 1:
            write( "Replay Block %s is running", replayName);
            break;
        case 2:
            write( "Replay Block %s is suspended", replayName);
            break;
        default:
            write( "Error: Replay Block %s has an unknown state!", replayName);
            break;
    };
}
```

- Technical References are only available in English
- © Vector Informatik GmbH
- CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3
- [Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)
- [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)