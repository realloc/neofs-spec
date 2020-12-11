## String presentation encoding and decoding

In NeoFS there are some data types that may be presented in various formats in
different parts of the system. Here we specify how they are supposed to be
encoded and decoded.

For detailed documentation of each type please see the API reference section.

### ObjectID

`ObjectID` is a 32 byte long
[SHA256](https://csrc.nist.gov/publications/detail/fips/180/4/final) hash of
it's stable-marshaled header in protobuf format, which, in it's turn, contains a
hash of object's payload.

String presentation is
[base58](https://tools.ietf.org/html/draft-msporny-base58-02) encoded string.

### ContainerID

`ContainerID` is a 32 byte long SHA256 hash of a stable-marshaled container
structure in protobuf format.

String presentation is base58 encoded string.

### OwnerID

`OwnerID` is a derivative of a user's main public key in a format of [Neo3
address](https://docs.neo.org/v3/docs/en-us/tooldev/wallets.html#address). 

In binary format it's a 25 bytes sequence starting with Neo version prefix byte,
then 20 bytes of ScrptHash and 4 bytes of checksumm.

String presentation is [Base58
Check](https://en.bitcoin.it/wiki/Base58Check_encoding) Encoded string.

### Object Address

In NeoFS objects are addressed by their `ContainerID` and `ObjectID`.

In binary form is a 64 bytes sequence starting with 32 bytes of `ContainerID`
followed by `ObjectID`.

String presentation of `Object Address` is a concatenation of string encoded
`ContainerID` and `ObjectID` delimited by '/' character.

### Format versions

### Object payload hash

### Object payload homomorphic hash

### Object type

### Object SplitID


