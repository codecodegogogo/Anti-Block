# AdGuard Home rules

`anti_fraud_dns_filter.txt` contains the domain block rules that can be used
by AdGuard Home.

Use it in one of these ways:

1. Paste the contents into AdGuard Home's custom filtering rules.
2. Publish the file somewhere reachable by AdGuard Home and add it as a DNS
   blocklist.
3. If AdGuard Home is configured by file, reference it as a local blocklist
   from the AdGuard Home host.

## IP rules

The IP entries in `../rules/anti_fraud_ips.txt` are not included in the
AdGuard Home DNS filter because DNS filtering only sees domain lookups. It
does not see traffic that an app sends directly to an IP address.

To block those IPs, put them in a real firewall layer instead, for example:

- the router or gateway firewall
- OpenWrt nftables/iptables
- Android iptables
- Windows Defender Firewall

AdGuard Home can prevent a client from resolving blocked domains when the
client uses AdGuard Home as DNS. It cannot reliably block hard-coded IP
connections by itself.
