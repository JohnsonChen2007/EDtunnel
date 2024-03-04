# EDtunnel

<p align="center">
  <img src="https://cloudflare-ipfs.com/ipfs/bafybeigd6i5aavwpr6wvnwuyayklq3omonggta4x2q7kpmgafj357nkcky" alt="edgetunnel" style="margin-bottom: -50px;">
</p>

GitHub Repository for [https://github.com/zizifn/edgetunnel](https://github.com/zizifn/edgetunnel)

ask question and cloudflare ips: [https://t.me/edtunnel](https://t.me/edtunnel)

[![Repository](https://img.shields.io/badge/View%20on-GitHub-blue.svg)](https://github.com/zizifn/edgetunnel)

## available branches and explain

| Branch Name   | Description                                                   |
| ------------- | ------------------------------------------------------------- |
| remote-socks5 | Branch for remote SOCKS5 proxy pool used implementation       |
| socks5        | Branch for SOCKS5 proxyIP implementation                      |
| vless         | Branch for outbound VLESS protocol implementation             |
| vless2        | Branch for alternative outbound VLESS protocol implementation |
| code1         | Branch for code1 feature development                          |
| code2         | Branch for code2 alternative feature development              |
| dns           | Branch for DNS alternative related development                |
| main          | Main branch for the project                                   |
| pages         | New version for deployment on Cloudflare Pages                |

## Deploy in pages.dev

1. See YouTube Video:

   [https://www.youtube.com/watch?v=8I-yTNHB0aw](https://www.youtube.com/watch?v=8I-yTNHB0aw)

2. Clone this repository deploy in cloudflare pages.

## Deploy in worker.dev

1. Copy `_worker.js` code from [here](https://github.com/3Kmfi6HP/EDtunnel/blob/main/_worker.js).

2. Alternatively, you can click the button below to deploy directly.

   [![Deploy to Cloudflare Workers](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/3Kmfi6HP/EDtunnel)

## Lazy to deploy

`aHR0cHM6Ly9vc3MudjJyYXlzZS5jb20vcHJveGllcy9kYXRhLzIwMjMtMDctMzAvRnJFS1lvQS50eHQ=` (free clash.meta subscribe config)

## UUID Setting (Optional)

1. When deploy in cloudflare pages, you can set uuid in `wrangler.toml` file. variable name is `UUID`. `wrangler.toml` file is also supported. (recommended) in case deploy in webpages, you can not set uuid in `wrangler.toml` file.

2. When deploy in worker.dev, you can set uuid in `_worker.js` file. variable name is `userID`. `wrangler.toml` file is also supported. (recommended) in case deploy in webpages, you can not set uuid in `wrangler.toml` file. in this case, you can also set uuid in `UUID` enviroment variable.

Note: `UUID` is the uuid you want to set. pages.dev and worker.dev all of them method supported, but depend on your deploy method.

### UUID Setting Example

1. single uuid environment variable

   ```.environment
   UUID = "uuid here your want to set"
   ```

2. multiple uuid environment variable

   ```.environment
   UUID = "uuid1,uuid2,uuid3"
   ```

   note: uuid1, uuid2, uuid3 are separated by commas`,`.
   when you set multiple uuid, you can use `https://edtunnel.pages.dev/uuid1` to get the clash config and vless:// link.

## subscribe vless:// link (Optional)

1. visit `https://edtunnel.pages.dev/uuid your set` to get the subscribe link.

2. visit `https://edtunnel.pages.dev/sub/uuid your set` to get the subscribe content with `uuid your set` path.

   note: `uuid your set` is the uuid you set in UUID enviroment or `wrangler.toml`, `_worker.js` file.
   when you set multiple uuid, you can use `https://edtunnel.pages.dev/sub/uuid1` to get the subscribe content with `uuid1` path.(only support first uuid in multiple uuid set)

3. visit `https://edtunnel.pages.dev/sub/uuid your set/?format=clash` to get the subscribe content with `uuid your set` path and `clash` format. content will return with base64 encode.

   note: `uuid your set` is the uuid you set in UUID enviroment or `wrangler.toml`, `_worker.js` file.
   when you set multiple uuid, you can will use `https://edtunnel.pages.dev/sub/uuid1/?format=clash` to get the subscribe content with `uuid1` path and `clash` format.(only support first uuid in multiple uuid set)

## subscribe Cloudflare bestip(pure ip) link

1. visit `https://edtunnel.pages.dev/bestip/uuid your set` to get subscribe info.

2. cpoy subscribe url link `https://edtunnel.pages.dev/bestip/uuid your set` to any clients(clash/v2rayN/v2rayNG) you want to use.

3. done. if have any questions please join [@edtunnel](https://t.me/edtunnel)

## multiple port support (Optional)

   <!-- let portArray_http = [80, 8080, 8880, 2052, 2086, 2095];
	let portArray_https = [443, 8443, 2053, 2096, 2087, 2083]; -->

For a list of Cloudflare supported ports, please refer to the [official documentation](https://developers.cloudflare.com/cloudflare-one/connections/connect-apps/ports).

By default, the port is 80 and 443. If you want to add more ports, you can use the following ports:

```text
80, 8080, 8880, 2052, 2086, 2095, 443, 8443, 2053, 2096, 2087, 2083
http port: 80, 8080, 8880, 2052, 2086, 2095
https port: 443, 8443, 2053, 2096, 2087, 2083
```

if you deploy in cloudflare pages, https port is not supported. Simply add multiple ports node drictly use subscribe link, subscribe content will return all Cloudflare supported ports.

## free node:
vmess://ew0KICAidiI6ICIyIiwNCiAgInBzIjogIvCfh6/wn4e1SlAtMTM4LjIuMzkuNTUtMTI4OSIsDQogICJhZGQiOiAiamFwYW4ucHhpei5zaXRlIiwNCiAgInBvcnQiOiAiNTQ3NTIiLA0KICAiaWQiOiAiMmRhNjRkZTQtNTRkMC00NjExLWFiMTYtMzQwMWE4ZDE2ZjBjIiwNCiAgImFpZCI6ICIwIiwNCiAgInNjeSI6ICJhdXRvIiwNCiAgIm5ldCI6ICJ3cyIsDQogICJ0eXBlIjogInZtZXNzIiwNCiAgImhvc3QiOiAiYmFpZHUuY29tIiwNCiAgInBhdGgiOiAiLz9lZD0yMDQ4IiwNCiAgInRscyI6ICIiLA0KICAic25pIjogImJhaWR1LmNvbSIsDQogICJhbHBuIjogImgyIiwNCiAgImZwIjogInNhZmFyaSINCn0=
vmess://ew0KICAidiI6ICIyIiwNCiAgInBzIjogIvCfj4FSRUxBWS0xMDQuMTguMzYuMTc0LTM2NTEiLA0KICAiYWRkIjogImNmY2RuMS5zYW5mZW5jZG45LmNvbSIsDQogICJwb3J0IjogIjgwIiwNCiAgImlkIjogIjEwNWNkZmY2LTE0ZDYtNGYzMS1kZjY5LWQyZDU4YzAwM2M4YiIsDQogICJhaWQiOiAiMCIsDQogICJzY3kiOiAiYXV0byIsDQogICJuZXQiOiAid3MiLA0KICAidHlwZSI6ICJ2bWVzcyIsDQogICJob3N0IjogImx4Y3VzLmluZWtva2trLnRvcCIsDQogICJwYXRoIjogIi8iLA0KICAidGxzIjogIiIsDQogICJzbmkiOiAibHhjdXMuaW5la29ra2sudG9wIiwNCiAgImFscG4iOiAiaDIsaHR0cC8xLjEiLA0KICAiZnAiOiAiY2hyb21lIg0KfQ==
vmess://ew0KICAidiI6ICIyIiwNCiAgInBzIjogIvCfj4FSRUxBWS0xNzIuNjcuMTY5LjI0NS0xMjkiLA0KICAiYWRkIjogInVzNjUubmV0ZmlseC5saXZlIiwNCiAgInBvcnQiOiAiODAiLA0KICAiaWQiOiAiNjBmMTI0MzUtYmI1NS00ZGEyLWNiN2QtNGZlYTM0ZWNmYTM3IiwNCiAgImFpZCI6ICIwIiwNCiAgInNjeSI6ICJhdXRvIiwNCiAgIm5ldCI6ICJ3cyIsDQogICJ0eXBlIjogInZtZXNzIiwNCiAgImhvc3QiOiAiIiwNCiAgInBhdGgiOiAiIiwNCiAgInRscyI6ICIiLA0KICAic25pIjogIiIsDQogICJhbHBuIjogImh0dHAvMS4xIiwNCiAgImZwIjogImFuZHJvaWQiDQp9
vmess://ew0KICAidiI6ICIyIiwNCiAgInBzIjogIjE0fOe+juWbvSBDbG91ZEZsYXJl6IqC54K5ICM1IiwNCiAgImFkZCI6ICJ1czY1Lm5ldGZpbHgubGl2ZSIsDQogICJwb3J0IjogIjgwIiwNCiAgImlkIjogIjYwZjEyNDM1LWJiNTUtNGRhMi1jYjdkLTRmZWEzNGVjZmEzNyIsDQogICJhaWQiOiAiMCIsDQogICJzY3kiOiAiYXV0byIsDQogICJuZXQiOiAid3MiLA0KICAidHlwZSI6ICJ2bWVzcyIsDQogICJob3N0IjogIiIsDQogICJwYXRoIjogIiIsDQogICJ0bHMiOiAiIiwNCiAgInNuaSI6ICIiLA0KICAiYWxwbiI6ICJoMixodHRwLzEuMSIsDQogICJmcCI6ICJmaXJlZm94Ig0KfQ==
vmess://ew0KICAidiI6ICIyIiwNCiAgInBzIjogIvCfh7rwn4e4IOe+juWbvSBDbG91ZEZsYXJl6IqC54K5IiwNCiAgImFkZCI6ICJ1czY1Lm5ldGZpbHgubGl2ZSIsDQogICJwb3J0IjogIjgwIiwNCiAgImlkIjogIjYwZjEyNDM1LWJiNTUtNGRhMi1jYjdkLTRmZWEzNGVjZmEzNyIsDQogICJhaWQiOiAiMCIsDQogICJzY3kiOiAiYXV0byIsDQogICJuZXQiOiAid3MiLA0KICAidHlwZSI6ICJ2bWVzcyIsDQogICJob3N0IjogInVzNjUubmV0ZmlseC5saXZlIiwNCiAgInBhdGgiOiAiLyIsDQogICJ0bHMiOiAiIiwNCiAgInNuaSI6ICJ1czY1Lm5ldGZpbHgubGl2ZSIsDQogICJhbHBuIjogImgyLGh0dHAvMS4xIiwNCiAgImZwIjogImZpcmVmb3giDQp9
vmess://ew0KICAidiI6ICIyIiwNCiAgInBzIjogIvCfh7rwn4e4IF9VU1/nvo7lm70tPvCfh6nwn4eqX0RFX+W+t+WbvSIsDQogICJhZGQiOiAiMTA0LjIxLjY5LjQ0IiwNCiAgInBvcnQiOiAiODAiLA0KICAiaWQiOiAiNzAyMjk4MmYtZGE0Yy00OGM5LWM2NjAtYjIzMTVhYmRjZjdlIiwNCiAgImFpZCI6ICIwIiwNCiAgInNjeSI6ICJhdXRvIiwNCiAgIm5ldCI6ICJ3cyIsDQogICJ0eXBlIjogInZtZXNzIiwNCiAgImhvc3QiOiAiYS5wcmFwdDQuaXIiLA0KICAicGF0aCI6ICIvIiwNCiAgInRscyI6ICIiLA0KICAic25pIjogImEucHJhcHQ0LmlyIiwNCiAgImFscG4iOiAiaHR0cC8xLjEiLA0KICAiZnAiOiAiZWRnZSINCn0=
vmess://ew0KICAidiI6ICIyIiwNCiAgInBzIjogIvCfh7Pwn4exIF9OTF/ojbflhbAiLA0KICAiYWRkIjogIjE4OC4xMTQuOTYuMTEzIiwNCiAgInBvcnQiOiAiODAiLA0KICAiaWQiOiAiNzAyMjk4MmYtZGE0Yy00OGM5LWM2NjAtYjIzMTVhYmRjZjdlIiwNCiAgImFpZCI6ICIwIiwNCiAgInNjeSI6ICJhdXRvIiwNCiAgIm5ldCI6ICJ3cyIsDQogICJ0eXBlIjogInZtZXNzIiwNCiAgImhvc3QiOiAiYS5wcmFwdDQuaXIiLA0KICAicGF0aCI6ICIvIiwNCiAgInRscyI6ICIiLA0KICAic25pIjogImEucHJhcHQ0LmlyIiwNCiAgImFscG4iOiAiaHR0cC8xLjEiLA0KICAiZnAiOiAicmFuZG9taXplZCINCn0=


## proxyIP (Optional)

1. When deploy in cloudflare pages, you can set proxyIP in `wrangler.toml` file. variable name is `PROXYIP`.

2. When deploy in worker.dev, you can set proxyIP in `_worker.js` file. variable name is `proxyIP`.

note: `proxyIP` is the ip or domain you want to set. this means that the proxyIP is used to route traffic through a proxy rather than directly to a website that is using Cloudflare's (CDN). if you don't set this variable, connection to the Cloudflare IP will be cancelled (or blocked)...

resons: Outbound TCP sockets to Cloudflare IP ranges are temporarily blocked, please refer to the [tcp-sockets documentation](https://developers.cloudflare.com/workers/runtime-apis/tcp-sockets/#considerations)

## Usage

frist, open your pages.dev domain `https://edtunnel.pages.dev/` in your browser, then you can see the following page:
The path `/uuid your seetting` to get the clash config and vless:// link.

## Star History

<a href="https://star-history.com/#3Kmfi6HP/EDtunnel&Date">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=3Kmfi6HP/EDtunnel&type=Date&theme=dark" />
    <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=3Kmfi6HP/EDtunnel&type=Date" />
    <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=3Kmfi6HP/EDtunnel&type=Date" />
  </picture>
</a>
