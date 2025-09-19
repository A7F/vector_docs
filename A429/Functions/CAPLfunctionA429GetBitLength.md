[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/A429/Functions/CAPLfunctionA429GetBitLength.md)

## CAPL Functions » A429 » a429GetBitLength

### Function Syntax

```plaintext
long a429GetBitLength( a429worderror myA429word );
```

### Description

If a Rx error (bitrate too high/low) is detected the bit position as well as the error position in the bit is measured. The length of the erroneous measured bit is returned with this function.

### Parameters

- **myA429word**: ARINC word in `on a429Worderror` handler

### Return Values

- **-1**: there is no bit length value available
- **0..100000**: time in nanoseconds

### Example

—

[See Also](javascript:void(0);)
