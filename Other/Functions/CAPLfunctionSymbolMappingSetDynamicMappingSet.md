# SymbolMappingSetDynamicMappingSet

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void SymbolMappingSetDynamicMappingSet(char mappingSetName[]);
```

## Description

Changes the dynamic mapping set that will be used for mapping in the CANoe DE product [Symbol Mapping](../../../CANoeCANalyzer/Ribbon/Environment/Mapping/Mapping.md) dialog. Only the mapping relations contained in the given dynamic mapping set and in the static mapping set are considered.

## Parameters

- **mappingSetName**: Name of a dynamic set which shall be activated.

## Return Values

- **-1**: if no mapping set with the given name is found
- **0**: if the mapping set with the given name is found and its contained mapping relations are mapped

## Example

```plaintext
on key '1'
{
  // Activate DataSet1 and map its contained mapping relations
  SymbolMappingSetDynamicMappingSet ("DataSet1");
}
```
