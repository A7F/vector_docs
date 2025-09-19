[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionlookupServiceSignalNumber.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » lookupServiceSignalNumber

# lookupServiceSignalNumber

**Valid for:** CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
serviceSignalNumber * lookupServiceSignalNumber(char serviceSignalName[]);
```

## Description

Searches for a SOME/IP [Service Signal](../../../CANoeCANalyzer/Ethernet/ILSomeIP/ILSomeIPServiceSignals.md) in the database(s). If the Service Signal is not found or if the name is not unique, test modules/units report an **error in test system** while simulation/analysis nodes write a warning into the Write Window, and the function returns an invalid `serviceSignal`. If the `lookupServiceSignalNumber` function is used during the measurement, the collection of signal values only begins at this point.

**Notes:** It is recommended to use this function only in special cases or during measurement start, since searching for the database definition may impact realtime performance.

`lookupServiceSignalNumber` can be used to access a Service Signal, which was specified by a string during measurement. The function makes it possible to write dynamic tests with Service Signals, where the name of the Service Signal is not given at compile-time.

`lookupServiceSignalNumber` is for Service Signals, which can be represented as number. For data and string types see [lookupServiceSignalData](CAPLfunctionlookupServiceSignalData.md) and [lookupServiceSignalString](CAPLfunctionlookupServiceSignalString.md).

## Parameters

- **serviceSignalName**: The [qualifier of the Service Signal](../../../CANoeCANalyzer/Ethernet/ILSomeIP/ILSomeIPServiceSignals.md).

## Return Values

The found unique Service Signal or an invalid object.

## Example

```plaintext
// set the values of some service-signals

int i;
char serviceSignalNames[3][70] = 
{ 
  "sif_2001::TrafficSignDetection::DetectedTrafficSign[0].DistanceToSign",
  "sif_2001::TrafficSignDetection::DetectedTrafficSign[0].Reliability",
  "sif_2001::TrafficSignDetection::DetectedTrafficSign[0].SignType" 
};
double serviceSignalValues[3] = { 1.0, 2.0, 3.0 };

for( i = 0; i < elcount(serviceSignalNames); i++ )
{
  serviceSignalNumber * sig;
  sig = lookupServiceSignalNumber( serviceSignalNames[i] );

  $sig = serviceSignalValues[i];
}
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
