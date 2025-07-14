# L3akCTF2025 - BrainCalc

Mobile - Easy - 50 points

## Challenge description

*Quick and fun math quiz app for practicing.*

## Solution

The challenge provides us an .apk app, we will have to look inside.

To do this, I used a tool called `jadx-gui` which decompiles all Android DEX files into Java source code.

I looked into the Java code if there were any suspicious strings that could be similar to a flag. 
Unfortunalety, nothing special came out but there were functions like `Decode`, `Base64.decode()` so I assume the flag is encrypted in Base64.

I go to the MainActivity file. It has lots of instructions in Python, and `getString(R.string.main_module)` caught my attention.
I search for main_module's name in the Resource field, which is `<string name="main_module">BrainCalc</string>`.
Now I search `BrainCalc` still in Resource, and there are several mentions of it in app.imy file.
I export the app.imy in my computer. `file app.imy` says `app.imy: Zip archive data, at least v2.0 to extract, compression method=deflate`

I rename it app.zip and then unzip it. We have .pyc files which contains bytecode.
Looking inside, there is a suspicious sentence `Nz0eJzzMXb0rvYqLS6JN4kPNynKjQ8tiHfOMMnJqQUAeHcJQA==zutf-8zError: Could not decode secret)�base64�	b64decode�zlib�`.

Let's try to put it into CyberChef. From Base64 `eJzzMXb0rvYqLS6JN4kPNynKjQ8tiHfOMMnJqQUAeHcJQA==`, the magical stick will suggest Zlib inflate. Zlib is a data compression library.
Use the magical stick and voila, you got your flag!

The flag is: `L3AK{Just_4_W4rm_Up_Ch4ll}`
