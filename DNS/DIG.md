>[!INFO] About investigating with `dig`
>`dig` is a powerful tool allowing researchers to : identify hidden subdomains, uncover internal systems or staging servers, extract email configuration (MX/TXT records), validate DNS misconfigurations.
# Commands
## Get ALL DNS Records

```bash
dig EXAMPLE.COM ANY
```

## Get Name Servers

```bash
dig EXAMPLE.COM NS
```

Once you know the nameservers, you can pivot:

```bash
dig @ns1.example.com subdomain.example.com
```

>This is where **zone transfers (AXFR)** come into play, critical if enabled.

### Zone Transfer Attempt
>If it is not properly configured, you might retrieve the entire DNS records.

```bash
dig AXFR example.com @ns1.example.com
```

## Get Mail Server
```bash
dig EXAMPLE.COM MX
dig EXAMPLE.COM TXT
```

- Get DMARC :
```bash
# Get DMARC records
dig TXT _dmarc.EXAMPLE.COM +short
```

## Get Points of Contact

```bash
dig EXAMPLE.COM SOA
```

## Reverse DNS
>From an IP, get the hostname

```bash
dig -x 1.1.1.1
```