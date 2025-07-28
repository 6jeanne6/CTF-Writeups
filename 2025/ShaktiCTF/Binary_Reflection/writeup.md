# ShaktiCTF2025 - Binary Reflection

Forensics - 100 points

## Challenge description

*The truth is hidden in a mirror*

## Solution

The challenge provides us a broken pdf file. It is impossible to open with Document Viewer, so I used `cat` to have a look inside.

The broken pdf starts with `%;EOF` and ends with `$PDF-1.3`. With common sense, it should be the other way around.

Let's use `tac`, which description is `Write each FILE to standard output, last line first.`

I do `tac corrupt.pdf > reversed.pdf`, and then:

<p align="center">
  <img src="https://github.com/6jeanne6/CTF-Writeups/blob/main/2025/ShaktiCTF/Binary_Reflection/pdf_fixed.png" width="500"/>
</p>

The flag is: `shaktictf{pdf_pr3tty_d4m4g3d_f0rm4t}`
