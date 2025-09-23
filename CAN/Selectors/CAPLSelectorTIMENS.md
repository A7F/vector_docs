
## Example Selector TIME_NS (time stamp of message in nanoseconds)

- **Type**: int64 (signed 64 bit integer) – only readable.

```plaintext
On message CAN1.100 {
  Write("CAN – Frame with time %I64d received", this.time_ns);
}
```

- Technical References are only available in English
- Build Time: 2024-10-8T21:20:34
