# Description

Data Exfiltration Protocol (DEP) Client - Transfer data with DEP

# Installation

`pip install dep_client`

# Usage

**From command line:**

`python -m dep_client --ip IP --port PORT [--pkgSize PKGSIZE] [--msg {sim,dim,dam,dcm}] --uuid UUID [--hash HASH] [--path PATH] [--size SIZE] [--dataState {0,1,2}]`

| Option | Short | Type | Default | Description |
|---|---|---|---|---|
|--ip | -i | String | - | IP address of destination |
|--port | -r | Int | - | Port of destination |
|--pkgSize | -k | Int | 1321 | Nr. of bytes to load in chunks. <= 1321 |
|--msg | -m | String | - | sim = SystemInformationMessage <br> dim = DataInformationMessage <br> dam = DataAcknowledgeMessage <br> dcm = DataContentMessage |
|--uuid | -u | String | - | uuid4 str, e.g.: 50f437d8-28b7-4c65-9588-eef116a60ae3 |
|--hash | -a | String | - | sha256 hash of data as hex string |
|--path | -p | String | - | (for files) path under which the data is located. (for in memory) path under which the data is saved at exfiltration endpoint |
|--size | -s | Int | - | size of data in bytes |
|--dataState | -d | Int | - | 0 = Data is not exfiltrated yet <br> 1 = Data is already exfiltrated <br> 2 = Data available under given path but hash differs |

# Example

`python -m dep_client -i 127.0.0.1 -r 6666 -m sim -u 50f437d8-28b7-4c65-9588-eef116a60ae3`

Sends `SystemInformationMessage` to `127.0.0.1` on port `6666` with uuid `50f437d8-28b7-4c65-9588-eef116a60ae3`