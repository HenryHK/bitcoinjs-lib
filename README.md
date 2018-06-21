# React Native Compatible Bitcoinjs-lib

This if a fork of [bitcoinjs-lib](https://github.com/bitcoinjs/bitcoinjs-lib) which improves compatibility with React Native for both iOS and Android. The based version of bitcoinjs-lib is v3.3.2.

## What this resolves

Since FB still uses a out-of-date in React Native, the `reverse()` function for `Buffer` doesn't work in RN. As a solution, this fork uses [buffer-reverse](https://github.com/crypto-browserify/buffer-reverse) instead. You can refer to this [issue](https://github.com/bitcoinjs/bitcoinjs-lib/issues/976).

## How to use

Add this line in your project dependencies:

```
"bitcoinlib-js": "git://github.com/HenryHK/bitcoinjs-lib#react-native-compatible"
```

Bitcoinjs-lib uses some node dependencies instead of react native dependencies. What I choose is to use [rn-nodeify](https://github.com/tradle/rn-nodeify).

Add this line to your `package.json`:

```
./node_modules/.bin/rn-nodeify --install buffer,events,process,stream,util,inherits,fs,path --hack
```

You may not need all the above core modules to be installed or need more.

Lastly, run

```
npm install
```