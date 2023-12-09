# AutoRecon

This Python script automates the reconnaissance process 
for penetration testers and bug hunters. It is designed to streamline 
subdomain enumeration, port scanning, template-based scanning, XSS, JS 
file analysis, and searching for exposed panels. The script sends live 
results via Discord, eliminating the need to manually check logs. It can
 be run as a cron job or within a tmux session, allowing users to 
efficiently await results.

## 

## Prerequisites

Before using the script, ensure you have the following tools and dependencies installed:

- Python 3.x
- [Subfinder](https://github.com/projectdiscovery/subfinder)
- [PureDNS](https://github.com/d3mondev/puredns)
- [Naabu](https://github.com/projectdiscovery/naabu)
- [Nuclei](https://github.com/projectdiscovery/nuclei)
- [HTTPX](https://github.com/projectdiscovery/httpx)
- [Gau](https://github.com/lc/gau)
- [kxss](https://github.com/tomnomnom/hacks/tree/main/kxss)
- [Notify](https://github.com/projectdiscovery/notify)
- [Wordlists](https://github.com/0x0Pwn/Wordlists)
- [nuclei_templates](https://github.com/0x0Pwn/nuclei_templates)

So you need to run this command, that will install all above dependecies, before doing something:

```bash
bash install.sh
```

## Setup

1. Clone the repository:

```
git clone https://github.com/0x0Pwn/AutoRecon.git
```

2. Navigate to the script directory:

```
cd AutoRecon
```

3. Set up a virtual environment (optional but recommended):

```
python -m venv venv
source venv/bin/activate  # On Windows, use 'venv\Scripts\activate'
```

4. Install the required prerequisites:

```
bash install.sh
```

5. Configure Discord Webhook URL in the Notify tool configuration file:

```
nvim $HOME/.config/notify/provider-config.yaml #or nano ...
```

## Usage

Run the script with the desired options to perform reconnaissance tasks. Below are some examples:

```
python AutoRecon.py -d example.com -se -p -nt -nf -ep -js -xss -wh your_discord_webhook_url
```

### 

### Available Options:

- `d, --domain`: Target domain for reconnaissance (required).
- `se, --subenum`: Perform subdomain enumeration.
- `p, --portscan`: Perform port scanning.
- `nt, --new-templates`: Scan with newly added templates to the nuclei templates repo.
- `nf, --nuclei-full`: Perform a full nuclei scan.
- `ep, --exposed-panels`: Perform Panels dorking with nuclei templates.
- `js, --js-exposures`: Perform JS Exposures.
- `sl, --subs-file`: Path to the subdomains file.
- `xss, --xss-scan`: Perform XSS scans.
- `wh, --webhook`: Webhook URL for Discord.

## Contributing

If you encounter any issues or have suggestions for 
improvements, feel free to open an issue or submit a pull request. 
Collaboration is welcome, and don't hesitate to reach out for 
assistance.
