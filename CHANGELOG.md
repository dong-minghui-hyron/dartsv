## 1.0.1
Resolved Null-safety warnings on project build

Building an example project threw up some warnings related to the  
pointycastle primitives and null-safety. I've made modifications to library  
implementation to resolve these compiler warnings.

## 1.0.0
- Null-Safety Update
- All dependencies have been upgraded or replaced with null-safe equivalents. 
- Minimum Dart version is now 2.12.2 

## 0.4.3
- Bugfix: Padded s-values to prevent invalid signatures
- Bugfix: Force 256-bit Private Keys to prevent invalid WIF exports
- Update: Updated example code to import latest major version of lib

## 0.4.2
- Bugfix: DataBuilder has script construction error for PUSHDATA transactions. 

## 0.4.1
- Bugfix: Bitcoin-Signed-Messages sometimes generate Signatures with short r-values of only 62 bytes length. This causes compact signatures to fail verification. This is now fixed. 

## 0.4.0
- Fixed a script behaviour bug. When using "add()" to update the SVScript's 
  contents the "toHex()" method failed to serialize the additional content. 
- Added a method to support generic data-only Locking Script Builders. 
- Upgraded the cryptographic library dependency to the new PointyCastle 2.0.1 


## 0.3.3
- Added Electrum-style ECIES (elliptic curve integrated encryption scheme) support

## 0.3.2
- API Exports
- Bug fix on testnet address encoding length
- DataBuilder modifications
- Added detection to TransactionOutput for P2PKH output
- Downgraded the required SDK version to 2.7.0. Aqueduct chokes on Dart 2.8+

## 0.3.1
New Feature
- Added DataLockBuilder to allow composing a simple data output script

Bug Fixes
- Bug fix submited by chen610620 for index bug on signing Transaction Inputs. The bug prevented signing of inputs other than the first one. 

## 0.3.0
This represents a rather major refactor of the way in which the Script Builder   
interface works. I have completely decoupled the creation of Custom Scripts   
from the SDK internals.

*NOTE:* This release is not backwards-compatible with earlier versions   
of the SDK, and contains breaking changes. Please see below.

#### What's New
- P2PKHUnlockBuilder, P2PKHLockBuilder
- P2MSUnlockBuilder, P2MSLockBuilder
- P2SHUnlockBuilder, P2SHLockBuilder
- P2PKLockBuilder, P2PKUnlockBuilder
- Deep refactor of the way that TransactionInput processes scriptSig
- Bugfix related to script serialization
- New API on SVScript to parse and serialize to ASM format
- Resolved one bitcoind MultiSig test vector which failed to pass (it was the last holdout)

Please note that this update makes small but important changes to how one composes a   
Transaction instance in conjunction with an UnlockingScriptBuilder and a LockingScriptBuilder   
instance. Review the example code and test cases to familiarize yourself with the new API.

## 0.2.5-RC1
- Added CLI example app

## 0.2.4-RC1
- Additional test coverage for Signatures
- Minor code refactor to improve code readability in line with linter suggestions

## 0.2.3-RC1
- Minor code refactor to improve code readability in line with linter suggestions

## 0.2.1-RC1
- Minor code refactor to improve code readability in line with linter suggestions

## 0.2.0-RC1
- Completed the API documentation
- Small API changes and cleanup

## 0.1.0-RC1
- Library is now functionally complete
- Script Interpreter Implementation is complete
- Handling of Raw Blocks has been implemented
- Bip39 mnemonics now has complete test coverage
- Minor updates to various APIs

## 0.1.0-alpha2

- Added support for contributed Bip39 mnemonics
- Added support for Bitcoin Signed Messages

## 0.1.0-alpha

- Initial Release
