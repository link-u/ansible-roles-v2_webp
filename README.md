# webp

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
webp_download_url: "https://storage.googleapis.com/downloads.webmproject.org/releases/webp/{{ webp_dirname }}.tar.gz"
webp_prefix: "/usr/local"
webp_download_dest: "{{ webp_prefix }}/src"
```

### Example playbook

```yaml
- hosts:
    - servers
  become: True
  roles:
    - { role: webp, tags: ["webp"] }
```




