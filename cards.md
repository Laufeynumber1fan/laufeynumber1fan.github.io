---
layout: default
title: Cards
---

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
    transition: color 0.2s, background-color 0.2s;
  }
  
  .cards-btn:hover {
    background-color:rgb(241, 241, 241);
  }

  .card-content {
    display: block;
    margin: 18vh auto 0 auto;
    width: 45%;
    height: 30%;
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
    padding: 0.65em 1.25em;
    border-radius: 5px;
    min-width: 40%;
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
    background-color: rgb(255, 255, 221);
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
            <label for='c1' class='answer'>Transmission Control Protocol</label>
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
            <label for='c3' class='answer'>TCP/UDP port 53</label>
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
        <div class='card-content s4'>
            <p>5. Name the TCP/IP layer that TCP belongs to.</p>
            <input type='checkbox' id='c5' class='hidden'>
            <label for='c5' class='answer'>Transport Layer</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s6'>
            <p>6. Which OSI layer does a router operate in.</p>
            <input type='checkbox' id='c6' class='hidden'>
            <label for='c6' class='answer'>Layer 3/Network Layer</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s1'>
            <p>7. What feature gives switches layer 3 functionality?</p>
            <input type='checkbox' id='c7' class='hidden'>
            <label for='c7' class='answer'>Inter-VLAN routing</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s9'>
            <p>8. What port is DHCP?</p>
            <input type='checkbox' id='c8' class='hidden'>
            <label for='c8' class='answer'>UDP port 67 and 68</label>
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
            <label for='c11' class='answer'>Dynamic Host Configuration Protocol</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s8'>
            <p>12. What does OSI layer 6 do?</p>
            <input type='checkbox' id='c12' class='hidden'>
            <label for='c12' class='answer'>Data encryption and compression</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s1'>
            <p>13. What port is FTP?</p>
            <input type='checkbox' id='c13' class='hidden'>
            <label for='c13' class='answer'>FTP servers use TCP port 21, FTP clients use TCP port 20</label>
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
            <label for='c15' class='answer'>STMP sends email from sender to reciever's mail server<br>POP3 is used by the receiver to fetch mail from the mail server</label>
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
            <label for='c17' class='answer'>User Datagram Protocol</label>
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
            <label for='c19' class='answer'>Layer 2, Data Link Layer</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s5'>
            <p>20. Name the layers of the TCP/IP model</p>
            <input type='checkbox' id='c20' class='hidden'>
            <label for='c20' class='answer'>Network Access, Internet, Transport, Application</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s1'>
            <p>21. What is the shorthand for the subnet mask 255.255.252.0?</p>
            <input type='checkbox' id='c21' class='hidden'>
            <label for='c21' class='answer'>/22</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s3'>
            <p>22. What is the broadcast address for the network 172.25.0.0/24</p>
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
            <label for='c' class='answer'>Class A</label>
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
            <p>27. How many usable (hosts + network + broadcast) IP addresses are in a /30 subnet?</p>
            <input type='checkbox' id='c27' class='hidden'>
            <label for='c27' class='answer'>4</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s7'>
            <p>28. What is the first usable host IP address in the network 251.156.11.64/15</p>
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
            <p>30. What is the broadcast address for the network 192.168.2.0/25</p>
            <input type='checkbox' id='c30' class='hidden'>
            <label for='c30' class='answer'>192.168.2.127</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s7'>
            <p>31. What is valid host range for the network 10.1.0.64/27</p>
            <input type='checkbox' id='c31' class='hidden'>
            <label for='c31' class='answer'>10.1.0.65-10.1.0.94</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s4'>
            <p>32. What is the full subnet mask for /18</p>
            <input type='checkbox' id='c32' class='hidden'>
            <label for='c32' class='answer'>255.255.192.0</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s7'>
            <p>33. What class is the IP address 172.0.0.1?</p>
            <input type='checkbox' id='c33' class='hidden'>
            <label for='c33' class='answer'>Class B</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s8'>
            <p>34. What is the default gateway for the IP address 192.168.12.254/24?</p>
            <input type='checkbox' id='c34' class='hidden'>
            <label for='c34' class='answer'>192.168.12.1</label>
        </div>
    </div>
    <div class='card'>
        <div class='card-content s2'>
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
            <input type='checkbox' id='c' class='hidden'>
            <label for='c' class='answer'>10.0.0.129</label>
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