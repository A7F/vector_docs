# diagGenerateKeyFromSeed

**Valid for**: CANoe DE

## Function Syntax

```plaintext
long diagGenerateKeyFromSeed ( byte seedArray[], dword seedArraySize, dword securityLevel, char variant[], char ipOption[], byte keyArray[], dword maxKeyArraySize, dword& keyActualSizeOut); // form 1
long diagGenerateKeyFromSeed (char ecuQualifier[], byte seedArray[], dword seedArraySize, dword securityLevel, char variant[], char option[], byte keyArray[], dword maxKeyArraySize, dword& keyActualSizeOut); // form 2
```

## Description

Creates a key to execute secured diagnostic functions within devices. The key will be defined with the Seed of the device. If the computation takes more than 1 ms, [diagStartGenerateKeyFromSeed](CAPLfunctionDiagStartGenerateKeyFromSeed.md) in combination with the callback [_Diag_GenerateKeyResult](CAPLfunctionDiagGenerateKeyResult.md) should be used.

## Parameters

- **seedArray**: Seed for the definition of the key.
- **seedArraySize**: Number of bytes in the SeedArray.
- **securityLevel**: Security level for which the key will be created.
- **variant**: Variant of the diagnostic description.
- **ipOption**: Optional parameter that will be forwarded to the customer function. If not used, an empty string " " must be given here. Further options that will be forwarded to the DLL. If not present or an empty string, the value might be derived from the state of the communication, e.g. the diagnostic session the ECU is in.
- **keyArray**: Key that is created with the customer DLL.
- **maxKeyArraySize**: The maximum allowed number of bytes in the keyArray.
- **keyActualSizeOut**: Actual used bytes in the keyArray.
- **ecuQualifier**: Qualifier of the ECU or target as set in the diagnostic configuration dialog for the respective diagnostic description.

## Return Values

At success 0 will be returned, otherwise an [error code](../CAPLfunctionsDiagnosticsErrorCode.md) will be returned.

## Example

This example shows schematically the use of `diagGenerateKeyFromSeed` and the Callback function in a CAPL test module.

```plaintext
variables
{
    //actual size of Seed and Key Arrays depend on ECU
    byte gSeedArray[2];
    int gSeedArraySize = 1;
    int gSecurityLevel = 0x02;
    char gVariant[200] = "Variant1";
    char gOption[200] = "option";
    byte gKeyArray[255];
    int gMaxKeyArraySize = 255;
    dword gActualSizeOut = 0;
    char gDebugBuffer[2000];
    diagRequest ECU.SeedLevel_0x01_Request gSeedReq;
    diagResponse ECU.SeedLevel_0x01_Request gSeedResp;
    diagRequest ECU.KeyLevel_0x01_Send gKeyReq;
}

//Unlock ECU by calling customer specific SeedKey DLL (e.g. in a CAPL test module)
testcase UnlockEcu()
{
    long ret;

    //Request seed from ECU
    diagSendRequest(gSeedReq);
    //Wait until request has been sent completely
    testWaitForDiagRequestSent(gSeedReq, 1000);
    //Wait for response and write seed from response parameter to array
    testWaitForDiagResponse(gSeedReq, 1000);
    diagGetLastResponse (gSeedReq, gSeedResp);
    diagGetParameterRaw (gSeedResp, "SecuritySeed", gSeedArray, elcount(gSeedArray));
    //Calculate key
    ret = diagGenerateKeyFromSeed ("ECU", gSeedArray, gSeedArraySize, gSecurityLevel, gVariant, gOption, gKeyArray, gMaxKeyArraySize, gActualSizeOut);
    if( 0 == ret) //diagGenerateKeyFromSeed successful
    {
        //Write result to diagnostic request
        diagSetParameterRaw(gKeyReq, "SecurityKey", gKeyArray, gActualSizeOut);
        //Send Key to unlock ECU
        gKeyReq.SendRequest();
        testWaitForDiagRequestSent(gKeyReq, 1000);
    }
}

void MainTest ()
{
    UnlockEcu();
}
```

[Seed & Key DLL / Security Access](../../../CANoeCANalyzer/Diagnostics/Special/DiagSecurityDLLAccess.md) • [_Diag_GenerateKeyResult](CAPLfunctionDiagGenerateKeyResult.md) • [diagStartGenerateKeyFromSeed](CAPLfunctionDiagStartGenerateKeyFromSeed.md) • [TestWaitForGenerateKeyFromSeed](../../Test/Functions/CAPLfunctionTestWaitForGenerateKeyFromSeed.md)
