###########

[![build](https://github.com/FuelLabs/fuels-rs/actions/workflows/ci.yml/badge.svg)](https://github.com/FuelLabs/fuels-rs/actions/workflows/ci.yml)
[![crates.io](https://img.shields.io/crates/v/fuels?label=latest）](https://crates.io/crates/fuels）
[![ドキュメント](https://docs.rs/fuels/badge.svg）](https://docs.rs/fuels）
[![discord](https://img.shields.io/badge/chat%20on-discord-orange?&logo=discord&logoColor=ffffff&color=7389D8&labelColor=6A7EC2)](https://discord.gg/xfpK4Pe)

燃料のための錆SDK。 これは、以下を含むがこれらに限定されない、様々なものに使用することができます:

-コンパイル、デプロイ、およびテスト[Sway](https://github.com/FuelLabs/sway）契約書;
-ローカル燃料ネットワークの立ち上げ;
-手作りのスクリプトや契約コールで取引を作成し、署名する;
-コントラクトメソッドのタイプセーフなRustバインディングの生成;
-そして、より多くの、"燃料-rsは"積極的な開発にまだあります。

##ドキュメント

を参照してください[`燃料-rs`の本](https://fuellabs.github.io/fuels-rs/latest/)

#＃特長

-[x]燃料ノードの起動
-[×]契約を展開する
-[x]展開された契約との対話
-[x]タイプセーフSway contractsバインディングコード生成
-[x]Swayスクリプトを実行する
-[x]一般的な操作のためのCLI
-[×]ローカルテスト
-[編集]ウォレット統合
-[]イベントのクエリ/監視

##よくある質問

###どのような依存関係が必要ですか？

-[最新の"安定した"Rustツールチェーン](https://docs...燃料だネットワーク/ガイド/インストール/#インストール-錆）;
-['forc'と`fuel-core'バイナリ](https://docs...燃料だネットワーク/ガイド/インストール/#installing-the-fuel-toolchain-using-fuelup)。

##＃SDKテストを実行するにはどうすればよいですか？

まず、`forc'を使用してテストプロジェクトをビルドします:

"'シェル
forc build--pathパッケージ/燃料
```

次に、SDKテストを次のように実行できます:

"'シェル
貨物検定
```

特定のテストを実行することもできます。 次の例では、すべての統合テストを`'で実行しますtypes.rs`その名前に`in_vector'が含まれ、その出力を表示します:

"'シェル
貨物テスト--テストタイプin_vector----show-output
```
##＃WASMテストを実行する方法は？
まだない場合は、wasm32をターゲットとして使用する必要があります:
"'シェル
rustupターゲット追加wasm32-unknown-unknown
```
まだない場合は、`wasm-pack`も必要です:
"'シェル
貨物はwasmパックを取付けます
```

`Packages/wasm-tests`に移動し、`wasm-pack test`を実行します。
##＃私のテストが`master`で失敗した場合の対処方法

他に何かをする前に、これらすべてのコマンドを試してください:

"'シェル
カーゴクリーン
rmカーゴロック
forc build--pathパッケージ/燃料
貨物検定
```

###接頭辞`fuels`と`fuel`ではないのはなぜですか？

燃料のためのSDKをから来るそれらによく知られている感じにさせるために[ethers.js](https://github.com/ethers-io/ethers.js）エコシステム、このプロジェクトは、最後に"s"を選択しました。 Sdkの「fuels-*」ファミリーは、エーテルプロジェクトに触発されています。

###ドキュメントをローカルで実行するにはどうすればよいですか？

実行して`mdbook'をインストールします:

"'シェル
cargoインストールmdbook
```

次に、'docs'フォルダに移動し、以下のコマンドを実行してローカルサーバーを起動し、ブラウザで新しいタブを開きます。

"'シェル
mdbook serve--open
```

次のコマンドを実行して本を構築できます:

"'シェル
mdbookビルド
```
フールエコ


# fuels-rs

[![build](https://github.com/FuelLabs/fuels-rs/actions/workflows/ci.yml/badge.svg)](https://github.com/FuelLabs/fuels-rs/actions/workflows/ci.yml)
[![crates.io](https://img.shields.io/crates/v/fuels?label=latest)](https://crates.io/crates/fuels)
[![docs](https://docs.rs/fuels/badge.svg)](https://docs.rs/fuels)
[![discord](https://img.shields.io/badge/chat%20on-discord-orange?&logo=discord&logoColor=ffffff&color=7389D8&labelColor=6A7EC2)](https://discord.gg/xfpK4Pe)

Rust SDK for Fuel. It can be used for a variety of things, including but not limited to:

- Compiling, deploying, and testing [Sway](https://github.com/FuelLabs/sway) contracts;
- Launching a local Fuel network;
- Crafting and signing transactions with hand-crafted scripts or contract calls;
- Generating type-safe Rust bindings of contract methods;
- And more, `fuels-rs` is still in active development.

## Documentation

See [the `fuels-rs` book](https://fuellabs.github.io/fuels-rs/latest/)

## Features

- [x] Launch Fuel nodes
- [x] Deploy contracts
- [x] Interact with deployed contracts
- [x] Type-safe Sway contracts bindings code generation
- [x] Run Sway scripts
- [x] CLI for common operations
- [x] Local test wallets
- [ ] Wallet integration
- [ ] Events querying/monitoring

## FAQ

### What dependencies do I need?

- [The latest `stable` Rust toolchain](https://docs.fuel.network/guides/installation/#installing-rust);
- [`forc` and `fuel-core` binaries](https://docs.fuel.network/guides/installation/#installing-the-fuel-toolchain-using-fuelup).

### How can I run the SDK tests?

First, build the test projects using `forc`:

```shell
forc build --path packages/fuels
```

Then you can run the SDK tests with:

```shell
cargo test
```

You can also run specific tests. The following example will run all integration tests in `types.rs` whose names contain `in_vector` and show their outputs:

```shell
cargo test --test types in_vector -- --show-output
```
### How to run WASM tests?
You need to have wasm32 as a target, if you don't already:
```shell
 rustup target add wasm32-unknown-unknown
```
You also need `wasm-pack`, if you don't already:
```shell
cargo install wasm-pack
```

Navigate to `packages/wasm-tests` and run `wasm-pack test`.
### What to do if my tests are failing on `master`

Before doing anything else, try all these commands:

```shell
cargo clean
rm Cargo.lock
forc build --path packages/fuels
cargo test
```

### Why is the prefix `fuels` and not `fuel`?

In order to make the SDK for Fuel feel familiar with those coming from the [ethers.js](https://github.com/ethers-io/ethers.js) ecosystem, this project opted for an `s` at the end. The `fuels-*` family of SDKs is inspired by The Ethers Project.

### How can I run the docs locally?

Install `mdbook` by running:

```shell
cargo install mdbook
```

Next, navigate to the `docs` folder and run the command below to start a local server and open a new tab in you browser.

```shell
mdbook serve --open
```

You can build the book by running:

```shell
mdbook build
```
FURL eco
