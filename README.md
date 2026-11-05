# Odin3 checksums

SHA-256 checksums for the Odin3 ZIP files hosted at [getodintool.com](https://getodintool.com/older-versions/).

I keep this list so you can compare your downloaded ZIP with the copy hosted on Get Odin Tool. On November 5, 2026, I downloaded all 21 archives again and checked their sizes and SHA-256 values. The byte sizes match the table below, and all 21 hashes match both [SHA256SUMS](SHA256SUMS) and the website's download cards.

## What this does and doesn't tell you

A matching hash identifies the reference copy used for this list. It doesn't certify the publisher, assess malicious behavior or establish that the program will work with your Galaxy. Keep the download source, Windows security notices and device requirements as separate checks.

The [v3.14.4 ZIP](https://getodintool.com/wp-content/uploads/2026/09/Odin3-v3.14.4.zip) and [v3.14.1 ZIP](https://getodintool.com/wp-content/uploads/2026/09/Odin3-v3.14.1.zip) contain EXEs with matching 2,016,256-byte `.text` sections. Their whole-file hashes differ. Both packages include `SS_DL.dll`, and those DLL files differ too; v3.14.4 also includes `cpprest141_2_10.dll`.

Matching one executable section does not establish equal behavior for the complete packages. The [package comparison](https://getodintool.com/latest/) explains the limits of that finding. These checks did not run either EXE or flash a device.

## How to read the executable metadata

The [executable metadata CSV](odin-executable-metadata.csv) records the EXE path, byte size and SHA-256 for all 21 archives I checked on November 5, 2026. It also includes the PE header and version fields from each EXE. Start with the row for your downloaded ZIP.

The two hash columns apply to different files. Use `zip_sha256` for the original ZIP and `executable_sha256` for the extracted program.

For example, open PowerShell in the extracted `Odin3-v3.12.7` folder and run:

```powershell
Get-FileHash -LiteralPath '.\Odin3 v3.12.7.exe' -Algorithm SHA256
```

Compare the result with `executable_sha256` in the `Odin3-v3.12.7.zip` row. For the single-file `certutil` or `shasum` examples below, replace the ZIP name with the EXE filename in double quotes.

For versions, keep the two field types separate. The `fixed_file_version` and `fixed_product_version` columns hold the numeric [VS_FIXEDFILEINFO](https://learn.microsoft.com/en-us/windows/win32/api/verrsrc/ns-verrsrc-vs_fixedfileinfo) values. The `file_version_string` and `product_version_string` columns hold [StringFileInfo](https://learn.microsoft.com/en-us/windows/win32/menurc/stringfileinfo) text.

Here are two examples from the checked files:

| ZIP | Version field | Fixed numeric value | Text value |
| --- | --- | --- | --- |
| Odin3-v3.12.7.zip | File version | `2016.8.10.1` | `2017.4.25.1` |
| Odin3-v3.12.4.zip | Product version | `3.12.5.0` | `3.12.4.0` |

Keep both values when comparing files. They record metadata in these particular EXEs. Support for a Windows version or a Galaxy model needs separate testing.

## How to check a file

On Windows, open PowerShell in the folder with the ZIP and run:

```
Get-FileHash .\Odin3-v3.14.1.zip -Algorithm SHA256
```

Read the value under Hash and compare it with this file's table entry. Microsoft's [Get-FileHash reference](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/get-filehash) documents the command.

Or use [certutil in Command Prompt](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/certutil):

```
certutil -hashfile Odin3-v3.14.1.zip SHA256
```

With `shasum` on macOS or Linux:

```
shasum -a 256 Odin3-v3.14.1.zip
```

The [shasum manual](https://perldoc.perl.org/shasum) documents the SHA-256 option and checklist format.

If you have the complete collection, put all 21 ZIPs and `SHA256SUMS` in one folder. With [GNU Coreutils](https://www.gnu.org/software/coreutils/manual/html_node/sha2-utilities.html), run:

```
sha256sum -c SHA256SUMS
```

With `shasum`, use:

```
shasum -a 256 -c SHA256SUMS
```

These checklist commands expect the listed files to be present. A missing-file error means that entry could not be checked. If you downloaded just one ZIP, use its single-file command above instead.

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

If your result differs, open an issue with the ZIP version, byte size, calculated SHA-256 and download URL. Those details let me compare the same file you checked.
