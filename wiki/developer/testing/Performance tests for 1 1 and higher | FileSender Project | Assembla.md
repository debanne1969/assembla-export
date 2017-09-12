
      <p><span style="background-color: #ff0000; font-size: xx-large;"> Work in progress</span></p>
<p> </p>
<p>The tests below were conducted from a VM client (win7) located in Utrecht against a VM server (debian lenny) located in Amsterdam. The network path was at least 1 Gbps (with 2-10Gbps path segments in between), 5 hops and a latency of approx. 3-5 ms (both IPv6 and IPv4).</p>
<p>When testing other installs make a note of client location, server location, number of network hops and latency (with traceroute) and whether IPV6 and/or SSL is used.</p>
<p><i>The table contains upload times (mm:ss) computed from the timestamp of the call to fs_uploadit.php in the apache log (start) and the timestamp of the first fs_main.php call in the apache log after that (stop).</i></p>
<table border="0">
<tbody>
<tr>
<td><b>Browser</b></td>
<td><b>Version</b></td>
<td> <b>Tweaks</b></td>
<td><b>OS</b></td>
<td><b>FileSender Version </b></td>
<td><b>Debug</b></td>
<td> <b>HTML5</b></td>
<td><b>SSL Cipher<br></b></td>
<td><b> IPv6?</b></td>
<td><b>Time (mm:ss)<br></b></td>
<td><b>Speed (Mbps)</b></td>
</tr>
<tr>
<td><b>Chrome<br></b></td>
<td> </td>
<td> -</td>
<td>Win7</td>
<td> </td>
<td> </td>
<td> yes</td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr>
<td> </td>
<td> </td>
<td> --use-system-ssl<sup>1</sup></td>
<td> </td>
<td> </td>
<td> </td>
<td> yes</td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
</tr>
</tbody>
</table>
<h2>User reports</h2>
<p> </p>
<table border="0">
<tbody>
<tr>
<td><b>Browser</b></td>
<td><b>Version</b></td>
<td> <b>Tweaks</b></td>
<td><b>OS</b></td>
<td><b>FileSender Version </b></td>
<td><b>Latency (ms)</b></td>
<td><b>Debug</b></td>
<td> <b>HTML5</b></td>
<td><b>SSL Cipher<br></b></td>
<td><b> IPv6?</b></td>
<td><b>Time (mm:ss)<br></b></td>
<td><b>Speed (Mbps)</b></td>
</tr>
<tr>
<td><b>Chrome<br></b></td>
<td> ?</td>
<td> -</td>
<td>Win7</td>
<td> 1.1 AARNet</td>
<td>23</td>
<td> </td>
<td> yes</td>
<td> ?</td>
<td> ?</td>
<td> </td>
<td> app. 4.5</td>
</tr>
<tr>
<td> </td>
<td> ?</td>
<td> --use-system-ssl<sup>1</sup></td>
<td>Win7</td>
<td> 1.1. AARNet</td>
<td>23</td>
<td> </td>
<td> yes</td>
<td> ?</td>
<td> ?</td>
<td> </td>
<td> 60</td>
</tr>
<tr>
<td> <b>FireFox</b></td>
<td> 4.0</td>
<td> </td>
<td>Ubuntu 11 LiveCD</td>
<td> 1.1 AARNet</td>
<td>23</td>
<td> </td>
<td> yes</td>
<td> ?</td>
<td> ?</td>
<td> </td>
<td> 60-80</td>
</tr>
<tr>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
</tr>
</tbody>
</table>
<p><b>Notes</b></p>
<p><sup>1</sup> There appears to be an issue with uploads from Chrome on Win7 using the default NSS libraries. See <a href="http://code.google.com/p/chromium/issues/detail?id=69813#c45">http://code.google.com/p/chromium/issues/detail?id=69813#c45</a></p>
    
