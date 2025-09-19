[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitScopeGetMessageBits.md)

[CAPL Functions](../../CAPLfunctions.md) » [Scope](../../Scope/CAPLfunctionsScopeOverview.md) » testWaitScopeGetMessageBits

# testWaitScopeGetMessageBits

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long testWaitScopeGetMessageBits(message msg, ScopeAnalysisSetup setup, dword arraySize, scopeBitData signalData1[], scopeBitData signalData2[], scopeBitData signalData3[]);
```

## Description

A CAN message stored in the scope buffer will be parsed. For each bit of the message, the signal voltage levels, the bit length, and the bit type will be returned.

## Parameters

- **msg**: The message the bits are fetched.
- **setup**: The parameter is used to configure the signal parser and has the following format.

  **ScopeAnalysisSetup Selectors**

  - **samplePoint**: Sample point in percent. At this point, the signal level will be measured.
    - Classic CAN: Value will be used for all bits of the message.
    - CAN FD: Value will be used for the bits of the arbitration phase.
  - **samplePointDataPhase**: Sample point in percent. At this point, the signal level will be measured.
    - Classic CAN: Value will not be used.
    - CAN FD: Value will be used for the bits of the data phase.

- **arraySize**:
  - [in] the size of the arrays signalData1, signalData2, and signalData3
  - [out] the number of bits parsed and stored in the signalData-arrays.

- **signalData1, signalData2, signalData3**: If the function was successful, the three arrays will contain information of all bits of the message.
  - **signalData1**: The data of each bit for CAN high
  - **signalData2**: The data of each bit for CAN low
  - **signalData3**: The data of each bit for CAN diff (CAN high - CAN low, or CAN low – CAN high as configured in the scope configuration).

  **scopeBitData Selectors**

  - **type**: Type of the bit
  - **typeEx**: 0: data bit, 1: stuff bit
  - **bitValue**: Logical bit value (0, or 1)
  - **startTime**: Time stamp of bit start in ns
  - **bitLength**: Length of the bit in ns
  - **signalVoltage**: Signal voltage at the sampling point
  - **signalPolarity**: Signal polarity:
    - 0 = CAN high - CAN low
    - 1 = CAN low - CAN high

## Return Values

- **1**: success
- **0**: timeout
- **-1**: general error
- **-2**: scope drift compensation error
- **-3**: scope has no measurement data
- **-100**: bit analyzer parser error
- **-105**: array size too small

## Example

```plaintext
dword arraySize = 200;
message 0x111 msg1;
long res;
long evtNo;
ScopeBitData data1[200];
ScopeBitData data2[200];
ScopeBitData data3[200];
ScopeAnalysisSetup setupAnalyse;

//------------------------------
//Connect to scope
//------------------------------
res = scopeConnect();
res = testWaitForScopeEvent(eScopeConnected, 8000);

if(res > 0)
{
  testStep("Wait For Event", "Waiting for Message 0x111");
  testJoinMessageEvent(msg1.id);
  evtNo = TestWaitForAnyJoinedEvent(2000);
  res = TestGetWaitEventMsgData(msg1);

  if(res != 0)
  {
    testStepFail("Wait For Event", "No event received");
    res = scopeDisconnect();
    res =testWaitForScopeEvent(eScopeDisconnected, 8000);
    return;
  }
  else
  {
    testStepPass("Wait For Event", "Event received");
  }

  res = scopeTriggerNow();
  if(res > 0)
  {
    res =(testWaitForScopeEvent(eScopeTriggered, 5000));

    if(res > 0)
    {
      setupAnalyse.samplePoint = 70;
      res = testWaitScopeGetMessageBits(msg1, setupAnalyse, arraySize, data1, data2, data3);

      if(res > 0 || res == -105)
      {
        int i;
        for(i = 0; i < arraySize;++i)
        {
          write("CANH: StarTime%.6f s, Type: %d, TypeExt: %d, BitLength: %d, Voltage: %.6f, BitValue: %d", data1[i].StartTime /1000000000., data1[i].type, data1[i].typeEx, data1[i].bitLength, data1[i].signalVoltage,data1[i].bitValue);
          write("CANL: StarTime%.6f s, Type: %d, TypeExt: %d, BitLength: %d, Voltage: %.6f, BitValue: %d", data2[i].StartTime /1000000000., data2[i].type, data2[i].typeEx, data2[i].bitLength, data2[i].signalVoltage,data2[i].bitValue);
          write("CANDiff: StarTime%.6f s, Type: %d, TypeExt: %d, BitLength: %d, Voltage: %.6f, BitValue: %d", data3[i].StartTime /1000000000., data3[i].type, data3[i].typeEx, data3[i].bitLength, data3[i].signalVoltage,data3[i].bitValue);
          if(i > 5) //write only first 5 results
          break; 
        }
      }
    }
  }
}
res = scopeDisconnect();
res =testWaitForScopeEvent(eScopeDisconnected, 8000);
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
