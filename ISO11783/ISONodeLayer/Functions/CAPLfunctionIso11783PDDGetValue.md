[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783PDDGetValue.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Node Layer** » Iso11783PDDGetValue

# Iso11783PDDGetValue

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
float Iso11783PDDGetValue( dword ecuHandle, dbSignal signal, dword elementNumber );
float Iso11783PDDGetValue( dword ecuHandle, dword ddi, dword elementNumber );
```

## Description

The function requests the value of a process variable.

## Parameters

- **ecuHandle**  
  Handle of the ECU. The handle must previously have been created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md).

- **signal**  
  Signal from the database. The attribute `ddi` must be defined for the signal. The signal must be defined in the same database as the node!

- **ddi**  
  Data Dictionary Identificator 0x000..0xFFFF

- **elementNumber**  
  Element number, 0x000..0xFFF

## Return Values

Value of the process variable, 0 if the variable is not defined

## Example

```plaintext
char text[256];
value = Iso11783PDDGetValue( ecuHandle, PD::AppRateSignal, 0;
if (Iso11783PDDGetLastError () != 0) {
  Iso11783PDDGetLastErrorText ( elCount(text), text );
  write( "ERROR: %s", text );
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
