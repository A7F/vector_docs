[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTExampleReadOutRegistries.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » Example: Read-Out of the Registries

# Example: Read-Out of the Registries

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

In the following example whenever a registry changes its contents are output to the Write Window.

```plaintext
OnMostAsRegistry(long regsel)
{
    long size, i;
    long rxtxlog, fblockid, instid;
    // display registry type
    if(regsel == 1)
        write("Local Registry:");
    else if(regsel == 2)
        write("Bus Registry:");
    // get registry size
    size = mostAsRgGetSize(regsel);
    // print the whole registry
    write("Adr FBlock InstID");
    for(i = 0; i < size; ++i)
    {
        rxtxlog = mostAsRgGetRxTxLog(regsel,i);
        fblockid = mostAsRgGetFBlockID(regsel,i);
        instid = mostAsRgGetInstID(regsel,i);
        write("%04X %02X    %02X", rxtxlog, fblockid, instid);
    }
}
```

Bus Registry:

```
Adr    FBlock InstID
0100   02 00
0100   04 01
0100   C0 01
0101   C1 01
0101   C5 01
```

---
