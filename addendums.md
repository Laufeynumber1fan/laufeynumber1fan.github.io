---
layout: default
---
<style>
.wrapper {
  width: 80%;
  max-width: none;
  margin: 0 auto;
}
</style>
```
## Unsorted snippets for general tips. Most of these have been linked from other files.
```
## About [drive partitioning](https://en.wikipedia.org/wiki/Disk_partitioning#Unix-like_systems) in Linux.  
> A common minimal configuration for Linux systems is to use three partitions: one holding the system files mounted on "/" (the root directory), one holding user configuration files and data mounted on /home (home directory), and a swap partition.
  
> When a partition is deleted, its entry is removed from a table and the data is no longer accessible. The data remains on the disk until it is overwritten.
  
## From an [Ubuntu article](https://help.ubuntu.com/community/HowtoPartition/OperatingSystemsAndPartitions)  
> ...when shrinking a partition, you should leave some free space to reduce the likelyhood of fragmentation and make it easier to defragment. Fragmented files will cause your computer to run slower and increase the possibility of file corruption.
A rule of thumb is to keep at least 10% of the partition as free space. Personally, I like at least 25%.
  
## Concerning partitioning and [disk drives](https://en.wikipedia.org/wiki/Hard_disk_drive#Formatting)
It is important align the partitions of disks by the start and end of logical blocks. It would be very ineffecient and error-prone for a partition to appear during a middle of a logical block.
> Data is stored on a hard drive in a series of logical blocks. Each block is delimited by markers identifying its start and end . . . These blocks often contained 512 bytes of usable data, but other sizes have been used.
  
Partitioning should be done in KiB, MiB, and GiB because HDD logical blocks are 512 bytes/block. For example, 1024 KiB is (2^10) * 1024 -> 1048576 bytes -> 2048 blocks. Refer to [table](https://www.techtarget.com/rms/onlineimages/storage-hc_exbibyte_multiples_bytes.png).
  
## Resizing partitions on VMware
`parted /example/drivename` go into the full drive
`print free` find the number
`resizepart X 100GiB` X for partition number and the new end of partition
`quit` to get out parted
  
You'll resize the actual partition but the filesystem will retain it's original size.
Do `df -h` + `fdisk -l` and you can compare the different partition sizes. It will be different.
`resize2fs /example/drivename` to sync the size of file system to the new partition size.

## Find all unique IPs in a zeek conn.log

`cat conn.log | zeek-cut id.orig_h id.resp_h | tr '\t' '\n' | sort | uniq | wc -l`
Why use `tr '\t' '\n'` (replace all \t with \n)?

When doing `cat conn.log | zeek-cut id.orig_h id.resp_h` you get this output:  
```
10.2.8.101      23.198.7.167
10.2.8.101      104.129.55.103
10.2.8.101      104.129.55.103
10.2.8.101      40.126.28.21
10.2.8.101      10.2.8.1
```
By replacing all tabs with newlines the new output will look like:
```
10.2.8.101
23.198.7.167
10.2.8.101
104.129.55.103
10.2.8.101
104.129.55.103
```
This makes it much easier to do `sort | uniq | wc -l`
  
## [Generate zeek logs in JSON format](https://docs.zeek.org/en/master/log-formats.html#zeek-json-format-logs)  
`zeek -C -r foo.pcap LogAscii::use_json=T`  
Make a separate dir for these json logs. This is useful for pretty printing zeek logs with `jq` or with firefox pretty print.  
`zeek-cut` is no longer usable. Use `jq`, for ex. `jq -c '[."id.orig_h", ."query", ."answers"]' dns.log` (see [zeek doc](https://docs.zeek.org/en/master/log-formats.html#zeek-json-format-and-jq) & [jq manual](https://stedolan.github.io/jq/manual/))

## Proper way to report malicious URLs
BAD | GOOD
--- | ---
[dontclickthiswebsite.com](https://www.youtube.com/watch?v=c8tGgVX9__Q) | dontclickthiswebsite[.]com  

Official term is defanging. This is to prevent browsers and text editors from automatically making links to URLs or to stop people from acidentally clicking the link

## Give tshark a GUI by putting pcaps into a web browser  

Step 1: Carve out a small portion of the pcap, use `-Y` to write out a display filter, `-V` to verbosely output the packet, `-T` to convert to Packet Display Markup Language (pdml)  
`tshark -r foo.pcap -Y "tcp.stream eq 0" -V -T pdml > test.xml`  
  
Step 2: convert the xml file into html with xsltproc this is a tool that applies xml styling.  
  
Wireshark already has this stylesheet preinstalled to convert pdml + xml files into html, so you're looking for the file `pdml2html.xsl`  
In kali it's `/usr/share/doc/wireshark/pdml2html.xsl.gz`. It's a gz file so you want to get into that directory and use `gunzip pdml2html.xsl.gz` to decompress it.  
  
Go back to your working dir, the full command is then:  
`xsltproc /usr/share/doc/wireshark/pdml2html.xsl test.xml > test.html`
  
Step 3: open the html into firefox
`firefox test.html`  
Now your shit has a drop down menu for packets, kinda like wireshark

## Trace PS command history
`Get-Content (Get-PSReadlineOption).HistorySavePath`
Useful for seeing if bad scripts had been running

## Installing zeek
Run these commands:
```
echo 'deb http://download.opensuse.org/repositories/security:/zeek/xUbuntu_24.10/ /' | sudo tee /etc/apt/sources.list.d/security:zeek.list
curl -fsSL https://download.opensuse.org/repositories/security:zeek/xUbuntu_24.10/Release.key | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/security_zeek.gpg > /dev/null
sudo apt update
sudo apt install zeek
```
Then set the path variable:  
`export PATH=/usr/local/zeek/bin:$PATH`
or zeek might have been installed in /opt
`export PATH=/opt/zeek/bin:$PATH`

If zeek is not working or the terminal is frozen, you may need to do `apt upgrade` to update zeek or zeek dependencies to the most recent distro version.

## Signing new gpg keys.
So all kali VMs needed a new gpg key because of this kali [blog](https://www.kali.org/blog/new-kali-archive-signing-key/) and this led me to this rabbit hole about how gpg is used to verify the safe installation of apt packages and preventing malicious URLs from providing the downloads.
  
Here's some of the stuff I read.
[You need to know why apt-key add is deprecated](https://askubuntu.com/questions/1286545/what-commands-exactly-should-replace-the-deprecated-apt-key/1307181#1307181)  
[Official doc](https://gnupg.org)  
[Arch wiki tutorial](https://wiki.archlinux.org/title/GnuPG)  
  
It's very easy to assume thatgpg is like adding TLS to file transfers, they achieve the same thing but achieve it differently. The difference is that TLS encrypts the connection but gpg encrypts the file itself and verifies that it is the correct package from the source repository.

## How to make aliases permanent in bash or zsh
Edit the file ~/.bash_aliases 

Add a new `alias` command, for example `alias ll='ls -l`
Save the txt file and run `source ~/.bash_aliases`. 
Verify by running the command `alias` without args.

For zsh, just do `echo "alias ll='ls -l'" >> ~/.zshrc` then `source ~/.zshrc`

This is the same method for other commands like `export` which can make path variables permanent.
`echo "export PATH=/opt/zeek/bin:$PATH" >> ~/.zshrc`  
`source ~/.zshrc`  

## Interactive awk exercises
The author of this [awk tutorial blog](https://learnbyexample.github.io/learn_gnuawk/preface.html) made an interactive tool for the blog's exercises.  
```
python3 -m venv textual_apps
cd textual_apps
source bin/activate
pip install awkexercises
awkexercises
```
Github of the tool [here](https://github.com/learnbyexample/TUI-apps/tree/main/AwkExercises)  

## Executing a command on a remote machine using SSH without getting a shell
For any reason that you want to remotely access a machine without getting a shell you can simply add the command you want to execute after the ssh command.  
`ssh foouser@localhost -p 9999 cat ./data.txt`  

This was useful to learn when I did overtiewire's [bandit level 18 -> 19](https://overthewire.org/wargames/bandit/bandit19.html) where the user's .bashrc logs clients out upon connection.  

## Digest big pcaps
`tshark` has limitations with 1GB+ pcaps which is when other tools like `tcpdump` and `editcap` plays a role in pcap analysis. tshark <ins>can</ins> still parse large pcaps but may take 1 min+ for every command as it is a more robust tool.  

Method 1: Split into multiple files
`tcpdump -r big.pcap -C 1000 -w small.pcap`
If, for example, `big.pcap` is 3GB big, tcpdump's -C (file size) flag may be used to carve `big.pcap` into 1GB pcaps.  
The output of this command will generate `small.pcap` `small.pcap1` `small.pcap2`  
If you're looking for a specific TCP stream or conversation, the entire connection will most likely be captured in a 1GB pcap slice. It's also palatable enough to open the slice on wireshark!