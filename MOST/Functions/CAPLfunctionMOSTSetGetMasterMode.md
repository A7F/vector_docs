[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSetGetMasterMode.md)

**CAPL Functions** » **MOST** » **mostSetMasterMode, mostGetMasterMode**

# mostSetMasterMode, mostGetMasterMode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is only available with MOST hardware VN2640, OptoLyzer G2 3150o and OptoLyzer MOCCA compact 150c.

## Function Syntax

```plaintext
long mostSetMasterMode(long channel, long mode);
long mostGetMasterMode(long channel);
```

## Description

Configures the timing master as static or non-static master. A non-static master shuts the network down if there is for example no signal at its optical input, whereas a static master keeps the network running independently from the input signal.

mostSetMasterMode becomes operative with the next call of [mostSetTimingMode](CAPLfunctionMOSTSetTimingMode.md).

## Parameters

- **channel**: Channel of the connected interface
- **mode**:
  - 0: static master
  - 1: non-static master

## Return Values

- **mostSetMasterMode**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)
- **mostGetMasterMode**:
  - \>\= 0: See mode parameter
  - \\\< 0: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

```plaintext
// configure network interface as non-static timing master
mostSetMasterMode(1, 1);
mostSetTimingMode(1, 1);
```

[mostGetChannel](CAPLfunctionMOSTGetChannel.md)
