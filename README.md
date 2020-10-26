# South African Driver's License (SADL) Decryption

## Based on a [SO post](https://stackoverflow.com/a/40871714) by [SweetToe](https://stackoverflow.com/users/7226705)

The PDF417 barcode is 720 bytes. First 4 bytes indicate the version of barcode.

V1: `01 e1 02 45`

V2: `01 9b 09 45`

Next two bytes are zero. Remaining 714 bytes form 6 blocks - 5 blocks of 128, 1 block of 74.

## Usage
Different keys are used depending on version and and block size.

`openssl rsautl -inkey _128.key -pubin -in block_1.enc -raw > block_1.bin`

## Useful Links

* [Additional spec info](https://github.com/ugommirikwe/sa-license-decoder/blob/master/SPEC.md)

