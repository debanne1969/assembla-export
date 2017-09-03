<p>The tests below were conducted from a VM client (win7) located in Utrecht against a VM server (debian lenny) located in Amsterdam. The network path was at least 1 Gbps (with 2-10Gbps path segments in between), 5 hops and a latency of approx. 3-5 ms (both IPv6 and IPv4).</p>

<h1 id="case_1_-_upload_performance_test_using_gears">Case 1 - Upload performance test using Gears</h1>

<h1 id="636f6e6475637465642062793a">Conducted by:</h1>

<p><a href="https://www.assembla.com/profile/xjansen">Xander Jansen</a></p>

<p>Since the upload speed is rather poor some tests were conducted to check the influence of debug logging and the gears upload chunk size. The tests were done with a 1 GByte file with random data against svn revision 205. The source file was located on and uploaded from local storage.</p>

<ul>
	<li><strong>Size in bytes:</strong> 1073527438 1GByte-random.dat</li>
	<li><strong>MD5: </strong>2280f7891ef488f937efc502dd394582 1GByte-random.dat</li>
</ul>

<p>The table contains upload times (mm:ss) computed from the timestamp of the apache log of the first chunk (start) and the timestamp (Date: field) of the mail sent when the upload was done (stop).</p>

<table border="0">
	<tbody>
		<tr>
			<td><strong>Browser</strong></td>
			<td><strong>Version</strong></td>
			<td><strong>OS</strong></td>
			<td><strong>Debug</strong></td>
			<td><strong>SSL</strong></td>
			<td><strong>200KB</strong></td>
			<td>&nbsp;</td>
			<td><strong>1MB</strong></td>
			<td>&nbsp;</td>
			<td><strong>10MB</strong></td>
			<td>&nbsp;</td>
			<td><strong>25MB</strong></td>
			<td>&nbsp;</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td><em>mm:ss</em></td>
			<td><em>Mbps</em></td>
			<td><em>mm:ss</em></td>
			<td><em>Mbps</em></td>
			<td><em>mm:ss</em></td>
			<td><em>Mbps</em></td>
			<td><em>mm:ss</em></td>
			<td><em>Mbps</em></td>
		</tr>
		<tr>
			<td><strong>IE8</strong></td>
			<td>8.0.7600.16385</td>
			<td>Win7</td>
			<td>true</td>
			<td>+</td>
			<td>20:08</td>
			<td>6.8</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>4:22</td>
			<td>31.3</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>20:55</td>
			<td>6.5</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>false</td>
			<td>+</td>
			<td>11:37</td>
			<td>11.7</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>4:25</td>
			<td>30.1</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
		</tr>
		<tr>
			<td><strong>Chrome</strong></td>
			<td>6.0.472.55</td>
			<td>Win7</td>
			<td>true</td>
			<td>+</td>
			<td>21:21</td>
			<td>6.4</td>
			<td>11:55</td>
			<td>11.5</td>
			<td>9:20</td>
			<td>14.6</td>
			<td>9:21</td>
			<td>14.6</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>false</td>
			<td>+</td>
			<td>15:01</td>
			<td>9.1</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>9:39</td>
			<td>14.1</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
		</tr>
		<tr>
			<td><strong>Firefox</strong></td>
			<td>3.6.8</td>
			<td>Win7</td>
			<td>true</td>
			<td>+</td>
			<td>18:29</td>
			<td>7.4</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>false</td>
			<td>&nbsp;</td>
			<td>9:25</td>
			<td>14.5</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>5:01</td>
			<td>27.2</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
		</tr>
	</tbody>
</table>

<p>As expected both the debug setting and the chunksize have a large impact on the upload speed. The effect of setting debug to true is largest with a small chunksize and isn&#39;t noticable anymore with the larger chunksizes (10MB+).</p>

<h1 id="case_2_-_upload_performance_test_using_flash">Case 2 - Upload performance test using Flash</h1>

<p>The tests were done with a 1 GByte file with random data against svn revision 205. The source file was located on and uploaded from local storage.</p>

<ul>
	<li><strong>Size in bytes:</strong> 1073527438 1GByte-random.dat</li>
	<li><strong>MD5: </strong>2280f7891ef488f937efc502dd394582 1GByte-random.dat</li>
</ul>

<p>The table contains upload times (mm:ss) computed from the timestamp of the call to fs_uploadit.php in the apache log (start) and the timestamp of the first fs_main.php call in the apache log after that (stop).</p>

<table border="0">
	<tbody>
		<tr>
			<td><strong>Browser</strong></td>
			<td><strong>Version</strong></td>
			<td><strong>OS</strong></td>
			<td><strong>Debug</strong></td>
			<td><strong>SSL</strong></td>
			<td><strong>Time (mm:ss)</strong></td>
			<td><strong>Speed (Mbps)</strong></td>
		</tr>
		<tr>
			<td><strong>Safari</strong></td>
			<td>5.0.2</td>
			<td>Win7</td>
			<td>true</td>
			<td>-none-</td>
			<td>5:16</td>
			<td>25.9</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>TLSv1 RC4-SHA</td>
			<td>11:31</td>
			<td>11.9</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>TLSv1 AES128-SHA</td>
			<td>11:27</td>
			<td>11.9</td>
		</tr>
		<tr>
			<td><strong>Opera</strong></td>
			<td>10.62</td>
			<td>Win7</td>
			<td>true</td>
			<td>-none-</td>
			<td>5:52</td>
			<td>23.3</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>TLSv1 RC4-SHA</td>
			<td>10:40</td>
			<td>12.8</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>TLSv1 DHE-RSA-AES256-SHA</td>
			<td>10:39</td>
			<td>12.8</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>TLSv1 DHE-RSA-AES256-SHA</td>
			<td>9:45</td>
			<td>14.0</td>
		</tr>
	</tbody>
</table>

<p><strong>Notes</strong></p>

<ul>
	<li>Due to weird problems on the Win7 testbox with Safari and SSL the Apache server was instructed to disable &#39;keepalive&#39; when doing SSL for Safari browsers, this may have some impact (to be tested where possible). Note that this option didn&#39;t solve the Safari problem</li>
</ul>

