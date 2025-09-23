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
