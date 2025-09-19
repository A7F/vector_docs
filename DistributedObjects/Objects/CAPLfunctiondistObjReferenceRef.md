# distObjReferenceRef

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Function Syntax

- `distObjReferenceRef *`
- `distObjReferenceRef <Interface>`

### Method Syntax

- [distObjReferenceRef *::ResetTarget](../Methods/CAPLfunctiondistObjReferenceRefResetTarget.md)
- [distObjReferenceRef *::SetTargetByPath](../Methods/CAPLfunctiondistObjReferenceRefSetTargetByPath.md)
- [distObjReferenceRef `<Interface>`::SetTarget](../Methods/CAPLfunctiondistObjReferenceRefSetTarget.md)

### Description

References a reference to a distributed object that is derived from the given interface.

### Parameters

- **Interface**: The optionally qualified name of a distributed object interface. It is also possible to take the reverse of an interface by using the `reverse<…>` operator.

### Selectors

- **Name**: Name of the reference.  
  Type: `char[]`  
  Access Limitation: Read only

- **Path**: Path of the reference.  
  Type: `char[]`  
  Access Limitation: Read only

- **IsValid**: 1 if a valid reference is referenced, 0 otherwise.  
  Type: `dword`  
  Access Limitation: Read only

- **TargetPath**: Value handle for the path of the distributed object that is referenced.  
  Type: `valueHandle string`  
  Access Limitation: Read only

- **Target**: Referenced distributed object.  
  Type: `distObjRef <Interface>`  
  Access Limitation: Read only

- **HasTarget**: 1 if the reference has a valid target, 0 otherwise.  
  Type: `dword`  
  Access Limitation: Read only

- **<Member Name>**: Access to a member of the reference.  
  Type: `<MemberType>`  
  Access Limitation: Read only

### Example

```c
// vCDL
version 1.3;
namespace SomeNamespace {
  interface SomeInterface {
    internal data int32 d;
  }
  object Obj : SomeInterface {}
  reference<SomeInterface> Ref;
}

// CAPL
on start {
  UseVariable();
  AccessTarget();
  AccessMember();
}

void UseVariable() {
  // variable declarations
  distObjReferenceRef * r1;
  distObjReferenceRef SomeInterface r2 = Ref;

  // check if a valid reference is referenced
  write("%d", r1.IsValid); // output: 0
  write("%d", r2.IsValid); // output: 1

  // type conversions (checked at runtime)
  r1 = r2;                                    // implicit upcast
  r2 = (distObjReferenceRef SomeInterface)r1; // explicit downcast

  // check the name and path of the reference
  write("%s", r1.Name); // output: Ref
  write("%s", r1.Path); // output: SomeNamespace::Ref
}

void AccessTarget() {
  // set the target directly (not possible at wildcard reference)
  Ref.SetTarget(Obj);

  // reset the target
  Ref.ResetTarget();

  // reset the target with empty string
  Ref.SetTargetByPath("");

  // set the target via its fully qualified path
  Ref.SetTargetByPath("SomeNamespace::Obj");

  // check if the reference target is valid
  write("%d", Ref.HasTarget);      // output: 1
  write("%d", Ref.Target.IsValid); // output: 1

  // access the reference target path
  write("%s", $Ref.TargetPath); // output: SomeNamespace::Obj
  write("%s", Ref.Target.Path); // output: SomeNamespace::Obj
}

void AccessMember() {
  // set the member at the reference
  $Ref.d = 42;
  write("%d = %d", $Obj.d, $Ref.d); // output: 42 = 42
}

on value_update Ref.TargetPath {
  write("Target of Ref was updated to: \"%s\"", $this);
}
on value_change Ref.TargetPath {
  write("Target of Ref was changed to: \"%s\"", $this);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)
