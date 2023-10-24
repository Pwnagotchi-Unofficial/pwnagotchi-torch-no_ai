# Pwnagotchi-Torch-64
<a href="https://github.com/jayofelony/pwnagotchi/releases/latest"><img alt="Release" src="https://img.shields.io/github/release/jayofelony/pwnagotchi.svg?style=flat-square"></a><br/>
**This fork of [Pwnagotchi](https://www.pwnagotchi.ai) has been overhauled to work solely on 64-bit Raspberry Pi's, it uses PyTorch as it's AI.**

**Use RPi imager to flash, if you want you can set a custom user/pass to ssh in.**

Default SSH credentials are pi/raspberry

# FAQ:
- Is the Raspberry Pi Zero W 2 working perfectly with this image?

  No, sadly not. It will reboot and restart wifi as often as needed by fix_services plugin. So don't freak out by that. I hope it will be sorted in the future.
- Will it go blind often?

  Yes! But I have tried to make it automatically fix **most** errors that may occur.
- Can you help me install an external antenna?

  Nope I will not help with these 'issues'. Read the manual/readme for your specific device, if that doesn't help -> **[GOOGLE](https://www.google.com)**

- If you want to use the gdrivesync plugin >> [README](README-google.md)
# Patreon: 

[Pwnagotchi-Torch](https://www.patreon.com/pwnagotchi_torch)

---

[Pwnagotchi](https://pwnagotchi.ai/) is an [A2C](https://hackernoon.com/intuitive-rl-intro-to-advantage-actor-critic-a2c-4ff545978752)-based "AI" leveraging [bettercap](https://www.bettercap.org/) that learns from its surrounding WiFi environment to maximize the crackable WPA key material it captures (either passively, or by performing authentication and association attacks). This material is collected as PCAP files containing any form of handshake supported by [hashcat](https://hashcat.net/hashcat/), including [PMKIDs](https://www.evilsocket.net/2019/02/13/Pwning-WiFi-networks-with-bettercap-and-the-PMKID-client-less-attack/), 
full and half WPA handshakes.

![ui](https://i.imgur.com/X68GXrn.png)

Instead of merely playing [Super Mario or Atari games](https://becominghuman.ai/getting-mario-back-into-the-gym-setting-up-super-mario-bros-in-openais-gym-8e39a96c1e41?gi=c4b66c3d5ced) like most reinforcement learning-based "AI" *(yawn)*, Pwnagotchi tunes [its parameters](https://github.com/evilsocket/pwnagotchi/blob/master/pwnagotchi/defaults.toml) over time to **get better at pwning WiFi things to** in the environments you expose it to. 

More specifically, Pwnagotchi is using an [LSTM with MLP feature extractor](https://stable-baselines.readthedocs.io/en/master/modules/policies.html#stable_baselines.common.policies.MlpLstmPolicy) as its policy network for the [A2C agent](https://stable-baselines.readthedocs.io/en/master/modules/a2c.html). If you're unfamiliar with A2C, here is [a very good introductory explanation](https://hackernoon.com/intuitive-rl-intro-to-advantage-actor-critic-a2c-4ff545978752) (in comic form!) of the basic principles behind how Pwnagotchi learns. (You can read more about how Pwnagotchi learns in the [Usage](https://www.pwnagotchi.ai/usage/#training-the-ai) doc.)

**Keep in mind:** Unlike the usual RL simulations, Pwnagotchi learns over time. Time for a Pwnagotchi is measured in epochs; a single epoch can last from a few seconds to minutes, depending on how many access points and client stations are visible. Do not expect your Pwnagotchi to perform amazingly well at the very beginning, as it will be [exploring](https://hackernoon.com/intuitive-rl-intro-to-advantage-actor-critic-a2c-4ff545978752) several combinations of [key parameters](https://www.pwnagotchi.ai/usage/#training-the-ai) to determine ideal adjustments for pwning the particular environment you are exposing it to during its beginning epochs ... but ** listen to your Pwnagotchi when it tells you it's boring!** Bring it into novel WiFi environments with you and have it observe new networks and capture new handshakes—and you'll see. :)

Multiple units within close physical proximity can "talk" to each other, advertising their presence to each other by broadcasting custom information elements using a parasite protocol I've built on top of the existing dot11 standard. Over time, two or more units trained together will learn to cooperate upon detecting each other's presence by dividing the available channels among them for optimal pwnage.

## Documentation

https://www.pwnagotchi.ai

## Links

| &nbsp;    | Official Links                                              |
|-----------|-------------------------------------------------------------|
| Website   | [pwnagotchi.ai](https://pwnagotchi.ai/)                     |
| Forum     | [community.pwnagotchi.ai](https://community.pwnagotchi.ai/) |
| Slack     | [pwnagotchi.slack.com](https://invite.pwnagotchi.ai/)       |
| Subreddit | [r/pwnagotchi](https://www.reddit.com/r/pwnagotchi/)        |
| Twitter   | [@pwnagotchi](https://twitter.com/pwnagotchi)               |

## License

`pwnagotchi` is made with ♥  by [@evilsocket](https://twitter.com/evilsocket) and the [amazing dev team](https://github.com/evilsocket/pwnagotchi/graphs/contributors). It is released under the GPL3 license.
