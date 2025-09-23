[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Functions/CAPLfunctionFRSetPDuFilter.md)

[CAPL Functions](../../CAPLfunctions.md) » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » frSetPduFilter

# frSetPduFilter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This function can be called in [on preStart](../../Other/CAPLfunctionsEventProceduresOverview.md) and during measurement. This function has only effects on the CAPL nodes in the Simulation Setup.

## Function Syntax

`void frSetPduFilter(frPDU message, long mode);`

## Description

The function configures a filter for PDUs. With this filter it is possible to receive single PDUs with update bit = 0.

The function overrides the network hardware setting **Show PDUs with disabled Update Bit** (menu path: **Configuration|Network Hardware...|FlexRay|** [Options](../../../CANoeCANalyzer/FlexRay/Configuration/FlexRay_Configuration_Options.md)).

The advantage of this filter is that only dedicated PDUs with disabled update bit are received instead of all PDUs with disabled update bit in the network.

## Parameters

- **message**  
  Name of the PDU to be filtered.

- **mode**  
  Configures the filter mode.

  - **0**  
    PDU reception disabled

  - **1**  
    PDU with update bit = 1 will be received

  - **2**  
    PDU will be received, the update bit is not evaluated

## Return Values

—

## Example

—
