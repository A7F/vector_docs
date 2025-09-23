[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTConfigureEclSequence.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostConfigureEclSequence

# mostConfigureEclSequence

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is only available with MOST hardware VN2640.

## Function Syntax

```plaintext
long mostConfigureEclSequence (long channel, long numIntervals, dword[] state, dword[] duration100us);
```

## Description

The function prepares VN2640 to generate a signal sequence on the ECL. The signal sequence can be started with the mostGenerateEclSeq function.

The sequence is defined in two arrays of dword. The first indicates the level (0: dominant, 1: recessive) of the generators output for each time interval. The second describes the duration for each time interval.

## Parameters

- **channel**: Channel of the connected interface.
- **numIntervals**: Number of intervals described in the following arrays.
- **state**: For each time interval  
  0: dominant  
  1: recessive
- **duration100us**: Duration of interval with a resolution of 100 µs.

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

```plaintext
on key 's'
{
   // configure a rectangle wave with a period of 20 ms
   const long kEclSequenceLength = 8;
   dword eclSequenceStates[kEclSequenceLength] = { 0, 1, 0, 1, 0, 1, 0, 1};
   dword eclSequenceDuration[kEclSequenceLength] = { 100, 100, 100, 100, 100, 100, 100, 100};
   mostConfigureEclSequence(1, kEclSequenceLength, eclSequenceStates, eclSequenceDuration);
   // start generation of the sequence
   mostGenerateEclSequence(1, 1);
}

OnMostEclSequence(long state)
{
   if(state == 1)
   {
      write ("ECL Sequence Started!");
   }
   else
   {
      write ("ECL Sequence Stopped or Finished!");
   }
}
```

[mostGenerateEclSequence](CAPLfunctionMOSTGenerateEclSequence.md) • [mostSetEcl](CAPLfunctionMOSTSetGetEcl.md) • [OnMostEcl](../EventProcedures/CAPLfunctionOnMOSTEcl.md) • [mostSetEclTermination](CAPLfunctionMOSTSetGetEclTermination.md) • [OnMostEclSequence](../EventProcedures/CAPLfunctionOnMOSTEclSequence.md)
