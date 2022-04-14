$ hs-airdrop -h

  hs-airdrop (v0.7.0)

  This tool will create the proof necessary to
  collect your faucet reward, airdrop reward, or
  sponsor reward on the Handshake blockchain.

  Usage: $ hs-airdrop [key-file] [id] [addr] [options]
         $ hs-airdrop [key-file] [addr] [options]
         $ hs-airdrop [addr]

  Options:

    -v, --version         output the version number
    -b, --bare            redeem airdrop publicly (i.e. without goosig)
    -f, --fee <amount>    set fee for redemption (default: 0.1)
    -d, --data <path>     data directory for cache (default: ~/.hs-tree-data)
    -h, --help            output usage information

  [key-file] can be:

    - An SSH private key file.
    - An exported PGP armor keyring (.asc).
    - An exported PGP raw keyring (.pgp/.gpg).

  [id] is only necessary for PGP keys.

  [addr] must be a Handshake bech32 address.

  The --bare flag will use your existing public key.
  This is not recommended as it makes you identifiable
  on-chain.

  This tool will provide a JSON representation of
  your airdrop proof as well as a base64 string.

  The base64 string must be passed to:
    $ hsd-rpc sendrawairdrop "base64-string"

  Examples:

    $ hs-airdrop ~/.gnupg/secring.gpg 0x12345678 hs1q5z7yyk8xrh4quqg3kw498ngy7hnd4sruqyxnxd -f 0.5
    $ hs-airdrop ~/.ssh/id_rsa hs1q5z7yyk8xrh4quqg3kw498ngy7hnd4sruqyxnxd -f 0.5
    $ hs-airdrop ~/.ssh/id_rsa hs1q5z7yyk8xrh4quqg3kw498ngy7hnd4sruqyxnxd -f 0.5 --bare
    $ hs-airdrop hs1q5z7yyk8xrh4quqg3kw498ngy7hnd4sruqyxnxd
