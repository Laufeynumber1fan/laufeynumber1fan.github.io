---
layout: default
title: Tools
nav_include: yes
nav_order: 2
---
<style>
.wrapper {
  width: 60%;
  max-width: none;
  margin: 0 auto;
}
</style>
## alias
TODO
Set aliases for commands <ins>temporarily</ins>.

[How to set an alias permanently in bash or zsh](https://laufeynumber1fan.github.io/addendums.html#how-to-make-aliases-permanent-in-bash-or-zsh)

## awk
TODO
**Fields are represented as $N where N is position**  
1st field `$1`  
3rd field `$3`  
Last field `$NF`  
Get total number of fields `NF`  
Get all fields `$0`  

**Concatenate strings by putting values next to each other**  
This adds a period at the end of every line `awk {print $0 "."}`


`-F` Field separator  

Good tutorial on awk [here](https://learnbyexample.github.io/learn_gnuawk/awk-introduction.html).
For interactive exercises see [addendum](https://laufeynumber1fan.github.io/addendums.html#interactive-awk-exercises)

## apt
TODO
Package manager for Debian, Ubuntu, Linux Mint, and Kali Linux. 

## cat
TODO
Con<ins><b>cat</b></ins>anate files, but mainly used to display text.

`--show-tabs` Show literal characters (for ex. whitespace is replaced with ^I)

## capinfos
TODO
Print information and properties of pcaps. Detects out of order packets.  

`-c` Display packet count.  
`-A` All information (does this with no given arguments).  

## cksum
Get checksums of file. You can choose a hashing algorithm to apply. For MD5 checksums see [md5sum](https://laufeynumber1fan.github.io/tool-journal.html#md5sum). MD5 is usually done for file integrity, SHA256 is used for password storage and digital certificates.

With no options, it does 32 bit CRC by default `cksum foo.exe`  
Do SHA256 hash (you can also do this with <a href=https://laufeynumber1fan.github.io/tool-journal.html#sha256sum>sha256sum</a>)`cksum -a sha256 foo.exe`  

## curl
TODO
Get file from url. Similar to wget

## date
Print system date and time.
  
## df
Print file system usage.

`-a` Include hidden and duplicate file systems.
`-h` Human readable data sizes

## diff
TODO
Compare the files line by line.  
`diff file1 file2`  

## dig
TODO  
DNS lookup utility.  


## fdisk
Interactive drive partitioning.

## gpg  
The successor to apt-key, gpg is a keyring manager, prominently used in apt for signing packages and preventing malicious repos from installing packages. Kinda like TLS in a way.

`--no-default-keyring` Very necessary command that prevents a new keyring into becoming a default keyring. Linux distros already have a configured default keyring so adding one is gonna add a vulnerability.
`--keyring file` Add the file to the list of keyrings<sup>[1]</sup>


Note: Move/store keyrings (.gpg) files in `/usr/share/keyrings/`

Example:
Initialise a new keyring from kali
Get the keyring with [curl](https://laufeynumber1fan.github.io/tool-journal.html#curl), save it to the correct dir  
`sudo curl https://archive.kali.org/archive-keyring.gpg -o /usr/share/keyrings/kali-archive-keyring.gpg`  
Intialise it with gpg  
`gpg --no-default-keyring --keyring /usr/share/keyrings/kali-archive-keyring.gpg -k /usr/share/keyrings/kali-archive-keyring.gpg`

Stackoverflow help: [What commands exactly should replace the deprecated apt-key?](https://askubuntu.com/questions/1286545/what-commands-exactly-should-replace-the-deprecated-apt-key/1307181#1307181)  

## grep
TODO

[1]: [Where GREP came from](https://www.youtube.com/watch?v=NTfOnGZUZDk)  

## gunzip
Unzip `.gz` files, but if you want to unzip `.tar.gz`, use `tar`.

`gunzip foo.gz`

## ifconfig
TODO 


## ip
TODO
Show and change ip configuration.  

`-a` Display all ip configuration  

## jobs
You can "pause" shell commands with `Ctrl + Z` which is then placed on a backlog of `jobs`. This allows you to execute a different command on the same shell while saving the current state of the paused command.  

`jobs` To see current backlog.
`fg %N` Resume a process with N as the process number found in `jobs`. This brings it to the foreground in the shell.  
`bg %N` Resume a process with N as the process number. This resumes the process but it executes in the background.  

See also: [Red Hat blog](https://www.redhat.com/en/blog/jobs-bg-fg)  

## jq
TODO
Used for parsing json files. Good synergy with zeek json logs.

## less
Used for displaying long cmdline outputs  
  
Cmdline args:  
`-S` Really useful when a line of text is too long. -S prevents the line wrapping.  
`-x` Adjusts the number of spaces for every `\t`. For ex. `less -x40` means 40 spaces for every tab.  

Inside the shell:  
How to search: `/PATTERN` and then press `n` to iterate from next or `Shift + n (Uppercase N)` to iterate previously.  
`g` Jump to first line  
`G` Jump to last line  
`f` Forward one window  
`b` Backward one window  
`d` Forward one half-window  
`u` Backward one half-window  
  
TROUBLESHOOTING  
  
Screen full of `~` and (END):  
If `less` is not showing anything and the whole screen is just `~` then that means the piped command may have outputted to `stderr` and not `stdout`.  
For example, the command `tshark -z help` displays the help command for `-z` but the help info is considered an error message. When you pipe this command to `less` nothing gets displayed. 
Do `2>&1` to change the console `std` to `out` and not `err`.  
`tshark -z help 2>&1 | less`

## ls
List files in directory.

List  
`-a` List all files, including hidden files and . & .. dirs.  
`-A` Same as `-a` but without . and .. dirs.  
`-1` List filenames one by one but don't add additional info.  
`-R` List subdirs recursively.  
  
Sort  
`-r` Reverse sort.  
`-t` Time sort  

  
Size  
`-S` Sort by file size.  
`-s` Include size of each file but not human readable.  
`-h` with `-s`, make it human readable sizes.  

## man
TODO
Used for getting help manuals of a command. Opens a `less` of the manual's txt file.

## md5sum 
Get MD5 hash of a file.

Get hash of file `md5sum foo.exe`
Get hash of files in the current directory `md5sum *`

## mkswap
Make a drive into a swap partition. Used in addition to [swapon](https://laufeynumber1fan.github.io/tool-journal.html#swapon).

## mount
Mount partitioned disks  
`--mkdir` Generate a named directory for the drive  

## nano
TODO
Text editor (not installed by default on bash, however [vi](https://laufeynumber1fan.github.io/tool-journal.html#vi) is!)

## nc
TODO  
Netcat. Multi-tool for anything TCP/UDP/IP.  

## nmap
TODO
Port scanner.

`-p` Scan one or a range of ports or all ports. Ex. `-p 1-1000`,  for all ports `-p-`  

## openssl
TODO
A tool for everything ssl/tls. Can be used to connect with SSL encryption, generate digital certs, etc. This tool has a ton of subcommands.

**s_client**
Connect as a client to a host/server using SSL/TLS. `man openssl-s_client`  
`-connect [host:port]`  
`-quiet` Supresses session information. Also enters the openssl into a "basic command" mode. See CONNECTED COMMANDS (BASIC) in s_client man page.  

Basic ex. `openssl s_client -connect localhost:1001`  

## pacstrap
TODO
Package manager for ArchLinux distros.  

## parted
Shell-based drive partitioning

## ping
TODO

## rm
Remove files, directories, etc...  

`-d` Delete empty dirs.
`-f` Force file deletion, no confirmation or logging
`-i` Prompt yes/no for every file  
`-I` Prompt yes/no for every 3 files  
`-r` Recursively delete files in dir and then delete the dir itself (you can also remove folders with [rmdir](https://laufeynumber1fan.github.io/tool-journal.html#rmdir)) 
`-v` Verbose  

**<u>Examples</u>**  
`rm foo.txt` Delete file  
`rm ../foo.txt` Delete file in parent directory  
`rm -fvr foobar` Force delete everything inside foobar  

## rmdir
TODO
Remove folder(s)
  
## route
TODO
Show and change routing table

## sed
TODO

## sha256sum  
Get sha256 hash.

Get hash of a file `sha256sum foo.txt`  
Get hash of files in the current directory `sha256sum *`  

## sfdisk
Non-interactive drive partitioning (like fdisk).
  
## sort
`-n` Numeric sort  
`-t -k` Sort based on values from a different column<sup>[1]</sup>  
`-r` Reverse sort  
`-u` Unique-only (remove duplicates)  
`-T` Specify tmp directory<sup>[2]</sup>

[1]: `-t:` is field separator, `-k` is sort based on location. To sort based on the 2nd value in .txt file that looks like this: 
```
1: Mark
2: James
3: Matthew
4: Simon
5: Peter
6: Andrew
```
Use this to sort the names on the 2nd column `sort -t: -k2 foo.txt`

[2]: With really big outputs, `sort` may not have enough space inside it's tmp directory to actually do sorting. Do `-T .` to specify the current directory to be used as temp space.  

## ssh
OpenSSH client.  
`ssh user@host`<sup>[1]</sup>  

`-p` Specify a port (default is 22).
`-l` Specify a user (2nd method).
`-i` Specify an identity file, a .key file that contains a SSH private key.

[1]: [Execute a command with ssh](https://laufeynumber1fan.github.io/addendums.html#executing-a-command-on-a-remote-machine-using-SSH-without-getting-a-shell)

## stty
Funny terminal settings commands

For example do `stty -icrnl` to disable the ENTER button to translate to a newline in terminal. `stty icrnl` to reenable. Read the man pages.

## swapon  
Adds a swap partitions to `/etc/fstab` to mount it.

`--show` Print swap partitions

## tar
Archive tool that compresses or decompresses folders. Makes tarballs.  
  
`-c` Create tar archive  
`-z` Apply gunzip while compressing or decompressing. Use for `.gz` extensions  
`-v` Verbose  
`-f` File/Folder name  
`-x` Decompress archives  
  
Examples:
Make tar.gz `tar -czvf [tar.gz name] [folder/file you want to tar]`  
Extract tar.gz `tar -xzvf foo.tar.gz`  

## tcpdump  
Cmdline pcap analyser, similar to tshark but lightweight. Has simpler filters.  
**Uses [capture filters](https://www.tcpdump.org/manpages/pcap-filter.7.html) for reading and capturing pcaps**  

`-r` Read pcap.  
`-c [n]` Limit output to n number of packets.  
`-tttt` Switch time to UTC.  
`-tt` Switch time to epoch.  
`--time-stamp-precision` With `-tt` set decimal places.<sup>[1]</sup>  
`-n` Don't convert IPs to hostnames.  
`-X` Print ASCII and hex of payloads. 
`-e` Print link level/ethernet packet header.
`-w` Make pcap from packets captured by filter.  

Only DNS packets `tcpdump -r foo.pcap port 53`  
Exclude outgoing (dst) DNS connections `tcpdump -r foo.pcap not dst port 53`  
Combination of filters `tcpdump -r foo.pcap not port 53 and not port 22`
Specific source IP `tcpdump -r foo.pcap src 192.168.0.1`
Combination of filter and args `tcpdump -r foo.pcap -ttttnXc 5 port 80`

Further reading:  
[Digest big pcaps](https://laufeynumber1fan.github.io/addendums.html#digest-big-pcaps)  

  
## tr  
Translate, replace, delete characters. Applies translations line by line.

Replace tabs into new lines `cat conn.log | zeek-cut id.orig_h id.resp_h | tr '\t' '\n' | sort | uniq | wc -l`  
Lowercase to uppercase `echo "hello world" | tr 'a-z' 'A-Z'`  
Reverse pipe `tr " " "\t" < input.txt`  
If a text has inconsistent spaces, use `-s` to squeeze repeated instances into a single translation `tr -s " " "\t" < input.txt`

## tshark
Cmdline wireshark, wireshark filters are processed as cmdline arguments.  
**Only uses [capture filters](https://www.tcpdump.org/manpages/pcap-filter.7.html) for capturing pcaps `-f`. Only uses display filters<sup>refs:[1, ](https://www.wireshark.org/docs/man-pages/wireshark-filter.html)</sup><sup>[2, ](https://www.wireshark.org/docs/dfref/)</sup><sup>[3](https://tshark.dev/setup/)</sup> for reading pcaps `-Y`.**
  
`-f` Capture packets with pcap-filters/tcpdump expressions.  
`-Y` Apply [display filters](https://www.wireshark.org/docs/dfref/)<sup>[1]</sup>.  
`-T` Specify different output formats like `json`, `text`, `fields`<sup>[1]</sup>, etc.  
`-D` Lists all available interfaces to listen for traffic.  
`-V` Display all packet information verbosely. Use injunction with `-Y`<sup>[2]</sup>.  
`-n` Disable name resolution.  
`-N` Name resolving options<sup>[4]</sup>.  
`-q` Be more quiet, ideally use with `-z`.  
`-x` Display hex & ASCII dump.  
`-E` Display options for headers when using `-T`<sup>[3]</sup>.  
`--export-objects` Export files in tshark, makes a separate directory.<sup>[5]</sup>  
  
Advanced help:  
`-G` Prints every wireshark filter. Use injunction with `egrep "\sPATTERN\." | less -Sx40`.  
`-G help` more info.  
`-G protocols` Find abbreviations of protocols.  
  
Statistics:  
`-z` Protocol Hierarchy  
`-z help | less` Display help  

[1a]: `-Y`, `-T fields`, `-e` are the bread and butter, `-Y` finds packets based on the display filter. `-T fields` and `-e` modifies the output to specific fields. See [1b].  
[4]: Specify name resolution options, by default tshark already does `-N dmN`. However `-N dmn` is probably more useful when reading pcaps because it will get name resolution from the DNS packets inside the pcap instead of external resolution (`-N N`) does this.  

<ins>Examples</ins>:  
[1b]: Display only dns queries `tshark -r foo.pcap -Y "dns.flags.response == 0" -T fields -e dns.qry.name`  
[2a]: To display packet 100 verbosely `tshark -r foo.pcap -Y frame.number==100 -V`  
[2b]: To display a specific tcp stream versbosely `tshark -r foo.pcap -Y "tcp.stream eq 0" -V`  
[3]: Add header fields for custom columns `tshark -r foo.pcap -E header=y -T fields -e ip.src -e ip.dst -e ip.proto -c 5 | less -sX40`  
[5]: Export http files, exports it to a dir called files `tshark -r foo.pcap --export-objects http,files`  

Filter for TCP SYN packets then show src and dst ip with dst ports of the connection then sort for most connections `tshark -r foo.pcap -Y tcp.flags==2 -T fields -e ip.src -e ip.dst -e tcp.dstport | sort | uniq -c | sort -n`  
Filter http content-length which is useful for seeing payload sizes `tshark -r foo.pcap -Y http -T fields -e frame.number -e http.content_length`  
View filter documentation in terminal `tshark -G | egrep '\sip\.' | less -S -x40`  
Find tcp stream number of tcp data payloads `tshark -r foo.pcap -Y tcp.completeness==7 -T fields -e http.request.uri -e tcp.stream | less`
Follow tcp stream 0 data payload `tshark -r foo.pcap -qz follow,tcp,ascii,0`  

## vi
Antediluvian text editor, installed by default basically everywhere. Very interesting history lesson by itself.  
Use `vimtutor` for a complete crash course.  
  
`h, j, k, l` Move cursor left, bottom, top, or right.  
`:q` Quit.  
`:q!` Force quit.  
`:wq` Write and quit.  
`y` Copy text (yank).  
`p` Paste text.  
`ESC` Go to command mode.  
`v` Go to visual mode (selects text so use it with y).  
`i` Go to insert mode.  
`a` Go to insert mode but append.  
`o` Go to insert mode but on a new line.  
`dd` Delete current line.  
`/` Search ahead; n for next occurrence, N for previous occurrance.  
`?` Same as / but it searches patterns behind the cursor.  
`u` Undo.  
`U` Undo the entire line.  
`Ctrl + r` Redo.  
`r` Replace char on cursor.  

MOTIONS - moves the cursor but can be combined with commands.  
`w` jump to the next word, selecting its 1st char.  
`e` until the end of the current word without selecting the next word.  
`$` go to the end of the current line.  
`2, 3, 4` Numbers specify repeats of the same motion<sup>[1]</sup>. 

<ins>Examples</ins>  
`:help wq` To get help on a specific command, this one is for wq. This actually opens a 2nd instance of vi, so you use `:q` to get out of help.  
[1]: `2w` Jump 2 words, `3$` Go to the end of current line + jump 2 lines.  
[2]:

## ufw  
Linux netfilter firewall. Installed by default on ubuntu.  

`ufw disable` Turn off and disabled on startup.  
`ufw enable` Turn on.  

## uname  
Print OS info

`-a` Print all info  

## uniq
TODO  
Filter ADJACENT matching lines and merges those repeating lines into 1. It's not magic, it's a compression algorithm.  
`-c` Adds a column for the number of occurrances of the value  

## whereis  
Print path locations of command aliases

## whois  
whois lookup on command line.  

`-H` Hide legal disclaimers.  

Example: `whois google.com | less`

## xmllint  
  
Check an xml file for format errors<sup>[[1]](https://laufeynumber1fan.github.io/tool-journal.html#tshark)</sup> `xmllint foo.xml --noout`  
  
[1]: Used in converting tshark pdml to xml for viewing pcaps in web browsers.
  
## xsltproc  
  
Apply an XSLT stylesheet to an XML to convert it to html `xsltproc foo.xsl foo.xml > foo.html`  
Get the XLST stylesheet from wireshark and apply it to an XML<sup>[[1]](https://laufeynumber1fan.github.io/tool-journal.html#tshark)</sup> `xsltproc /usr/share/wireshark/pdml2html.xsl foo.xml > foo.html`
  
[1]: Used in converting tshark pdml to xml for viewing pcaps in web browsers.
  
## xxd

Get hex of output

`-p` remove offset

Get hex of "hello world" `echo -n "hello world" | xxd`
Without format, get hex of "hello world" `echo -n "hello world" | xxd -p`

## zeek
[How to install](https://laufeynumber1fan.github.io/addendums.html#installing-zeek)  
