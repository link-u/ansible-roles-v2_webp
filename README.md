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
webp_version: 1.0.0
webp_dirname: "libwebp-{{ webp_version }}"
webp_download_url: "https://storage.googleapis.com/downloads.webmproject.org/releases/webp/{{ webp_dirname }}.tar.gz"
webp_prefix: "/usr/local"
webp_download_dest: "{{ webp_prefix }}/src"
webp_install_dest: "{{ webp_prefix }}"
```

### Example playbook

```yaml
- hosts:
    - servers
  become: True
  roles:
    - { role: webp, tags: ["webp"] }
```




