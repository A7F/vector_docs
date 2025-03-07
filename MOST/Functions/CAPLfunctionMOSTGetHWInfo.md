[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGetHWInfo.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGetHWInfo

# mostGetHWInfo

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostGetHWInfo(long channel, long infoID); // form 1
long mostGetHWInfo(long channel, long infoID, char infostring[], long buffersize); // form 2
```

## Description

Provides information about the MOST interface used.

## Parameters

- **channel**: Channel of the connected interface.
- **infoID**: The ID decides the meaning of the return value.

  - **kMostHWInfo_Type = 0**: 
    - Return Value: >0
    - Description: Interface type:
      - 1: VN2600/VN2610
      - 2: OptoLyzer
      - 3: —
      - 4: OptoLyzer G2 3150o
      - 5: VN2640
      - 6: OptoLyzer G2 3050e
      - 7: —
      - 8: OptoLyzer MOCCA compact 50e
      - 9: Logger
      - 10: OptoLyzer MOCCA compact 150c

  - **kMostHWInfo_SimulationMode = 1**: 
    - Return Value: 0, 1
    - Description: 
      - 0: real
      - 1: simulated

  - **kMostHWInfo_Manufacturer = 2**: 
    - Manufacturer: "Vector", "K2L"

  - **kMostHWInfo_SyncMode = 3**: 
    - Return Value: >=0
    - Description: Synchronization mode:
      - 0: off
      - 1: SW Sync active
      - 2: HW Sync active (network interface on <channel> is Sync Master)
      - 3: HW Sync active (network interface on <channel> is Sync Slave)

  - **kMostHWInfo_SyncStatus = 4**: 
    - Return Value: >=0
    - Description: Synchronization status:
      - 0: HW Sync not active
      - 1: HW Sync active
      - 2: HW Sync works correctly

- **infostring**: Target buffer to which text information is copied.
- **buffersize**: Size of the target buffer.

## Return Values

- **>=0**: Information value
- **<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [mostGetHWCapability](CAPLfunctionMOSTGetHWCapability.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)