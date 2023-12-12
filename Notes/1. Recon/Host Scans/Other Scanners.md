# Other Scanners

## Unicornscan: 
Another asynchronous TCP scanner, unicornscan can be a masscan alternative, but given it is no longer maintain, use only in the unlikely scenario that nmap and masscan are unavailable.

- `unicornscan -mU -p ,161,162,137,123,138,1434,445,135,67,68,53,139,500,637,162,69`

## Netcat
```
#!/bin/bash
for i in {0..255}; do
    for j in {0..255};do
        for k in {0..65535};do
            nc -v -z -n -w 1 10.100.${i}.${j} ${k} >> nc_port_scan.txt
        done
    done
done
```

## Naabu
Source: https://github.com/projectdiscovery/naabu

### Installing Naabu: 
Latest: 
`go install -v github.com/projectdiscovery/naabu/v2/cmd/naabu@latest`
 
In Kali Linux: 
`sudo apt install naabu`
 
## Using Naabu:
- `naabu -host megacorpone.com`
- `naabu -p 80,443,21-23,u:53 -host megacorpone.com`
- `naabu -p - -exclude-ports 80,443 -host megacorpone.com`
- `naabu -host megacorpone.com -json`