[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/CAPLfunctionsJ1939Limitations.md)

[CAPL Functions](../CAPLfunctions.md) » [J1939](CAPLfunctionsJ1939StartPage.md) » Specific Language Limitations

# Specific Language Limitations

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

- It is possible to change the DLC of a parameter group (PG), depending on the specified size. If the original DLC is smaller than 8 bytes, the DLC can be changed variable in the range 1..8 bytes. If the parameter group was created with a DLC > 8 byte, it can only be changed within this range (maximal size is the original DLC).
- It is not possible to define arrays with parameter groups.

•  Technical References are only available in English

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)