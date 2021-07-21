# NeoC-sample-project

[RotationE/NeoC](https://github.com/RotationE/NeoC)をCMakeから利用するサンプルプロジェクト

## build

buildフォルダを作成する。

```sh
$ mkdir build
$ cd build
```

ビルド環境を作成し、ビルドする。NeoCライブラリはGCC拡張機能を利用しているので、コンパイラには`gcc`を利用する必要がある。
そのため、デフォルトで利用するコンパイラが`gcc`ではない場合は、以下のように`CMAKE_C_COMPILER`を定義する。

```sh
# CMakeによって自動で検出したコンパイラを利用する場合(gccではない可能性がある)
$ cmake ..

# コンパイラを指定する場合(ここでは/usr/bin/gccを指定している)
$ cmake .. -DCMAKE_C_COMPILER=/usr/bin/gcc
```

```sh
$ make
```

生成した実行ファイルを実行する。

```
$ cd build/src
$ ./main
```
