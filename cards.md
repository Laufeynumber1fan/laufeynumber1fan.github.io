---
layout: default
title: Cards
---
<meta property="description" content="Quick flashcards by a cybersec student. It covers basic computer networking knowledge and pcap analysis.">

<style>
  .page-content > .wrapper {
    max-width: none;
    overflow:visible;
  }
  
  #cards-container {
    position: relative;
    overflow: hidden;
    margin: auto;
    height: 75vh;
  }

  #cards-wrapper {
    display: flex;
    width: 100%;
    height: 100%;
    text-align: center;
    transition: transform 0.3s ease-in-out;
  }

  .card {
    flex: 0 0 100%;
  }

  .cards-btn {
    position: relative;
    display: flex;
    background-color:rgb(225, 225, 225);
    border: 0;
    border-radius: 2px;
    position: relative;
    justify-content: center;
    align-content: center;
    flex-direction: column;
    height: 75vh;
    width: 10vh;
    font-size: 3em;
    color:rgb(44, 44, 44);
    transition: color 0.1s, background-color 0.1s;
  }
  
  .cards-btn:hover {
    background-color:rgb(241, 241, 241);
  }

  .card-content {
    display: block;
    margin: 18vh auto 0 auto;
    width: 55%;
    min-height: 30%;
    border-radius: 5px;
    padding: 10px;
    padding-top: 3em;
  }

  .prev {
    float: left;
  }

  .next {
    float: right;
  }

  .answer {
    display: inline-block;
    background-color:rgb(255, 255, 255);
    color: transparent;
    padding: 0.65em 1em;
    border-radius: 5px;
    min-width: 40%;
    max-width: 60%;
    cursor: pointer;
    transition: color 0.5s ease, opacity 0.5s ease;
    user-select: none;
  }

  .hidden {
    display: none;
  }

  .hidden:checked + .answer {
    color: black;
    opacity: 1;
  }

  ..answer:not(:hover) {
    opacity: 0.7;
  }

  .s1 {
    background-color: rgb(255, 221, 221);
  }
  
  .s2 {
    background-color: rgb(240, 240, 221);
  }

  .s3 {
    background-color: rgb(221, 221, 255);
  }

  .s4 {
    background-color: rgb(216, 239, 227);
  }
  
  .s5 {
    background-color: rgb(227, 239, 216);
  }

  .s5 {
    background-color: rgb(227, 239, 216);
  }

  .s6 {
    background-color: rgb(239, 227, 216);
  }

  .s7 {
    background-color: rgb(216, 239, 227);
  }
  
  .s8 {
    background-color: rgb(227, 216, 239);
  }
  
  .s9 {
    background-color: rgb(216, 216, 239);
  }

  .s10 {
    background-color: rgb(255, 236, 216);
  }

  .s11 {
    background-color: rgb(200, 200, 225);
  }

  .s12 {
    background-color: rgb(245, 210, 245);
  }

  .s13 {
    background-color: rgb(210, 245, 245);
  }

  .s14 {
    background-color: rgb(142, 156, 174);
  }
  
  .s15 {
    background-color: rgb(161, 88, 88);
  }

  .s16 {
    background-color: #7db04f;
  }

  .s17 {
    background-color: #4fb052;
  }

  .s18 {
    background-color: #adb04f;
  }

  .s19 {
    background-color: #824fb0;
  }

  .s20 {
    background-color: #4fadb0;
  }

  .s21 {
    background-color: #b0524f;
  }

  .s22 {
    background-color: #b04f7d;
  }

  .s23 {
    background-color: #b0383a;
  }

  .s24 {
    background-color:rgb(83, 175, 82);
  }

  .s25 {
    background-color: #383ab0;
  }

  .s26 {
    background-color: #b07238;
  }

  .s27 {
    background-color:rgb(199, 111, 157);
  }

  .s28 {
    background-color: #76b038;
  }

  .s29 {
    background-color: #38b0ae;
  }

  .s30 {
    background-color: #7238b0;
  }

  .s31 {
    background-color: #583c96;
  }

  .s32 {
    background-color: #96583c;
  }

  .s33 {
    background-color: #3c9658;
  }

  .s34 {
    background-color: #8a4641;
  }

  .s35 {
    background-color: #618a41;
  }

  .s36 {
    background-color: #41868a;
  }

  .s37 {
    background-color: #6a418a;
  }

  .s38 {
    background-color: #864686;
  }

  .s39 {
    background-color: #468646;
  }

  .s40 {
    background-color: #a3605c;
  }
</style>


<button class='cards-btn prev' aria-keyshortcuts='Left'>&#x276E;</button>
<button class='cards-btn next' aria-keyshortcuts='Right'>&#x276F;</button>
<div id='cards-container'>
  <div id='cards-wrapper'>
    <div class='card'>
        <div class='card-content'>
            <img src='/src/laufey.png' style='margin:auto;display:block;'>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s1'>
            <p>1. What does TCP stand for?</p>
            <input type='checkbox' id='c1' class='hidden'>
            <label for='c1' class='answer'>Transmission Control Protocol.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s3'>
            <p>2. What port is TCP?</p>
            <input type='checkbox' id='c2' class='hidden'>
            <label for='c2' class='answer'>TCP is a transport protocol, it doesn't have assigned ports.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s4'>
            <p>3. What port is DNS?</p>
            <input type='checkbox' id='c3' class='hidden'>
            <label for='c3' class='answer'>TCP/UDP port 53.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s2'>
            <p>4. What is SMTP?</p>
            <input type='checkbox' id='c4' class='hidden'>
            <label for='c4' class='answer'>Simple Mail Transfer Protocol. For email used by mail servers.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s10'>
            <p>5. Name the TCP/IP layer that TCP belongs to.</p>
            <input type='checkbox' id='c5' class='hidden'>
            <label for='c5' class='answer'>Transport Layer.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s6'>
            <p>6. Which OSI layer does a router operate in.</p>
            <input type='checkbox' id='c6' class='hidden'>
            <label for='c6' class='answer'>Layer 3 (Network).</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s1'>
            <p>7. What feature gives switches layer 3 functionality?</p>
            <input type='checkbox' id='c7' class='hidden'>
            <label for='c7' class='answer'>Inter-VLAN routing.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s9'>
            <p>8. What port is DHCP?</p>
            <input type='checkbox' id='c8' class='hidden'>
            <label for='c8' class='answer'>UDP port 67 for requests and 68 for replies.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s3'>
            <p>9. What port is ICMP?</p>
            <input type='checkbox' id='c9' class='hidden'>
            <label for='c9' class='answer'>Doesn't have one!</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s4'>
            <p>10. What does ICMP stand for?</p>
            <input type='checkbox' id='c10' class='hidden'>
            <label for='c10' class='answer'>Internet Control Message Protocol.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s1'>
            <p>11. What does DHCP stand for?</p>
            <input type='checkbox' id='c11' class='hidden'>
            <label for='c11' class='answer'>Dynamic Host Configuration Protocol.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s8'>
            <p>12. What does OSI layer 6 do?</p>
            <input type='checkbox' id='c12' class='hidden'>
            <label for='c12' class='answer'>Data encryption and compression.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s1'>
            <p>13. What port is FTP?</p>
            <input type='checkbox' id='c13' class='hidden'>
            <label for='c13' class='answer'>FTP servers use TCP port 21, FTP clients use TCP port 20.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s8'>
            <p>14. What does SSH do?</p>
            <input type='checkbox' id='c14' class='hidden'>
            <label for='c14' class='answer'>Creates an encrypted tunnel for communication.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s6'>
            <p>15. What's the difference between POP3 and SMTP?</p>
            <input type='checkbox' id='c15' class='hidden'>
            <label for='c15' class='answer'>STMP sends email from sender to reciever's mail server.<br>POP3 is used by the receiver to fetch mail from the mail server.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s7'>
            <p>16. What does OSI layer 1 do?</p>
            <input type='checkbox' id='c16' class='hidden'>
            <label for='c16' class='answer'>Converts binary into electronic signals, through wire, wifi, cellular, etc.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s9'>
            <p>17. What does UDP stand for?</p>
            <input type='checkbox' id='c17' class='hidden'>
            <label for='c17' class='answer'>User Datagram Protocol.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s5'>
            <p>18. Do LANs use routing tables?</p>
            <input type='checkbox' id='c18' class='hidden'>
            <label for='c18' class='answer'>Yes, if it uses a distance vector algorithm.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s9'>
            <p>19. Which OSI layer do switches mainly operate?</p>
            <input type='checkbox' id='c19' class='hidden'>
            <label for='c19' class='answer'>Layer 2 (Data Link).</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s5'>
            <p>20. Name the layers of the TCP/IP model.</p>
            <input type='checkbox' id='c20' class='hidden'>
            <label for='c20' class='answer'>Network Access, Internet, Transport, Application.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s11'>
            <p>21. What is the shorthand for the subnet mask 255.255.252.0?</p>
            <input type='checkbox' id='c21' class='hidden'>
            <label for='c21' class='answer'>/22</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s3'>
            <p>22. What is the broadcast address for the network 172.25.0.0/24?</p>
            <input type='checkbox' id='c22' class='hidden'>
            <label for='c22' class='answer'>172.25.0.255</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s7'>
            <p>23. What class is the IP address 10.305.1.256?</p>
            <input type='checkbox' id='c23' class='hidden'>
            <label for='c23' class='answer'>It's not a valid IP address!</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s1'>
            <p>24. What class is the IP address 8.8.8.8?</p>
            <input type='checkbox' id='c' class='hidden'>
            <label for='c' class='answer'>Class A.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s9'>
            <p>25. What is the full subnet mask for /28?</p>
            <input type='checkbox' id='c25' class='hidden'>
            <label for='c25' class='answer'>255.255.255.240</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s4'>
            <p>26. What is the valid host range for the network 192.168.0.64/26?</p>
            <input type='checkbox' id='c26' class='hidden'>
            <label for='c26' class='answer'>192.168.0.65-192.168.0.126</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s2'>
            <p>27. How many usable IP addresses are in a /30 subnet?</p>
            <input type='checkbox' id='c27' class='hidden'>
            <label for='c27' class='answer'>4</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s7'>
            <p>28. What is the first usable host IP address in the network 251.156.11.64/15?</p>
            <input type='checkbox' id='c28' class='hidden'>
            <label for='c28' class='answer'>251.156.11.65</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s9'>
            <p>29. What is the full subnet mask for /24?</p>
            <input type='checkbox' id='c29' class='hidden'>
            <label for='c29' class='answer'>255.255.255.0</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s1'>
            <p>30. What is the broadcast address for the network 192.168.2.0/25?</p>
            <input type='checkbox' id='c30' class='hidden'>
            <label for='c30' class='answer'>192.168.2.127</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s7'>
            <p>31. What is valid host range for the network 10.1.0.64/27?</p>
            <input type='checkbox' id='c31' class='hidden'>
            <label for='c31' class='answer'>10.1.0.65-10.1.0.94</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s4'>
            <p>32. What is the full subnet mask for /18?</p>
            <input type='checkbox' id='c32' class='hidden'>
            <label for='c32' class='answer'>255.255.192.0</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s7'>
            <p>33. What class is the IP address 172.0.0.1?</p>
            <input type='checkbox' id='c33' class='hidden'>
            <label for='c33' class='answer'>Class B.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s10'>
            <p>34. What is the default gateway for the IP address 192.168.12.254/24?</p>
            <input type='checkbox' id='c34' class='hidden'>
            <label for='c34' class='answer'>192.168.12.1</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s11'>
            <p>35. What is the shorthand for the subnet mask 255.255.255.254?</p>
            <input type='checkbox' id='c35' class='hidden'>
            <label for='c35' class='answer'>/31</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s5'>
            <p>36. What is the valid host range for the network 10.10.1.64/28?</p>
            <input type='checkbox' id='c36' class='hidden'>
            <label for='c36' class='answer'>10.10.1.65-10.10.1.78</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s1'>
            <p>37. What is the default gateway for the IP address 200.10.10.3/30</p>
            <input type='checkbox' id='c37' class='hidden'>
            <label for='c37' class='answer'>200.10.10.1</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s8'>
            <p>38. What network does the IP address 192.168.0.25/25 belong to?</p>
            <input type='checkbox' id='c38' class='hidden'>
            <label for='c38' class='answer'>192.168.0.0</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s5'>
            <p>39. What network does the IP address 172.16.50.16/23 belong to?</p>
            <input type='checkbox' id='c39' class='hidden'>
            <label for='c39' class='answer'>172.16.50.0</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s2'>
            <p>40. What is the default gateway for the IP address 10.0.0.130/26</p>
            <input type='checkbox' id='c40' class='hidden'>
            <label for='c40' class='answer'>10.0.0.129</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s7'>
            <p>41. Can a router provide DHCP services?</p>
            <input type='checkbox' id='c41' class='hidden'>
            <label for='c41' class='answer'>Yes, routers can provide DHCP to its local subnet.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s2'>
            <p>42. What does ARP stand for?</p>
            <input type='checkbox' id='c42' class='hidden'>
            <label for='c42' class='answer'>Address Resolution Protocol.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s9'>
            <p>43. Why does a device need a MAC address?</p>
            <input type='checkbox' id='c43' class='hidden'>
            <label for='c43' class='answer'>It's used for layer 2/LAN routing. Without a MAC address it cannot use a network interface and Ethernet.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s2'>
            <p>44. Why would you refer to the TCP/IP model instead of the OSI model?</p>
            <input type='checkbox' id='c44' class='hidden'>
            <label for='c44' class='answer'>The TCP/IP model describes Internet communication. The OSI model is outdated.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s10'>
            <p>45. What does NAT stand for?</p>
            <input type='checkbox' id='c45' class='hidden'>
            <label for='c45' class='answer'>Network Address Translation.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s5'>
            <p>46. Why would a router do port forwarding?</p>
            <input type='checkbox' id='c46' class='hidden'>
            <label for='c46' class='answer'>Routers only have a single public IP address, in order to route traffic to the correct private IP, the public IP uses ports to identify the correct private IP.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s1'>
            <p>47. Can a router perform NAT?</p>
            <input type='checkbox' id='c47' class='hidden'>
            <label for='c47' class='answer'>Yes.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s7'>
            <p>48. Can a router do ARP?</p>
            <input type='checkbox' id='c48' class='hidden'>
            <label for='c48' class='answer'>Yes. Just like any device in the network, a router can also use ARP to build its own ARP table.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s10'>
            <p>49. What's the difference between HTTP and HTTPS?</p>
            <input type='checkbox' id='c49' class='hidden'>
            <label for='c49' class='answer'>HTTPS uses SSL/TLS to encrypt web traffic, HTTP does not encrypt its traffic so it is less secure.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s2'>
            <p>50. What TCP/IP layer does FTP work in?</p>
            <input type='checkbox' id='c50' class='hidden'>
            <label for='c50' class='answer'>Layer 4 (Application).</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s9'>
            <p>51. Can a host also be a server?</p>
            <input type='checkbox' id='c51' class='hidden'>
            <label for='c51' class='answer'>Yes. As long as they don't use the same port.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s11'>
            <p>52. How many bits are in a IPv4 address?</p>
            <input type='checkbox' id='c52' class='hidden'>
            <label for='c52' class='answer'>32 bits.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s10'>
            <p>53. Which protocol is implemented to mitigate IPv4 address exhaustion?</p>
            <input type='checkbox' id='c53' class='hidden'>
            <label for='c53' class='answer'>NAT.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s2'>
            <p>54. What port is HTTP and HTTPS?</p>
            <input type='checkbox' id='c54' class='hidden'>
            <label for='c54' class='answer'>HTTP uses TCP port 80, HTTPS uses TCP port 443.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s7'>
            <p>55. What does DNS do with URLs and IPs?</p>
            <input type='checkbox' id='c55' class='hidden'>
            <label for='c55' class='answer'>It translate network IP addresses into human-readable urls in order to easily connect to domains and websites.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s2'>
            <p>56. List 5 common DNS record types.</p>
            <input type='checkbox' id='c56' class='hidden'>
            <label for='c56' class='answer'>A, AAAA, CNAME, NS, MX.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s5'>
            <p>57. Why would an online banking site need SSL/TLS?</p>
            <input type='checkbox' id='c57' class='hidden'>
            <label for='c57' class='answer'>Sensitive information like passwords must be encrypted with SSL/TLS or else it will be human-readable and then stolen.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s4'>
            <p>58. What role does an IDS/IPS do inside a network?</p>
            <input type='checkbox' id='c58' class='hidden'>
            <label for='c58' class='answer'>They are network security devices similar to firewalls.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s10'>
            <p>59. What layer 2 technology connects devices inside a network?</p>
            <input type='checkbox' id='c59' class='hidden'>
            <label for='c59' class='answer'>Ethernet.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s12'>
            <p>60. What role do router ACLs do inside a network?</p>
            <input type='checkbox' id='c60' class='hidden'>
            <label for='c60' class='answer'>ACLs are basic traffic filters that allow or block certain IP addresses into the network.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s11'>
            <p>61. Can switches have ACLs?</p>
            <input type='checkbox' id='c61' class='hidden'>
            <label for='c61' class='answer'>Yes, if it enabled inter-VLAN routing.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s4'>
            <p>62. Which bytes of a MAC address identify the manufacturer?</p>
            <input type='checkbox' id='c62' class='hidden'>
            <label for='c62' class='answer'>The first 3 bytes.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s1'>
            <p>63. What is nbns?</p>
            <input type='checkbox' id='c63' class='hidden'>
            <label for='c63' class='answer'>It's a network protocol for NetBIOS name resolution.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s7'>
            <p>64. What port does Kerberos use?</p>
            <input type='checkbox' id='c64' class='hidden'>
            <label for='c64' class='answer'>It mainly uses UDP port 88 but it may use others.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s12'>
            <p>65. What is a DHCP lease?</p>
            <input type='checkbox' id='c65' class='hidden'>
            <label for='c65' class='answer'>It is a temporary IP address leased by the DHCP server for a limited time.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s10'>
            <p>66. What routing algorithms do WAN use?</p>
            <input type='checkbox' id='c66' class='hidden'>
            <label for='c66' class='answer'>BGP (Border Gateway Protocol).</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s12'>
            <p>67. What does the PSH flag do in TCP packets?</p>
            <input type='checkbox' id='c67' class='hidden'>
            <label for='c67' class='answer'>It's the push flag meant to prioritise this packet and bypass buffering.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s13'>
            <p>68. In Ethernet frames, what is MTU?</p>
            <input type='checkbox' id='c68' class='hidden'>
            <label for='c68' class='answer'>Maximum Transmission Unit for limiting the size of Ethernet frames.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s2'>
            <p>69. What are the three steps of the TCP Handshake?</p>
            <input type='checkbox' id='c69' class='hidden'>
            <label for='c69' class='answer'>SYN, SYN-ACK, ACK</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s3'>
            <p>70. What flags are used to end a TCP connection?</p>
            <input type='checkbox' id='c70' class='hidden'>
            <label for='c70' class='answer'>FIN and ACK.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s1'>
            <p>71. What is a broadcast IP address?</p>
            <input type='checkbox' id='c71' class='hidden'>
            <label for='c71' class='answer'>It's the address used to send packets to every device in the subnet.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s5'>
            <p>72. What does the MAC address FF:FF:FF:FF:FF:FF mean?</p>
            <input type='checkbox' id='c72' class='hidden'>
            <label for='c72' class='answer'>It's the broadcast MAC address for the local network.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s12'>
            <p>73. What is a firewall policy?</p>
            <input type='checkbox' id='c73' class='hidden'>
            <label for='c73' class='answer'>It defines the traffic that firewalls allow or block in the network.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s2'>
            <p>74. What does it mean when a firewall policy is default deny?</p>
            <input type='checkbox' id='c74' class='hidden'>
            <label for='c74' class='answer'>All traffic is blocked.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s13'>
            <p>75. How do firewalls filter traffic based on website data?</p>
            <input type='checkbox' id='c75' class='hidden'>
            <label for='c75' class='answer'>By inspecting the data payload of HTTP packets.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s10'>
            <p>76. How do firewalls filter traffic based on website data?</p>
            <input type='checkbox' id='c76' class='hidden'>
            <label for='c76' class='answer'>By inspecting the data payload of HTTP packets.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s12'>
            <p>77. What is anomaly-based detection in network security?</p>
            <input type='checkbox' id='c77' class='hidden'>
            <label for='c77' class='answer'>A benchmark of normal activity is recorded, any irregular activity is then considered anomalous.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s2'>
            <p>78. What is signature-based detection in network security?</p>
            <input type='checkbox' id='c78' class='hidden'>
            <label for='c78' class='answer'>If traffic matches the signatures of malware the traffic is blocked.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s13'>
            <p>79. How do firewalls inspect the packets with encrypted payloads?</p>
            <input type='checkbox' id='c79' class='hidden'>
            <label for='c79' class='answer'>Through SSL/TLS inspection. Firewalls hold private keys of incoming traffic.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s1'>
            <p>80. Can firewall be software or hardware?</p>
            <input type='checkbox' id='c80' class='hidden'>
            <label for='c80' class='answer'>It can be both.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s10'>
            <p>81. What is polymorphic malware?</p>
            <input type='checkbox' id='c81' class='hidden'>
            <label for='c81' class='answer'>Malware that dynamically changes its signature to bypass detection.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s12'>
            <p>82. What is a worm?</p>
            <input type='checkbox' id='c82' class='hidden'>
            <label for='c82' class='answer'>Malicious code that self-replicates inside a network.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s4'>
            <p>83. What is a rootkit?</p>
            <input type='checkbox' id='c83' class='hidden'>
            <label for='c83' class='answer'>Malware that modify the OS's functions.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s14'>
            <p>84. What does RAT stand for?</p>
            <input type='checkbox' id='c84' class='hidden'>
            <label for='c84' class='answer'>Remote Access Trojan.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s8'>
            <p>85. What does the term Script Kiddies mean?</p>
            <input type='checkbox' id='c85' class='hidden'>
            <label for='c85' class='answer'>Inexperienced attackers that use open-source scripts.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s13'>
            <p>86. What are the 2 servers needed for Kerberos?</p>
            <input type='checkbox' id='c86' class='hidden'>
            <label for='c86' class='answer'>Authentication Server and Ticket Granting Server.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s1'>
            <p>87. What are digital certificates used for?</p>
            <input type='checkbox' id='c87' class='hidden'>
            <label for='c87' class='answer'>Data encryption.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s15'>
            <p>88. What do you do in Weaponisation(2) in the Cyber Kill Chain?</p>
            <input type='checkbox' id='c88' class='hidden'>
            <label for='c88' class='answer'>Find or develop malicious payloads to attack a network.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s16'>
            <p>89. What do you do in the 8th step of the Cyber Kill Chain?</p>
            <input type='checkbox' id='c89' class='hidden'>
            <label for='c89' class='answer'>There's only 7 steps!</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s17'>
            <p>90. What do you do in Exploitation(4) in the Cyber Kill Chain?</p>
            <input type='checkbox' id='c90' class='hidden'>
            <label for='c90' class='answer'>Exploit vulnerabilities to bypass security measures.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s19'>
            <p>91. What is a logic bomb?</p>
            <input type='checkbox' id='c91' class='hidden'>
            <label for='c91' class='answer'>A malicious payload that hides and waits for a date or event before activating.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s20'>
            <p>92. Can you use hashes to encrypt files?</p>
            <input type='checkbox' id='c92' class='hidden'>
            <label for='c92' class='answer'>No, hashing is irreversible.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s21'>
            <p>93. What's the difference between encoding and encrypting?</p>
            <input type='checkbox' id='c93' class='hidden'>
            <label for='c93' class='answer'>Encrypting needs public and private keys to secure data. Encoding like gzip can be easily decoded by anyone.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s22'>
            <p>94. What is more secure, MD5 or SHA-256?</p>
            <input type='checkbox' id='c94' class='hidden'>
            <label for='c94' class='answer'>SHA-256 is a stronger and newer algorithm.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s23'>
            <p>95. What encoding algorithm would have leading "==" as padding?</p>
            <input type='checkbox' id='c95' class='hidden'>
            <label for='c95' class='answer'>Base64.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s24'>
            <p>96. Why is ROT-26 not a valid encoding algorithm?</p>
            <input type='checkbox' id='c96' class='hidden'>
            <label for='c96' class='answer'>It applies ROT-13 twice. This is a joke.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s25'>
            <p>97. Are private and public keys involved in symmetric encryption?</p>
            <input type='checkbox' id='c97' class='hidden'>
            <label for='c97' class='answer'>No, those are for asymmetric.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s26'>
            <p>98. Is Kerberos symmetric or asymmetric encryption?</p>
            <input type='checkbox' id='c98' class='hidden'>
            <label for='c98' class='answer'>Symmetric encryption.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s27'>
            <p>99. What is SFTP?</p>
            <input type='checkbox' id='c99' class='hidden'>
            <label for='c99' class='answer'>A protocol that combines SSH and FTP for secure file transfers.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s28'>
            <p>100. Why would a sender share the public key and not the private key?</p>
            <input type='checkbox' id='c100' class='hidden'>
            <label for='c100' class='answer'>The public key is used to encrypt the reply. The private key then decrpypts the encrypted response.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s29'>
            <p>101. Which tcpdump option lets you 'carve' pcaps?</p>
            <input type='checkbox' id='c101' class='hidden'>
            <label for='c101' class='answer'>-w</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s30'>
            <p>102. How do you filter for https traffic in tcpdump?</p>
            <input type='checkbox' id='c102' class='hidden'>
            <label for='c102' class='answer'>port 443</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s25'>
            <p>103. Which tcpdump option switches timestamps to UTC time?</p>
            <input type='checkbox' id='c103' class='hidden'>
            <label for='c103' class='answer'>-tttt</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s24'>
            <p>104. In tcpdump, why would do <code>-w</code> instead of <code>> foo.pcap</code> ?</p>
            <input type='checkbox' id='c104' class='hidden'>
            <label for='c104' class='answer'>> foo.pcap will just make a new text file and so will not be a readable pcap.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s31'>
            <p>105. Does <code>tcpdump -nn</code> slow down command execution?</p>
            <input type='checkbox' id='c105' class='hidden'>
            <label for='c105' class='answer'>No, -nn disables hostname and port resolution so it actually makes the command go faster.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s32'>
            <p>106. In tcpdump, how do you extract hostnames from DHCP?</p>
            <input type='checkbox' id='c106' class='hidden'>
            <label for='c106' class='answer'>tcpdump -r foo.pcap -v port 67 or port 68 | grep Hostname</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s33'>
            <p>107. In tcpdump, what does the tcpflag [S.] mean?</p>
            <input type='checkbox' id='c107' class='hidden'>
            <label for='c107' class='answer'>SYN-ACK.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s34'>
            <p>108. In tcpdump, how do you filter 192.168.0.1's FTP traffic?</p>
            <input type='checkbox' id='c108' class='hidden'>
            <label for='c108' class='answer'>ip host 192.168.0.1 and port 20 and port 21</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s35'>
            <p>109. How do you pipe tcpdump -r output to awk?</p>
            <input type='checkbox' id='c109' class='hidden'>
            <label for='c109' class='answer'>tcpdump -r foo.pcap | awk '$0'</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s37'>
            <p>110. How do you print the 13th field using awk?</p>
            <input type='checkbox' id='c110' class='hidden'>
            <label for='c110' class='answer'>awk '{print $13}'</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s36'>
            <p>111. How can you print the last field using awk?</p>
            <input type='checkbox' id='c111' class='hidden'>
            <label for='c111' class='answer'>awk '{print $NF}'</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s37'>
            <p>112. In awk, how do you filter for the ip 172.16.0.1 and then print the 5th field?</p>
            <input type='checkbox' id='c112' class='hidden'>
            <label for='c112' class='answer'>awk '/172.16.0.1/{print $5}'</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s38'>
            <p>113. Given a list of filenames, how would you use regex to only filter for html files?</p>
            <input type='checkbox' id='c113' class='hidden'>
            <label for='c113' class='answer'>.html$</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s39'>
            <p>114. How would you use awk to filter for lines that have greater than 15 characters?</p>
            <input type='checkbox' id='c114' class='hidden'>
            <label for='c114' class='answer'>awk 'length{$0}>15'</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s40'>
            <p>115. How would you use awk to print the character length of the 2nd field in each line?</p>
            <input type='checkbox' id='c115' class='hidden'>
            <label for='c115' class='answer'>awk '{print length($2)}'</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s32'>
            <p>116. Where does usually Linux keep a file that lists the port mappings for every service?</p>
            <input type='checkbox' id='c116' class='hidden'>
            <label for='c116' class='answer'>/etc/services</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s38'>
            <p>117. How would you use Linux's /etc/services to find the port numbers of all SQL services?</p>
            <input type='checkbox' id='c117' class='hidden'>
            <label for='c117' class='answer'>cat /etc/services | grep sql -i</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s35'>
            <p>118. How would use Linux's /etc/services to the find the service with the default port of 4094?</p>
            <input type='checkbox' id='c118' class='hidden'>
            <label for='c118' class='answer'>cat /etc/services | grep 4094</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s36'>
            <p>119. As a tshark filter, how would you find probable domain names in kerberos traffic?</p>
            <input type='checkbox' id='c119' class='hidden'>
            <label for='c119' class='answer'>kerberos.realm</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s37'>
            <p>120. Describe this awk statement: awk '$3 !~ /172.16.0.*/'</p>
            <input type='checkbox' id='c120' class='hidden'>
            <label for='c120' class='answer'>If the 3rd field contains the regex expression 172.16.0.* then print the entire line.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s38'>
            <p>121. Describe what this command does: <code>zeek -r foo.pcap local</code></p>
            <input type='checkbox' id='c121' class='hidden'>
            <label for='c121' class='answer'>This is a zeek command that runs all local zeek scripts on the pcap.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s39'>
            <p>122. Can you find a device's hostname in DHCP traffic?</p>
            <input type='checkbox' id='c122' class='hidden'>
            <label for='c122' class='answer'>Yes, the tshark filter is dhcp.option.hostname</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s40'>
            <p>123. What is the tshark filter for Netbios Name Service packets?</p>
            <input type='checkbox' id='c123' class='hidden'>
            <label for='c123' class='answer'>nbns</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s24'>
            <p>124. Describe this command: <code>tshark -r foo.pcap -Y 'nbns.flags.response==True' -T fields -e nbns.name</p>
            <input type='checkbox' id='c124' class='hidden'>
            <label for='c124' class='answer'>It's a tshark command that filters for NetBios responses and prints the hostnames of those responses.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s25'>
            <p>125. Name some protocols in pcap analysis that you can investigate to find a device's hostname.</p>
            <input type='checkbox' id='c125' class='hidden'>
            <label for='c125' class='answer'>Kerberos, NetBios, LDAP, DHCP, DNS, and more!</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s27'>
            <p>126. Describe this wireshark filter <code>ip contains "google.com"</code></p>
            <input type='checkbox' id='c126' class='hidden'>
            <label for='c126' class='answer'>Filter for packets with the string google.com</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s29'>
            <p>127. Describe this wireshark filter <code>http,request.method matches "^(get|post)"</code></p>
            <input type='checkbox' id='c127' class='hidden'>
            <label for='c127' class='answer'>matches indicates a regex expression. The regex itself filters for http request methods that starts with either GET or POST.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s31'>
            <p>128. Describe this wireshark filter <code>http.request.method matches "[^(get)]"</code></p>
            <input type='checkbox' id='c128' class='hidden'>
            <label for='c128' class='answer'>matches indicates a regex expression. This regex filters for http request methods that are NOT get requests.</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s33'>
            <p>129. </p>
            <input type='checkbox' id='c129' class='hidden'>
            <label for='c129' class='answer'></label>
        </div>
    </div>
  </div>
</div>

<script>
  function getRandomInt(max) {
    return Math.floor(Math.random() * max);
  }
  const cardsWrapper = document.querySelector('#cards-wrapper');
  const cards = document.querySelectorAll('.card');
  let arrIndex = [];
  let target = 0;
  while (arrIndex.length < cards.length) {
      const random = getRandomInt(cards.length)
      if (arrIndex.includes(random)) {
        continue;
      }
      else {
        arrIndex.push(random);
      }
    }

  function updateCard(index) {
    cardsWrapper.style.transform = `translateX(${index * -100}%)`;
  }

  function prevCard() {
    target--;
    if (target <= -1) { 
      target = arrIndex.length - 1;
    }
    updateCard(arrIndex[target]);
  }

  function nextCard() {
    target++;
    if (target >= arrIndex.length) { 
      target = 0;
    }
    updateCard(arrIndex[target]);
  }

  document.querySelector('.prev').addEventListener('click', () => {
    prevCard();
  })

  document.querySelector('.next').addEventListener('click', () => {
    nextCard();
  })

  document.addEventListener('DOMContentLoaded', () => {
    updateCard(arrIndex[target]);
  });

  document.addEventListener('keydown', (e) => {
    if (e.code == 'ArrowLeft') {
        prevCard();
    }
    else if (e.code =='ArrowRight') {
        nextCard();
    }
  })
</script>
<br>
<p style='text-align: right;font-size: 0.6em;font-style: italic;'>Note: you can use arrow keys!</p>