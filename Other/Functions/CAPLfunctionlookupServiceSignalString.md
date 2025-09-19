[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionlookupServiceSignalString.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » lookupServiceSignalString

# lookupServiceSignalString

Valid for: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
serviceSignalString * lookupServiceSignalString(char serviceSignalName[]);
```

## Description

Searches for a SOME/IP [Service Signal](../../../CANoeCANalyzer/Ethernet/ILSomeIP/ILSomeIPServiceSignals.md) in the database(s). If the Service Signal is not found or if the name is not unique, test modules/units report an **error in test system** while simulation/analysis nodes write a warning into the Write Window, and the function returns an invalid `serviceSignal`. If the `lookupServiceSignalString` function is used during the measurement, the collection of signal values only begins at this point.

**Notes**: It is recommended to use this function only in special cases or during measurement start, since searching for the database definition may impact realtime performance.

`lookupServiceSignalString` can be used to access a Service Signal, which was specified by a string during measurement. The function makes it possible to write dynamic tests with Service Signals, where the name of the Service Signal is not given at compile time.

`lookupServiceSignalString` is for Service Signals, which can be represented as string. For data and number types see [lookupServiceSignalData](CAPLfunctionlookupServiceSignalData.md) and [lookupServiceSignalNumber](CAPLfunctionlookupServiceSignalNumber.md).

## Parameters

- **serviceSignalName**: The [qualifier of the Service Signal](../../../CANoeCANalyzer/Ethernet/ILSomeIP/ILSomeIPServiceSignals.md).

## Return Values

The found unique Service Signal or an invalid object.

## Example

```plaintext
// set the string of some service-signals to empty data

int i;
char serviceSignalNames[2][70] = 
{ 
  "sif_001::TrafficSignDetection::DetectedTrafficSign.Name",
  "sif_2001::TrafficSignDetection::DetectedTrafficSign.Description" 
};
char emptyString[8] = "";

for( i = 0; i < elcount(serviceSignalNames); i++ )
{
  serviceSignalString * sig;
  sig = lookupServiceSignalString( serviceSignalNames[i] );

  SetServiceSignalString( sig, emptyString );
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
