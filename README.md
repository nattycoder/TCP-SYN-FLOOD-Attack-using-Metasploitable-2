<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>

  <h1>TCP SYN Flood Attack using Hping3 on Metasploitable 2</h1>
  <h3>Work realised by: <b>Alaa Eddine Ayedi - 2GT2</b></h3>

  <h2>⚡️Description⚡️</h2>
  <p>This repository provides a hands-on experience of a TCP SYN flood attack, showcasing the potency of `hping3`. Witness the relentless storm of SYN packets unleashed upon `Metasploitable 2`, accompanied by real-time network traffic visualization using `Wireshark`. This knowledge is potent and should be wielded responsibly by ethical hackers with pure intentions.</p>

  <h2>⚔️Prerequisites⚔️</h2>
  <ul>
    <li><strong>Kali Linux:</strong> Your trusted weapon in the ethical hacking arsenal (You can use Parrot Security OS too).</li>
    <li><strong>Metasploitable 2:</strong> The unsuspecting victim of our digital assault.</li>
    <li><strong>Wireshark:</strong> The all-seeing eye of the network.</li>
    <li>A thirst for knowledge and a passion for understanding the intricate world of network security.</li>
  </ul>

  <h2>Setting the Stage</h2>
  <ol>
    <li><strong>Arm yourself:</strong> Install hping3 on Kali to prepare for the attack (In most cases you will find it pre-installed).
      <pre><code>sudo apt install hping3</code></pre>
    </li>
    <li><strong>Summon the target:</strong> Boot up Metasploitable 2 and watch it tremble in anticipation. Type `ifconfig` in metasploitable shell and open your browser and type the inet IP address that you metasploitable is using. (In my case it was 192.168.1.11)</li>
    <li><strong>Establish communication:</strong> Verify network connectivity between Kali and Metasploitable using the `ping` command.</li>
    <li><strong>Unveil the hidden world:</strong> Open Wireshark and prepare to be mesmerized by the impending digital storm. Make sure to choose the network interface that you're using. (In my case it was eth0)</li>
  </ol>

  <h2>Unleashing the Storm</h2>
  <ol>
    <li><strong>Open a terminal on Kali:</strong> Your command center for the chaos to come.</li>
    <li><strong>Execute the attack:</strong> Unleash a torrent of SYN packets with this command:
      <pre><code>sudo hping3 --count 1500 --data 120 --syn --flood -p 80 --rand-source &lt;target_IP&gt;</code></pre>(for example: 192.168.1.11)
      <p>
        --count is used to specify the number of SYN packets that we're willing to send <br>
        --data is used to specify the packet size <br>
        --syn to set SYN flag, and --flood to sent packets as fast as possible (Don't show replies) <br>
        -p to specify the destination port (in our case it was an HTTP service so it's port 80) <br>
        --rand-source to make sure that we're not using the IP address of our machine and we're staying anonymous
      </p>
    </li>
  </ol>

  <h2>Witnessing the Devastation</h2>
  <ol>
    <li><strong>Observe the carnage:</strong> Watch Wireshark display the mesmerizing flood of SYN packets leaving your Kali machine.</li>
    <li><strong>Feel the tremors:</strong> Witness Metasploitable's defenses crumble under the pressure of the attack.</li>
    <li><strong>Savor the victory:</strong> Observe the disruption on Metasploitable's terminal, a testament to your mastery of the SYN flood technique.</li>
  </ol>

  <h2>️Bringing the Storm to a Close️</h2>
  <ol>
    <li><strong>Stop the attack:</strong> Press <code>Ctrl + C</code> to cease the flow of SYN packets and let Metasploitable recover.</li>
    <li><strong>Analyze the aftermath:</strong> Observe the network traffic in Wireshark and see how the storm subsides.</li>
    <li><strong>Confirm the damage:</strong> Check Metasploitable's terminal to ensure its functionality has been restored.</li>
  </ol>

  <h2>Further Exploration</h2>
  <ul>
    <li><strong>Delve deeper into the abyss:</strong> Explore the hping3 documentation to unlock its full potential.</li>
    <li><strong>Expand your knowledge:</strong> Learn more about the TCP protocol and the inner workings of the SYN flood attack.</li>
    <li><strong>Sharpen your skills:</strong> Practice safely in controlled environments to hone your ethical hacking skills.</li>
  </ul>

  <h2>⚠️Disclaimer⚠️</h2>
  <p>This knowledge is a powerful tool. Use it wisely and ethically to contribute to a more secure cyber world.</p>
  <p>Alaa Eddine Ayedi - 2nd year Telecommunications Engineering student</p>
</body>
</html>
