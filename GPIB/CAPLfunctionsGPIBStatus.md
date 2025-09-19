[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/GPIB/CAPLfunctionsGPIBStatus.md)

**CAPL Functions** » **GPIB** » Status

# GPIB Status
*(Only available with GPIB & CANoe!)*

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE

## Status Word
Contains the status bits of the current bus/device situation.  
Integer, 2 Bytes

- 15: ERR
- 14: TIMO
- 13: END
- 12: SRQI
- 11: RQS
- 10: —
- 9: —
- 8: CMPL
- 7: LOK
- 6: REM
- 5: CIC
- 4: ATN
- 3: TACS
- 2: LACS
- 1: DTAS
- 0: DCAS

## Explanation

- **ERR**: Error detected
- **TIMO**: Timeout
- **END**: EOI or EOS detected
- **SRQI**: SRQ detected by CIC
- **RQS**: Device needs service
- **CMPL**: I/O completed
- **LOK**: Local lockout state
- **REM**: Remote state
- **CIC**: Controller-in-Charge
- **ATN**: Attention asserted
- **TACS**: Talker active
- **LACS**: Listener active
- **DTAS**: Device trigger state
- **DCAS**: Device clear state

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
