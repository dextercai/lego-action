# lego-action

use lego to issue ssl certificate

## HOW TO USE
```
jobs:
  issue-ssl-certificate:
    name: Issue SSL certificate
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: dextercai/lego-action@main
        with:
          version: latest
          accounts-tar-base64: ${{ secrets.LEGO_ACCOUNT_TAR }}
          lego-envs: ALICLOUD_ACCESS_KEY=${{ secrets.ALI_AK }},ALICLOUD_SECRET_KEY=${{ secrets.ALI_SK }}
          email: you@exmple.com
          lego-dns-provider: alidns
          domains: "*.example,com*"
          dns-resolvers: 1.1.1.1:53
```