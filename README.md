# Odin3 checksums

SHA-256 checksums for the Odin3 ZIP files hosted at [getodintool.com](https://getodintool.com/older-versions/).

I put this list here so you can check that the file you downloaded is the same one I hosted, byte for byte. Every hash below was recomputed from the live files on 2026-10-02.

## What this does and doesn't tell you

A matching checksum means your download wasn't corrupted or swapped on the way. It doesn't prove the file came from Samsung. Samsung has never published Odin for the public, and every copy you can find online traces back to a leak, so no one can give you an official hash to compare against.

Version 3.14.4 needs a special note. Its program code is identical to v3.14.1, but the ZIP ships with an extra DLL and edited resources. I explain what I found on the [latest version page](https://getodintool.com/latest/). If you want the build without the extra DLL, use v3.14.1.

Scan any download before you run it, and only flash firmware that matches your exact model.

## How to check a file

On Windows, open PowerShell in the folder with the ZIP and run:

```
Get-FileHash .\Odin3-v3.14.1.zip -Algorithm SHA256
```

Or use Command Prompt:

```
certutil -hashfile Odin3-v3.14.1.zip SHA256
```

On macOS or Linux:

```
shasum -a 256 Odin3-v3.14.1.zip
```

Compare the output to the table below. If you want to check everything at once, put `SHA256SUMS` next to the ZIPs and run `sha256sum -c SHA256SUMS`.

## Checksums

| Version | File | Size (bytes) | SHA-256 |
|---|---|---|---|
| 3.14.4 | Odin3-v3.14.4.zip | 4,511,538 | `eda427680fbd16716b8a4856fd450857d1bcc75e379ac90b9165e49d9d652828` |
| 3.14.1 | Odin3-v3.14.1.zip | 2,595,015 | `638296a11b1bfa954991b0597214d833511b973480ae9e15e299a761fea1f794` |
| 3.13.3 | Odin3-v3.13.3.zip | 2,592,953 | `f6f2b83e3e85ff48fafc55612efe64e43fa6113e5cbe6801994ef62194db0a02` |
| 3.13.1 | Odin3-v3.13.1.zip | 2,662,928 | `652d535c37ca5a81bce330139b7e79ec29b33027a81a0d0419589699fb078038` |
| 3.12.7 | Odin3-v3.12.7.zip | 1,295,578 | `04a771b3ec1129c78272470059616002ff4284bef13d9ab083b847ae4d72a321` |
| 3.12.5 | Odin3-v3.12.5.zip | 1,295,842 | `e589dd239e35c61edb80cd9929db16696a4b730f38e34fce6dc245beb87f0d93` |
| 3.12.4 | Odin3-v3.12.4.zip | 1,295,841 | `8f273098427e7db1cb4a282110491868baf6f2e8ad22f74b007112202b1fdb06` |
| 3.12.3 | Odin3-v3.12.3.zip | 1,150,898 | `1bf654c8cf43a5d42939a6034d534cedd7486e40d9be42c8b1ef374ac67a83e2` |
| 3.11.2 | Odin3-v3.11.2.zip | 1,003,037 | `febbb0ba51fe97ab576b12d8d782cfd012796e678a6abf08684cc3c2f2a4e4ce` |
| 3.11.1 | Odin3-v3.11.1.zip | 1,002,757 | `a2402d4f17e6759f1f8ec742d44debd29a0e3e65461422cbdeae79a3519e8cf9` |
| 3.10.7 | Odin3-v3.10.7.zip | 1,109,840 | `240e1ace55a79731af5751105c49352e8d1ab662227f3d507f369802078ff4ae` |
| 3.10.6 | Odin3-v3.10.6.zip | 1,031,853 | `8f348abcb066ec2d16b6afb864c26fcaf69fd6436e77e84c786276e324152e3d` |
| 3.10.5 | Odin3-v3.10.5.zip | 1,030,718 | `84d0a5bab96622ac49fb0e06e6847dc563341c90f3db49fda2994afa5a94e797` |
| 3.09 | Odin3-v3.09.zip | 999,701 | `8f63d2ded22ef152efa6e6c2515181a1bf6725fc2c69519b331a06a2de4ff426` |
| 3.07 | Odin3-v3.07.zip | 355,069 | `e87fad4a5b045661fe256c1a537f0640ca05fa2a6cc519450beba57d1b628e51` |
| 3.06 | Odin3-v3.06.zip | 483,233 | `4b090d7e9fbd30a199f1870edd4f9b5e3708f9d835992c6b12f273d60968a627` |
| 3.04 | Odin3-v3.04.zip | 480,340 | `b5887a7ecb64e0f4b9c6d1222f9302f3b2dcd79def2a0b6bf8c629856af463e0` |
| 1.86 | Odin3-v1.86.zip | 204,266 | `3c6821264a6d7236e629e6dbe22fbc163346052085d3fa5b745eb0bddadfc00f` |
| 1.83 | Odin3-v1.83.zip | 203,722 | `b75ed24055e6a65c77e702afaa6e44fa0c2f0d160a36a8863a89e51027a6d1d3` |
| 1.82 | Odin3-v1.82.zip | 203,825 | `4258e93e4cb09398bbdf2b924a1cf798b17dc473a55c476fae68fdfcaf0e29cf` |
| 1.70 | Odin3-v1.70.zip | 202,282 | `bd280c355677eea995ef3080afecaa12e6f6cf2e9f94783402ed56c4b8e052aa` |

## More

- [Odin3 download page](https://getodintool.com/)
- [How to use Odin to flash Samsung firmware](https://getodintool.com/tutorial/)
- [Odin error messages explained](https://getodintool.com/odin-errors/)

If a hash doesn't match, open an issue and tell me the version and where you downloaded it.
