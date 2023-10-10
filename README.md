# コードの実行例

## コンテナのビルド
このファイルのあるディレクトリ上で

``` bash
$ docker build . -t convert_pdf
```

## 使用例

```bash
$ docker run --rm -v $(pwd):/tmp convert_pdf convert_pdf  pandoc -t html5 /tmp/hoge.md --extract-media=/tmp/  --self-contained --output=/tmp/hoge.pdf
```

ファイル指定しない例
```bash
$ for f in *.md; do docker run --rm -v $(pwd):/tmp  convert_pdf  pandoc -t html5 /tmp/${f} --extract-media=/tmp/  --self-contained --output=/tmp/${f}.pdf ;done
```
