<h2 id="assumptions">Assumptions</h2>

<p>As of version beta 0.1.17 filesender can handle text in character sets other than US-ASCII. The code is based on the following assumptions:</p>

<ul>
	<li>The Flash UI handles text as Unicode and uses UTF-8 as encoding for transmitting text strings containing international characters to the backend</li>
	<li>The PHP backend and database store strings with international characters in UTF-8 encoding</li>
	<li>Browser, Mail client and OS can handle UTF-8 encoded strings where appropriate</li>
</ul>

<p>All handling of strings that might contain international characters should be UTF-8 aware/transparent. At the moment this concerns the &#39;filesubject&#39;, &#39;filemessage&#39; and &#39;fileoriginalname&#39; variables.</p>

<h2 id="database_considerations">Database considerations</h2>

<p>The <em>filesender</em> PostgreSQL database must be in either the SQL_ASCII or UTF8 encoding. Check with <em>psql -l</em></p>

<h2 id="character_set_distinctions">Character set distinctions</h2>

<p>When handling one of the relevant variables (mainly in outgoing mails and when downloading) the following distinction should be made:</p>

<ol>
	<li>string contains only US-ASCII characters (plain text, no special characters)</li>
	<li>string contains (multibyte) UTF-8 encoded characters from the ISO-8859-1 character set only</li>
	<li>string contains (multibyte) UTF-8 encoded characters from other character sets</li>
</ol>

<p>Category 2. (UTF-8 encoded ISO-8859-1) is handled differently on some occasions to either adhere to existing standards or to prevent multibyte encoding where &#39;single byte encoding&#39; can be used. In these cases the multibyte UTF-8 string is converted (iconv) to a single byte encoding in the ISO-8859-1 character set (with, where possible, the appropriate charset-labels).</p>

<p>Strings from category 3. (UTF-8 encoded &#39;other&#39; character sets) are handled and labeled as such, UTF-8.</p>

<h2 id="7468652022636f6e74656e742d646973706f736974696f6e222070726f626c656d">The &quot;Content-Disposition&quot; problem</h2>

<p>At the moment the <strong>labeling</strong> of a string as UTF-8 encoded is not done when a file containing special characters is downloaded. The download process uses the HTTP Content-Disposition header with a filename parameter. This header is only defined for filenames containing characters from the (single byte) ISO-8859-1 character set.</p>

<p>Although there are currently ongoing standardisation efforts to make it possible to use other character sets there is no universally adopted way of transmitting a UTF-8 encoded filename yet (see <a href="http://greenbytes.de/tech/webdav/draft-ietf-httpbis-content-disp-latest.html">http://greenbytes.de/tech/webdav/draft-ietf-httpbis-content-disp-latest.html</a> for details). The current filesender code therefore relies on what is called &#39;encoding sniffing&#39; in browsers such as FireFox, Chrome and Safari. Internet Explorer can only handle ISO-8859-1 (single byte) encoded filenames.</p>

<p>For now this means that when using international characters in filenames <strong>other than ISO-8859-1</strong> the filename will look &#39;funny&#39; when downloaded with Internet Explorer and possibly other browsers other than FireFox, Chrome or Safari. The file is however correctly downloaded and usable.</p>

<h2 id="known_issues">Known issues</h2>

<p>- Sometimes the Flash UI gets confused by certain international characters and will display text (also text with only ASCII characters) in a garbled way. This appears to be related to uploading filenames with characters from the Unicode &#39;Combining Diacritical Marks&#39; set with Gears. This will be commonly seen with files uploaded from a Mac since the Mac HFS+ file system enforces the use of &#39;decomposed Unicode&#39; characters in filenames (see <a href="http://code.google.com/p/macfuse/issues/detail?id=139#c2">http://code.google.com/p/macfuse/issues/detail?id=139#c2</a> for a nice explanation) . This is not affecting the functionality (uploads and dowloads use the correct text and filenames).</p>

<p>- Some of the PHP-code in the back-end might appear to be unneeded (most notably the utf_encode before json_decode parts).</p>

