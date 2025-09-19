# CANstressOnFinished

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```
long CANstressOnFinished( char fnctCallback[] );
```

## Description

Registers a CAPL function as callback that is called if CANstress is switched into the state **Finished**.

## Parameters

- **fnctCallback**: Name of the function that should be used as callback.

  **Note**
  - The callback functions must correspond to the following syntax: `long FunctionName ( dword );`
  - Should the CAPL function used as callback not longer be called when CANstress changes into the **Finished** condition, an empty string must be passed as parameter to [CANstressOnPending](CAPLfunctionCANstressIsPending.md).

  ```
// delete or switch off present callback
CANstressOnFinished( " " );

  ```

## Return Values

- **0**: On successful call.

## Example

—
