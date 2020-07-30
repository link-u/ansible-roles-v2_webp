# webp

![ansible ci](https://github.com/link-u/ansible-roles-v2_webp/workflows/ansible%20ci/badge.svg)

## 概要

webp をインストール ansible role
現在はビルドしてインストールしている.

## 使い方 (ansible)

### Role variables

```yaml
### インストール設定 ###############################################################################
## 基本設定
webp_install_flag: True  # インストールフラグ

## make install していた名残の変数.
#  * deb に以降する際に make install したファイルを掃除するのに以下の変数は必要
#  * 特に group_vars で修正するような項目はない
webp_version: 1.0.0
webp_download_url: "https://storage.googleapis.com/downloads.webmproject.org/releases/webp/libwebp-{{ webp_version }}.tar.gz"
webp_prefix: "/usr/local"
```

### Example playbook

```yaml
- hosts:
    - servers
  become: True
  roles:
    - { role: webp, tags: ["webp"] }
```

## 後方互換性について

### 削除された変数の一覧

deb パッケージでのインストールに移行したため以下の変数は `group_vars` から削除して頂いて大丈夫です.

* `webp_dirname`
* `webp_install_dest`
* `webp_download_dest`

## License
MIT
