[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/CAPLfunctionsTSLStimulusCsvFile.md)

[CAPL Functions](../CAPLfunctions.md) » [Test Service Library](CAPLfunctionsTSLStimulusOverview.md) » Stimulus Generator: CSV File as Data Source

# Stimulus Generator: CSV File as Data Source

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

This generator takes values for updating the data sink (signal or environment variable) from a CSV file. Output of all values from the CSV file defines one period **T** of the Stimulus Generator. These periods are automatically repeated. The [Reset Function](Functions/CAPLfunctionStmControlStartStopResetDestroy.md) causes a new period to begin immediately, i.e. values are taken from the beginning of the CSV file again.  
If a Cycle Time is specified for generation by the Stimulus Generator, the data sink is updated periodically with the next value from the CSV file.  
If the Stimulus Generator is operating non periodically, the time stamps associated with the values are taken from the CVS file to control updating of the data sink. The format of the CSV file is exactly the same in both cases.

## First Example of a csv file:

```
Time,DB1::Msg1::Sig1,Msg2::Sig2,Sig3
0.500000,0.000000,1.000000,0.000000
0.800000,,2.000000,
1.000000,0.000000,3.000000,
1.700000,,4.000000,
1.800000,0.000000,5.000000,
2.000000,,6.000000,
```

## Non-cyclical

**Note**  
The time stamps are absolute data in reference to the start of a new period.

## Cyclical

**Note**  
File format: Two backslashes "\\" or one forward slash "/" must be inserted after the drive characters and between the folders, e.g.:

- `C:\\path\\to\\the\\file\\testfile.csv`

or

- `C:/path/to/the/file/testfile.csv`

There are various restrictions with regard to formatting the CSV file. These restrictions are derived from [Trace Window Export Options](CAPLfunctionsTSLRequirementStimuli.md).

## Second Example of a csv file: (same effect as first example)

```
Time , DB1::Msg1::Sig1, Msg2::Sig2, Sig3
50000 , 0.000000 , 1.000000 , 0.000000
80000 , , 2.000000 ,
100000 , 0.000000 , 3.000000 ,
1.700000; ; 4.000000 ;
1.800000; 0.000000 ; 5.000000 ;
2.000000; ; 6.000000 ;
```

**Note**

- Blank characters are ignored
- Time data without decimal point is interpreted as time x 10 µs, e.g. 50000 = 0.5 s
- Time data with decimal point is interpreted as time in seconds, e.g. 1.800000 = 1.8 s
- You can also specify the time unit in the header of the CSV file, e.g. [s] or [µs]:

```
Time[s],DB1::Msg1::Sig1,Msg2::Sig2,Sig3
0.500000,0.000000,1.000000,0.000000
1,0.000000,3.000000,
1.700000,,4.000000,
2,,6.000000,
```

-> time data: 0.5 s, 1 s, 1.7 s, 2 s

## Functions that create the Stimulus Generator for stimulating signals and environment/system variables

- [StmCreate_CSV](Functions/CAPLfunctionStmCreateCsvNonCyclical.md) (non-cyclical)
- [StmCreate_CSV](Functions/CAPLfunctionStmCreateCsvCyclical.md) (cyclical)
