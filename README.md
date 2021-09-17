# geolocate
This tool uses a public API to query geolocation data and identify the origin of an IP address from the terminal. You can specify a single IP address or a text file with multiple IP addresses.

## Requirements
Python3

## Installation
```bash
git clone https://github.com/ghsinfosec/geolocate.git
```

You can add a symbolic link to run it from anywhere by typing:

```bash
sudo ln -s $(pwd)/geolocate.py /usr/local/bin/geolocate
```


## Usage

To query for a single IP
```bash
python3 geolocate.py -i x.x.x.x
```

To query a list of IP's (one IP per line)
```bash
python3 geolocate.py -f <filename>
```

The IP list file would look like:
```
x.x.x.x
y.y.y.y
z.z.z.z
```

## Examples
To geolocate a sinle IP address:

```bash
python3 geolocate.py -i 1.188.206.54

ip_address    country    regionName    city        lat      lon  isp                                         org    as
------------  ---------  ------------  ------  -------  -------  ------------------------------------------  -----  -------------------------------------
1.188.206.54  China      Heilongjiang  Suihua  46.6395  126.995  China Unicom Heilongjiang Province Network         AS4837 CHINA UNICOM China169 Backbone
```

To geolocate a list of IP addresses
```bash
python3 geolocate.py -f /opt/ip-list.txt

ip_address       country         regionName              city            lat       lon  isp                                          org                                          as
---------------  --------------  ----------------------  ----------  -------  --------  -------------------------------------------  -------------------------------------------  ---------------------------------------------------
1.188.206.54     China           Heilongjiang            Suihua      46.6395  126.995   China Unicom Heilongjiang Province Network                                                AS4837 CHINA UNICOM China169 Backbone
109.224.232.102  United Kingdom  England                 Hampstead   51.5506   -0.1873  gradwell dot com Limited                     Gradwell Communications Limited              AS29676 Gradwell Communications Limited
161.97.157.19    Germany         North Rhine-Westphalia  Düsseldorf  51.1878    6.8607  Contabo GmbH                                 Contabo GmbH                                 AS51167 Contabo GmbH
197.210.71.217   Nigeria         Lagos                   Lagos        6.4474    3.3903  Reserved Enterprise-Internet-WAN                                                          AS29465 MTN NIGERIA Communication limited
59.111.103.165   China           Beijing                 Beijing     39.9042  116.407   Guangzhou NetEase Computer System Co., Ltd.  Hangzhou NetEase Leihuo Technology Co., Ltd  AS45062 Guangzhou NetEase Computer System Co., Ltd.

```
