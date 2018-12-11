# MILENAGE

MILENAGE algorithm implemented in the Go Programming Language.

# Quickstart

Compute OPc from K and OP.

```go
// initialize Milenage first with K, OP, RAND, SQN, and AMF.
mil := milenage.New(
    []byte{0x00, 0x11, 0x22, 0x33, 0x44, 0x55, 0x66, 0x77, 0x88, 0x99, 0xaa, 0xbb, 0xcc, 0xdd, 0xee, 0xff},
    []byte{0x00, 0x11, 0x22, 0x33, 0x44, 0x55, 0x66, 0x77, 0x88, 0x99, 0xaa, 0xbb, 0xcc, 0xdd, 0xee, 0xff},
    []byte{0x00, 0x11, 0x22, 0x33, 0x44, 0x55, 0x66, 0x77, 0x88, 0x99, 0xaa, 0xbb, 0xcc, 0xdd, 0xee, 0xff},
    0x000001,
    0x8000,
)

// get MAC-A by executing F1()
macA, err := mil.F1()
if err != nil {
    log.Fatal(err)
}

// get MAC-S by executing F1Star()
macS, err := mil.F1Star()
if err != nil {
    log.Fatal(err)
}

// get RES, CK, IK, AK by executing F2345()
res, ck, ik, ak, err := mil.F1()
if err != nil {
    log.Fatal(err)
}

// get OPc from K and OP. This is not the method on *Milenage.
opc, err := milenage.ComputeOPc(
    []byte{0x00, 0x11, 0x22, 0x33, 0x44, 0x55, 0x66, 0x77, 0x88, 0x99, 0xaa, 0xbb, 0xcc, 0xdd, 0xee, 0xff},
    []byte{0x00, 0x11, 0x22, 0x33, 0x44, 0x55, 0x66, 0x77, 0x88, 0x99, 0xaa, 0xbb, 0xcc, 0xdd, 
)
if err != nil {
    log.Fatal(err)
}
```

## Author

Yoshiyuki Kurauchi ([GitHub](https://github.com/wmnsk/) / [Twitter](https://twitter.com/wmnskdmms))

## License

[MIT](https://github.com/wmnsk/milenage/blob/master/LICENSE)