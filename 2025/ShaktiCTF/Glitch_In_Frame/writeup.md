# ShaktiCTF2025 - Glitch In Frame

Forensics - 100 points

## Challenge description

*Kael intercepted a strange transmission. Nyra says it's just a looped diagnostic — but something feels off. Can you find the hidden message?*

## Solution

The challenge provides us a pcap (packet capture) file, which records network packets. Let's have a look with `Wireshark`.

<p align="center">
  <img src="https://github.com/6jeanne6/CTF-Writeups/blob/main/2025/ShaktiCTF/Glitch_In_Frame/wireshark_gif89a.png" width="500"/>
</p>

A suspicious packet with `GIF89a` caught my attention. I right-click, `Follow` and `TCP Stream` to have a detailed view about it.

<p align="center">
  <img src="https://github.com/6jeanne6/CTF-Writeups/blob/main/2025/ShaktiCTF/Glitch_In_Frame/wireshark_packet.png" width="500"/>
</p>

In `Show Data as`, put `Raw`, and `Save as` `whatever.gif`. The GIF won't open because it is glitched.

With `Vim`, I remove the useless text before `GIF89a` and after `B...;`.
Now we have a working GIF, but frames move too quickly. I use `ezgif` to cut the gif into each frame.

<p align="center">
  <img src="https://github.com/6jeanne6/CTF-Writeups/blob/main/2025/ShaktiCTF/Glitch_In_Frame/ezgif.png" width="500"/>
</p>

Each frame has a fragment of the flag.

The flag is: `shaktictf{v1sU4l_d@t4_xf3ltr4t10n_thru_pkt5_and_fr4m3s_is_n0t_a_myth_just_v3ry_und3rr4ted}`
