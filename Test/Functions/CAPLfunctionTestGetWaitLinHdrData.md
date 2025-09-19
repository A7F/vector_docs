[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestGetWaitLinHdrData.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestGetWaitLinHdrData

# TestGetWaitLinHdrData

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long TestGetWaitLinHdrData (linheader aHeader);
long TestGetWaitLinHdrData (dword index, linheader aHeader);
```

## Description

If LIN Header event is the last event that triggers a wait instruction, the header content can be called up with the first function. The second function can only be used for "joined events". The number of the "joined event" (return value of "testJoin...") is here being used as an index.

## Parameters

- **aHeader**: Header variable that should be filled in with this function.
- **index**: Number of the "joined event" corresponds with the return value of "testJoin...".

## Return Values

- **0**: Data access successful
- **-1**: Data access could not be executed, the last event was not a LIN header event

## Example

```plaintext
testcase tcTFS_linHdrEvent ()
{
    linheader  linHeaderData;
    if (testWaitForLinHeader(5000) == 1)
    {
        if (TestGetWaitLinHdrData(linHeaderData) == 0)
        {
            testStep("Evaluation", "LIN Header event occurred for FrameId=0x%X", linHeaderData.ID);
        }
    }
}
```

[TestWaitForLinHeader](CAPLfunctionTestWaitForLinHeader.md) • [TestJoinLinHeaderEvent](CAPLfunctionTestJoinLinHeaderEvent.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
