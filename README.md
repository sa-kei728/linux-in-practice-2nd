# linux-in-practice-2nd

* 「Linuxのしくみ 増補改訂版」の実験コードです

## 実験プログラム実行環境の作成

* お手元のUbuntu 20.04環境で本書の実験プログラムを実行する際は、以下のコマンドを実行して必要パッケージのインストールおよびユーザ設定をしてください。

```console
$ sudo apt update && sudo apt install binutils build-essential golang sysstat python3-matplotlib python3-pil fonts-takao fio qemu-kvm virt-manager libvirt-clients virtinst jq docker.io containerd libvirt-daemon-system
$ sudo adduser `id -un` libvirt
$ sudo adduser `id -un` libvirt-qemu
$ sudo adduser `id -un` kvm
```

### WSL2での補足

* WSL2の場合, 素直にaptを動かすとqemu-kvmのVersionが合わない場合がある.

```console
$ sudo apt install qemu-kvm
The following packages have unmet dependencies:
 qemu-kvm : Depends: qemu-system-x86 (= 1:5.0-5ubuntu9.6~backport20.04-202102230209~ubuntu20.04.1) but it is not going to be installed
E: Unable to correct problems, you have held broken packages.
```

* 以下のコマンドを指定するなど, ディストリビューション指定のVersionを取り込む.

```console
$ sudo apt install qemu-system-x86=1:4.2-3ubuntu6.24 qemu-kvm=1:4.2-3ubuntu6.24
```

## python実行方法.

* pyenvでPython3.11.2を取得.

```console
pyenv install 3.11.2
```
