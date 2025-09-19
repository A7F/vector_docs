# distObjMemberBlueprint::SetInitialValue

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

```plaintext
long distObjMemberBlueprint::SetInitialValue(T value);
```

## Description

Sets the initial value of the member blueprint. This method is only available for members that hold a value (data, non-void event, or field).

The parameter type depends on the type of the underlying member.

## Parameters

- **T**: Value

## Return Values

—

## Example

```plaintext
// vCDL
version 1.4;
namespace Test {
  struct S {
    int32 a;
  }
  typedef A = array<int32, 42>;

  interface X {
    internal data int32 i32;
    internal data int64 i64;
    internal data uint32 u32;
    internal data uint64 u64;
    internal data string s;
    internal data S t;
    internal data A a;
    internal data Y o;
  }
  interface Y {
    internal data int32 dummy;
  }
  Y Obj;
}

// CAPL
on key 'a' {
  stack distObjBlueprint Test::X bp = Test::X.CreateObjectBlueprint();
  array Test::A a;
  struct Test::S t;

  a[0] = 5;
  t.a = 6;

  bp.i32.SetInitialValue(-1);
  bp.i64.SetInitialValue(-2ll);
  bp.u32.SetInitialValue(3);
  bp.u64.SetInitialValue(4ll);
  bp.s.SetInitialValue("test");
  bp.a.SetInitialValue(a);
  bp.o.SetInitialValue(Test::Obj);
  bp.t.SetInitialValue(t);
  {
    distObjRef Test::X res;
    res = bp.CreateObject("Test::Result");
    write(
      "%d, %I64d, %u, %I64u, %s, %d, %s, %d",
      $res.i32,
      $res.i64,
      $res.u32,
      $res.u64,
      $res.s,
      $res.a[0],
      $res.o.Path,
      $res.t.a
    );
  }
}
```
