---
published: false
---
We have a great feature in the SushiChain command line which applies to all three of the binaries - `sushi`, `sushid` and `sushim`

In the `sushi` client there is a command called `config`

```
available sub actions
 - save                 | save the specified options as default for sushi, sushid and sushim
 - show                 | show current default configuration
 - clean                | clean the default configuration
 ```
 
This allows you to save a default set of command line flags when using the command line. For all the binaries you have to supply various flags such as the connecting node `-n` and the wallet `-w`. But if you use the same values for these flags all the time then using config means you don't have to pass them.
 
If you do pass any of the flags then the passed values overwrite the stored ones. This makes it very flexible and easy to use. The config is stored in `~/.sushi/config`

Consider this example:

```
sushi tx create -m 100 -f 1 -w wallets/w1.json -n http://testnet.sushichain.io:3000 -a some-address --testnet --password=password
```

Saving the following config:

```
sushi config save -w wallets/w1.json -n http://testnet.sushichain.io:3000 --testnet --password=password
```

Means you can shorten the command line to this:

```
sushi tx create -mn 100 -f 1 -a some-address
```

This is much shorter and vastly easier to use. We hope you like the config feature and start using it!
