# cryptostore-use-crypton

This repo reproduces a bug where [dependencies behind a cabal flag](https://github.com/ocheron/cryptostore/blob/1c52dd5fc7c0184cfae0e09e305bef54a04854a4/cryptostore.cabal#L68-L71) aren't passed to the derivation of `cryptostore` leading to:
```sh
> Using Parsec parser
       > Configuring cryptostore-0.3.1.0...
       > CallStack (from HasCallStack):
       >   withMetadata, called at libraries/Cabal/Cabal/src/Distribution/Simple/Utils.hs:368:14 in Cabal-3.10.3.0:Distribution.Simple.Utils
       > Error: Setup: Encountered missing or private dependencies:
       > crypton, crypton-x509, crypton-x509-validation
       >
```

## Reproduce

```sh
nix develop github:shivaraj-bh/cryptostore-use-crypton
```



