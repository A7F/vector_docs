[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/CAPLfunctionsMOSTHighObserverErrorCodes.md)

[CAPL Functions](../CAPLfunctions.md) » [MOST](CAPLfunctionsMOSTOverview.md) » High Observer Error Codes

# MOST: High Observer Error Codes

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE

## Errors

- **Error Code:** 0
  - **Description:** Data Frame has unexpected FrameID.
  - **Erroneous Value:** yes
  - **Expected Value:** yes

- **Error Code:** 1
  - **Description:** 0-Frame has an unexpected Block Nr.
  - **Erroneous Value:** yes
  - **Expected Value:** yes

- **Error Code:** 2
  - **Description:** Data Frames without prior 0-Frame.
  - **Erroneous Value:** no
  - **Expected Value:** no

- **Error Code:** 3
  - **Description:** FrameID of Ack/Nack Frame does not match FrameID of the last Data Frame.
  - **Erroneous Value:** yes
  - **Expected Value:** yes

- **Error Code:** 4
  - **Description:** Block Nr of Ack/Nack Frame does not match Nr of the block.
  - **Erroneous Value:** yes
  - **Expected Value:** yes

- **Error Code:** 5
  - **Description:** Frame acknowledge in Block Acknowledge mode.
  - **Erroneous Value:** no
  - **Expected Value:** no

- **Error Code:** 6
  - **Description:** (Multiple) Frame or Block Request not allowed.
  - **Erroneous Value:** no
  - **Expected Value:** no

- **Error Code:** 7
  - **Description:** MHP message without existing connection.
  - **Erroneous Value:** no
  - **Expected Value:** no

- **Error Code:** 8
  - **Description:** Observer Timeout, observing of connection stopped.
  - **Erroneous Value:** no
  - **Expected Value:** no

- **Error Code:** 9
  - **Description:** Invalid MHP message.
  - **Erroneous Value:** no
  - **Expected Value:** no

- **Error Code:** 10
  - **Description:** Too many REQUEST CONNECTION retries (R_Request).
  - **Erroneous Value:** yes
  - **Expected Value:** yes

- **Error Code:** 11
  - **Description:** Timeout violation between REQUEST CONNECTION attempts (T_Send).
  - **Erroneous Value:** yes (ms)
  - **Expected Value:** yes (ms)

- **Error Code:** 12
  - **Description:** Too many START CONNECTION retries (R_Start).
  - **Erroneous Value:** yes
  - **Expected Value:** yes

- **Error Code:** 13
  - **Description:** Timeout violation between START CONNECTION attempts (T_Ready).
  - **Erroneous Value:** yes (ms)
  - **Expected Value:** yes (ms)

- **Error Code:** 14
  - **Description:** Illegal value of Options field in 0-Frame.
  - **Erroneous Value:** yes
  - **Expected Value:** no

- **Error Code:** 15
  - **Description:** Timeout of 0-Frame retry (T_Frame).
  - **Erroneous Value:** yes (ms)
  - **Expected Value:** yes (ms)

- **Error Code:** 16
  - **Description:** Timeout violation sending NegAck on missing 0-Frame (T_Frame).
  - **Erroneous Value:** yes (ms)
  - **Expected Value:** yes (ms)

- **Error Code:** 17
  - **Description:** Too many NegAck retries on missing 0-Frame (R_NegAck).
  - **Erroneous Value:** yes
  - **Expected Value:** yes

- **Error Code:** 18
  - **Description:** Too many retransmission attempts (R_Trans).
  - **Erroneous Value:** yes
  - **Expected Value:** yes

- **Error Code:** 19
  - **Description:** Timeout violation between retransmission attempts (T_Retrans).
  - **Erroneous Value:** yes (ms)
  - **Expected Value:** yes (ms)

- **Error Code:** 20
  - **Description:** Timeout transmitting one block (T_Trans).
  - **Erroneous Value:** yes (ms)
  - **Expected Value:** yes (ms)

- **Error Code:** 21
  - **Description:** Timeout violation between Data Frames (T_AIR_Delay).
  - **Erroneous Value:** yes (ms)
  - **Expected Value:** yes (ms)

- **Error Code:** 22
  - **Description:** Too many END CONNECTION Tx retries (R_End).
  - **Erroneous Value:** yes
  - **Expected Value:** yes

- **Error Code:** 23
  - **Description:** Timeout violation between END CONNECTION attempts (T_End).
  - **Erroneous Value:** yes (ms)
  - **Expected Value:** yes (ms)

- **Error Code:** 24
  - **Description:** Timeout violation closing the connection (T_Delay_End).
  - **Erroneous Value:** yes (ms)
  - **Expected Value:** yes (ms)

- **Error Code:** 25
  - **Description:** Timeout violation between HOLD CONNECTION messages (T_Hold_Resend).
  - **Erroneous Value:** yes (ms)
  - **Expected Value:** yes (ms)

- **Error Code:** 26
  - **Description:** Timeout after last HOLD CONNECTION message (T_Hold).
  - **Erroneous Value:** yes (ms)
  - **Expected Value:** yes (ms)

- **Error Code:** 27
  - **Description:** Timeout of HOLD CONNECTION cycle (T_Hold_Max_Buf).
  - **Erroneous Value:** yes (ms)
  - **Expected Value:** yes (ms)

- **Error Code:** 28
  - **Description:** Timeout violation sending NegAck (T_Receive).
  - **Erroneous Value:** yes (ms)
  - **Expected Value:** yes (ms)

- **Error Code:** 29
  - **Description:** Timeout violation between Data Frame and NegAck (T_dwn_NegAck).
  - **Erroneous Value:** yes (ms)
  - **Expected Value:** yes (ms)

- **Error Code:** 30
  - **Description:** Illegal value of NDF_Ack: Value must not exceed NDF.
  - **Erroneous Value:** yes
  - **Expected Value:** yes

- **Error Code:** 31
  - **Description:** Scale * NDF_Ack exceeds maximum block size.
  - **Erroneous Value:** yes (block size)
  - **Expected Value:** yes (block size)

- **Error Code:** 32
  - **Description:** Timeout violation between ADJUST TRANSMISSION RATE (increase) messages (T_TxSpeedRecovery).
  - **Erroneous Value:** yes (ms)
  - **Expected Value:** yes (ms)

- **Error Code:** 33
  - **Description:** ADJUST TRANSMISSION RATE is only allowed for block acknowledge mode using the asynchronous channel.
  - **Erroneous Value:** no
  - **Expected Value:** no

- **Error Code:** 34
  - **Description:** Total number of frames changed.
  - **Erroneous Value:** yes
  - **Expected Value:** yes

- **Error Code:** 35
  - **Description:** MHP message not expected.
  - **Erroneous Value:** no
  - **Expected Value:** no

- **Error Code:** 40
  - **Description:** Usage of control channel not allowed with MHP 2.3 or newer
  - **Erroneous Value:** no
  - **Expected Value:** no

- **Error Code:** 41
  - **Description:** Field **MaxBlkSize** not allowed in MHP version < 2.3
  - **Erroneous Value:** no
  - **Expected Value:** no

- **Error Code:** 42
  - **Description:** Illegal value of **MaxBlkSize**: Value must be between Scale *NDF_ACK and (Scale+1)* NDF_ACK
  - **Erroneous Value:** yes
  - **Expected Value:** yes (`Scale << 16 + NDF_ACK`)

- **Error Code:** 43
  - **Description:** Frame Interleave not allowed for connections with different priorities
  - **Erroneous Value:** no
  - **Expected Value:** no

- **Error Code:** 44
  - **Description:** Frame Interleave not allowed for multiple connections to one device
  - **Erroneous Value:** no
  - **Expected Value:** no

- **Error Code:** 45
  - **Description:** Field **HoldFlag** not allowed in MHP version < 2.3 or Negative Acknowledge frames
  - **Erroneous Value:** no
  - **Expected Value:** no

## Warnings

- **Error Code:** 36
  - **Description:** Negative Acknowledge frame observed.
  - **Erroneous Value:** yes (block no.)
  - **Expected Value:** no

- **Error Code:** 37
  - **Description:** (Multiple) Frame Request observed.
  - **Erroneous Value:** no
  - **Expected Value:** no

- **Error Code:** 38
  - **Description:** Block Request observed.
  - **Erroneous Value:** no
  - **Expected Value:** no

- **Error Code:** 39
  - **Description:** Receiver refused connection by sending PrioAck with higher value than Prio.
  - **Erroneous Value:** yes
  - **Expected Value:** yes

[OnMostMHPError](EventProcedures/CAPLfunctionOnMOSTMHPError.md) • [MOST High Observer and Combiner](CAPLfunctionsMOSTHighObserverCombiner.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
