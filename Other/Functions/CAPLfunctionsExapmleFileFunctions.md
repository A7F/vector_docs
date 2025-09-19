[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionsExapmleFileFunctions.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » Example: File Functions

# Example: File Functions

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Example fileGetBinaryBlock

```plaintext
variables
{
  msTimer writeTimer;
  long glbPeriod = 250;

  dword glbHandle = 0;
  struct Data
  {
    long value;
  }
  glbData;
}

on Start
{
  byte buffer[4];
  long ret;

  //
  // Opens the file in binary mode for read access.
  //
  // To determine the absolute path, the search procedure will be used.
  // The file must be located in the directory of the databases or the
  // configuration directory.
  //
  glbHandle = OpenFileRead ("Data.Bin",1);

  if ( glbHandle!=0 )
  {
    //
    // got to end of file ...
    //
    while ( fileGetBinaryBlock(buffer,elcount(buffer),glbHandle)!=0 ) {};
    //
    // Get the last parameters
    // (saved on disk after the end of the last measurement)
    //
    memcpy(glbData, buffer);
    write ("Last value %d.",glbData.value);
    fileClose (glbHandle);
  }
  else
  {
    write ("File 'Data.Bin' was not opened for read access.");
  }
  //
  // Open the file in binary mode for write access.
  //
  // The write path was not set using the function setWritePath(), so
  // the configuration directory will be used instead. This is the
  // default behavior.
  //
  glbHandle = OpenFileWrite ("Data.Bin",3);

  if ( glbHandle!=0 )
  {
    setTimer (writeTimer,glbPeriod);
  }
  else
  {
    write ("File 'Data.Bin' was not opened for write access.");
  }
}

on timer writeTimer
{
  struct Data randomValue;
  byte buffer [4];

  if ( glbHandle!=0 )
  {
    randomValue.value = random (32767);
    memcpy(buffer, randomValue);
    fileWriteBinaryBlock (buffer, elcount(buffer),glbHandle);
    write("Last value written: %d", randomValue.value);
    setTimer (writeTimer,glbPeriod);
  }
  else
  {
    write ("Error, invalid file handle.");
  }
}

on StopMeasurement
{
  fileClose (glbHandle);
}
```

## Example fileGetString

```plaintext
variables
{
  msTimer writeTimer;
  long glbPeriod = 250;

  dword glbHandle = 0;
  long glbValue;
}

on Start
{
  char buffer[64];
  long ret;

  //
  // Opens the file in ASCII mode for read access.
  //
  // To determine the absolute path, the search procedure will be used.
  // The file must be located in the directory of the databases or the
  // configuration directory.
  //
  glbHandle = OpenFileRead ("Data.Txt",0);

  if ( glbHandle!=0 )
  {
    //
    // got to end of file ...
    //
    while ( fileGetString(buffer,elcount(buffer),glbHandle)!=0 ) {};
    //
    // Get the last parameters
    // (saved on disk after the end of the last measurement)
    //
    glbValue = atol (buffer);
    write ("Last value %d.",glbValue);
    fileClose (glbHandle);
  }
  else
  {
    write ("File 'Data.Txt' was not opened for read access.");
  }
  //
  // Open the file in ASCII mode for write access.
  //
  // The write path was not set using the function setWritePath(), so
  // the configuration directory will be used instead. This is the
  // default behavior.
  //
  glbHandle = OpenFileWrite ("Data.Txt",2);

  if ( glbHandle!=0 )
  {
    setTimer (writeTimer,glbPeriod);
  }
  else
  {
    write ("File 'Data.Txt' was not opened for write access.");
  }
}

on timer writeTimer
{
  long randomValue;
  char buffer [64];

  if ( glbHandle!=0 )
  {
    randomValue = random (32767);
    snprintf (buffer,elcount(buffer)," %d \n",randomValue);
    filePutString (buffer, elcount(buffer),glbHandle);
    setTimer (writeTimer,glbPeriod);
  }
  else
  {
    write ("Error, invalid file handle.");
  }
}

on StopMeasurement
{
  fileClose (glbHandle);
}
```

## Example fileGetStringSZ

```plaintext
variables
{
  msTimer writeTimer;
  long glbPeriod = 250;

  dword glbHandle = 0;
  long glbValue;
}

on Start
{
  char buffer[64];
  long ret;

  //
  // Opens the file in ASCII mode for read access.
  //
  // To determine the absolute path, the search procedure will be used.
  // The file must be located in the directory of the databases or the
  // configuration directory.
  //
  glbHandle = OpenFileRead ("Data.Txt",0);

  if ( glbHandle!=0 )
  {
    //
    // got to end of file ...
    //
    while ( fileGetStringSZ(buffer,elcount(buffer),glbHandle)!=0 ) {};
    //
    // Get the last parameters
    // (saved on disk after the end of the last measurement)
    //
    glbValue = atol (buffer);
    write ("Last value %d.",glbValue);
    fileClose (glbHandle);
  }
  else
  {
    write ("File 'Data.Txt' was not opened for read access.");
  }
  //
  // Open the file in ASCII mode for write access.
  //
  // The write path was not set using the function setWritePath(), so
  // the configuration directory will be used instead. This is the
  // default behavior.
  //
  glbHandle = OpenFileWrite ("Data.Txt",2);

  if ( glbHandle!=0 )
  {
    setTimer (writeTimer,glbPeriod);
  }
  else
  {
    write ("File 'Data.Txt' was not opened for write access.");
  }
}

on timer writeTimer
{
  long randomValue;
  char buffer [64];

  if ( glbHandle!=0 )
  {
    randomValue = random (32767);
    snprintf (buffer,elcount(buffer)," %d \n",randomValue);
    filePutString (buffer, elcount(buffer),glbHandle);
    setTimer (writeTimer,glbPeriod);
  }
  else
  {
    write ("Error, invalid file handle.");
  }
}

on StopMeasurement
{
  fileClose (glbHandle);
}
```

•  Technical References are only available in English

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
