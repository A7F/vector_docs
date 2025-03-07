[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionA664ResizeMessage.md)

**CAPL Functions** » [AFDX](../CAPLfunctionsAFDXOverview.md) » A664ResizeMessage

# A664ResizeMessage

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long A664ResizeMessage (a664Message aMessage, word newSize)
```

## Description

The message object’s payload area is resized to match the new payload size. This affects the selectors [Length](../CAPLfunctionsAFDXSelectors.md#SelectorLength) and [AfdxLength](../CAPLfunctionsAFDXSelectors.md#AfdxLength). If the current aMessage headers are valid (see [AFDX packet validation rules](../../../CANoeCANalyzer/AFDX/protocols/afdxProtocolAfdx.md#validAfdxFrame)), the corresponding header content is adapted as well (IP and UDP headers).

## Parameters

- **aMessage**: Message object to be resized.
- **newSize**: New payload size (without counting sequence number) in range 0..8192.

## Return Values

- **0**: Resize failed.
- **1**: Resize successful.

## Example

```plaintext
a664Message DEMOMSG_ALLTYPES msg8 = {msgChannel = 1};
write ("DEMOMSG_ALLTYPES message initialized!");
write ("Msg Name:%s", msg8.Name);

result = a664ResizeMessage(msg8, 512);
if (result == 0) {
    writeEx (-3,3,"resizing DEMOMSG_ALLTYPES message to length 512 failed!");
} else {
    writeEx (-3,3,"resize DEMOMSG_ALLTYPES to payload size 512 succeeded!");
}
```

[See Also](javascript:void(0);)