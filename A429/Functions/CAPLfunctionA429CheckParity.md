[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/A429/Functions/CAPLfunctionA429CheckParity.md)

**CAPL Functions** » **A429** » **a429CheckParity**

# a429CheckParity

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```
dword a429CheckParity( a429word myA429word, int parity_value );
```

## Description

Checks the parity over 32 bits of the specified ARINC word.

## Parameters

- **myA429word**: ARINC word
- **parity_value**: specify whether check is odd or even
  - 2: odd parity
  - 3: even parity

## Return Values

- **0**: ARINC word’s parity does not correspond to checking rule. This value is also returned for an invalid parity_value.
- **1**: parity corresponds to checking rule

## Example

—

[See Also](javascript:void(0);)
- A429 CAPL Functions
- a429CalcBitLength
- a429CheckParity
- a429GetBitLength
- a429GetConfiguration
- a429GetErrorPosition
- a429ResetEx
- a429SetConfiguration
- a429SetGap
- a429SetParity
- a429SetScheduleTx
- a429StopTx
- a429Transmit
- ARINC Word Selectors
- Declaration of ARINC Words (A429)
- on a429error
- on a429word
- on a429worderror
- output (A429)
- Reconfigure a Channel (A429)
- Scheduling an ARINC Word (A429)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)