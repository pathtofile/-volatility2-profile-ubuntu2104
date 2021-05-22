# Ubuntu 21.04 Profile For Volatility 2

This zip contains a `System.map` and `modules.dwarf` That Matches `Ubuntu 21.04`, Kernel `5.11.0-17`. As of 22-May-2021 this way the current kernel for Ubuntu 21.04.

This was to enable teasting using Volatility to extract information from eBPF CO-RE programs.

# Usage
Simply move the .zip to your Volatility plugins directory (or an empty directory if you don't have one), then run volaility with the `--plugins` and `--profile` flags:

```bash
$> vol.py --plugins=/path/to/plugins/folder --info | grep Linux
LinuxUbuntu2104x64    - A Profile for Linux Ubuntu2104 x64
```
```bash
$>vol.py --plugins=/path/to/plugins/folder -f memdump.lime --profile=LinuxUbuntu2104x64 linux_lsmod
```

# How this was made:
Following this guide: [https://github.com/volatilityfoundation/volatility/wiki/Linux](https://github.com/volatilityfoundation/volatility/wiki/Linux)


# Why not Volatility 3?
My kernel was compiled with BTF information and not DAWRF, and currently there is no was to get a Volatility 3 symbol table without downloading and re-compilnig another kernel.
