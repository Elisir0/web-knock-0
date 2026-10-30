## 課題18：レスポンスのContent-Typeを調べる
` curl -sI <URL> | grep -i '^content-type:' | cut -d' ' -f2-` コマンドを使って、レスポンスの Content-Type を取得する．
- curlを用いてHTTPレスポンスヘッダーを取得する
- grepでContent-Typeの行だけを抽出する
- cutで「Content-Type:」を除き、値だけを取得する


リソースタイプ、URL、Content-TypeをMarkdown形式で1行にまとめて出力する．
複数のリソースについて、リソースタイプとURLを定義し、Markdown形式の表として一括出力する．
```
# Markdown形式の表のヘッダーを出力する
echo "| リソースタイプ | URL | Content-Type |"
echo "| :--- | :--- | :--- |"

# テスト対象となるリソースの種類とURLを定義する
for item in \
  "HTML|https://example.com" \
  "HTML|https://httpbin.org/html" \
  "JSON|https://httpbin.org/json" \
  "JPEG画像|https://httpbin.org/image/jpeg" \
  "PNG画像|https://httpbin.org/image/png" \
  "SVG画像|https://httpbin.org/image/svg" \
  "WEBP画像|https://httpbin.org/image/webp" \
  "AVIF画像|https://httpbin.org/image/avif" 
do
  # 「|」を区切り文字として、リソースの種類とURLに分割する
  type="${item%%|*}"
  url="${item#*|}"

  ct=$(curl -sI "$url" | grep -i '^content-type:' | tr -d '\r' | cut -d' ' -f2-)
  # tr -d '\r'でHTTPヘッダーに含まれる'\r'を削除する
  echo "| $type | \`$url\` | \`$ct\` |"
done
```
実行結果は以下となります．
```
| リソースタイプ | URL | Content-Type |
| :--- | :--- | :--- |
| HTML | `https://example.com` | `text/html; charset=utf-8` |
| HTML | `https://httpbin.org/html` | `text/html; charset=utf-8` |
| JSON | `https://httpbin.org/json` | `application/json` |
| JPEG画像 | `https://httpbin.org/image/jpeg` | `image/jpeg` |
| PNG画像 | `https://httpbin.org/image/png` | `image/png` |
| SVG画像 | `https://httpbin.org/image/svg` | `image/svg+xml` |
| WEBP画像 | `https://httpbin.org/image/webp` | `image/webp` |
| AVIF画像 | `https://httpbin.org/image/avif` | `image/avif` |
```
| リソースタイプ | URL | Content-Type |
| :--- | :--- | :--- |
| HTML | `https://example.com` | `text/html; charset=utf-8` |
| HTML | `https://httpbin.org/html` | `text/html; charset=utf-8` |
| JSON | `https://httpbin.org/json` | `application/json` |
| JPEG画像 | `https://httpbin.org/image/jpeg` | `image/jpeg` |
| PNG画像 | `https://httpbin.org/image/png` | `image/png` |
| SVG画像 | `https://httpbin.org/image/svg` | `image/svg+xml` |
| WEBP画像 | `https://httpbin.org/image/webp` | `image/webp` |
| AVIF画像 | `https://httpbin.org/image/avif` | `image/avif` |