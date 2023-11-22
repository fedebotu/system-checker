# System Checker

Script reporting possible problems on Linux servers as provided by KAIST

## Usage

- Change permissions to 744: `chmod 744`
- Run as root: `sudo ./linux_checker.sh`

The script will simply report several things such as network permission, command history, and so on. Note that collected data might be highly private (e.g. connections through private endpoints), so don't share it lightly.

## Exploits

There are several exploits. For instance, I use `zsh` and history is separated from the usual `bash_history`, so the script above won't work if a "malicious program" is detected.


## Why do you have this script?


> Every time we want to install even just PyTorch, we have to wait around 1 hour in KAIST, with multiple connection drops. By using a simple VPN connection, this is a couple of minutes.

We were asked to report all our information from the server by the KAIST security team because we use [NGROK](https://ngrok.com/), somewhat detected by them as a malware. However, there is an important reason why we have it, so I will take the opportunity to raise awareness about network connection issues in our university.
Here is our message:

_We would like to acknowledge that we are the ones using NGROK, a useful reverse proxy. In our case, NGROK is not a virus but a feature (or lifesaver)._

_Why are we paying for NGROK and VPNs to circumvent the KAIST network?_

_Unfortunately, the connection in KAIST (or at least, in our department and for many servers we use even outside of the above) makes it hard to do research. Many websites, including Github, are actively blocked, polluted, or slowed down. Commonly used hosts of, e.g., Python programs (when using pip install) randomly drop connection with a time-out message, which hinders installation, similar to how the so-called "Great Chinese Firewall" operates in China.
By using our NGROK, we can 1) download way faster and 2) avoid random connection drops to several websites such as PyPI. For example, from around 2 MB/s and random disconnections to 20MB/s+, which means the physical connection in KAIST is not the real problem, but rather firewalls or other control methods that are severely restricting the network access._

_We hope KAIST, in the future, will implement less restrictive network access, at least for websites (pytorch.org, pypi.org, *.github.io) that are well-known in the research community whose access is fundamental for advancing research._
