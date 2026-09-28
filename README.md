# BlockingLists

DNS blocklists for [AdGuard Home](https://github.com/AdguardTeam/AdGuardHome) and [Pi-hole](https://pi-hole.net/).

## Lists

| File | Entries | Format | Blocks |
|------|--------:|--------|--------|
| [`AdGuard/Youtube-Ads-Blocking`](AdGuard/Youtube-Ads-Blocking) | 2,772 | hosts (`127.0.0.1 <host>`) | YouTube video-server (`googlevideo`) hosts (`r*---sn-*` and `r*.sn-*` patterns) |

The list is a static snapshot, last updated on 2020-08-27. Nothing in this repository refreshes it automatically.

## Usage

Use the raw URL:

```
https://raw.githubusercontent.com/t0mer/BlockingLists/master/AdGuard/Youtube-Ads-Blocking
```

**AdGuard Home:** open **Filters → DNS blocklists → Add blocklist → Add a custom list**, enter a name and the URL above, then click **Save**.

**Pi-hole:** open **Adlists** (Pi-hole v5) or **Lists** (Pi-hole v6), paste the URL above, add it, then update gravity (`pihole -g`).

Both tools accept the hosts-file format used by this list.

## Known issues

* **YouTube playback may break.** YouTube serves both ads and regular video from `googlevideo.com` hosts, so blocking them can stop normal videos from playing. Remove the list, or allowlist the affected host, if that happens.
* **21 entries are malformed.** Lines for `r1`–`r20.sn-uhvcpax0n5-v53e.a1.googlevideo` are missing the trailing `.com`, and the first line (`1---sn-p5qlsndz.googlevideo.com`) is missing the leading `r`, so these never match a real host.

## Contributing

Issues and pull requests are welcome.

## License

This repository has no license file.
