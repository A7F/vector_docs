[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/A429/CAPLfunctionsA429DefineARINCword.md)

# Declaration of ARINC Words

[CAPL Functions](../CAPLfunctions.md) » [A429](CAPLfunctionsA429Overview.md) » Declaration of ARINC Words

**Valid for**: CANoe DE • CANoe4SW DE

ARINC words may be controlled by means of a CAPL program. An ARINC word object is created with the keyword **a429word**. ARINC words [defined in a database](../../CANoeCANalyzer/A429/basicsA429/A429dbSupport.md) may also be used for initialization.

For more convenience in the programming environment a [CAPL include file](../../Shared/CAPL/IncludeFiles/IncludeFiles.md) is provided. The file gives the programmer a number of symbolic constants and some helper routines as a supplement for the CAPL API. Use this statement in the include section of your CAPL code: `#include "A429/A429utils.cin"`.

**Example: Create ARINC Word Objects**

```plaintext
a429word 0x82 myA429msg1; // (1)
a429word Label_123 myA429msg2; // (2)
a429word * myA429msg3; // (3)
```

The members of the ARINC word object are accessed via [selectors](CAPLfunctionsA429Selectors.md).

**Example: Transmit an ARINC Word on Request**

```plaintext
a429word * myA429msg4 = {msgChannel = 1, id = 0x82}; // create ARINC word
myA429msg4.dword(0) = 0x1234 << 10; // shift behind SDI
output(myA429msg4);  // transmit it
```

## ARINC word specific event procedures

If there is a valid ARINC word event received, an event procedure is called. Note that ARINC word events may be triggered from a connected hardware channel or even internally from a simulated node or an [Interactive Generator](../../CANoeCANalyzer/A429/windows/ig/A429IGold.md). The [event procedures](../../Shared/CAPL/General/EventProceduresOverview.md)

- [on a429Word](EventProcedures/CAPLfunctionA429OnA429Word.md) and
- [on a429Worderror](EventProcedures/CAPLfunctionA429OnA429WordError.md)

are available.

**Note**

Most of the API functions need an ARINC word as a parameter. Note that in this ARINC word a valid channel needs to be assigned with the selector [msgchannel](CAPLfunctionsA429Selectors.md).

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)