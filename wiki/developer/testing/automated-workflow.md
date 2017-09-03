<p>Automation of FileSender client side workflow tests is in progress using <a href="http://seleniumhq.org/">Selenium</a>. This is occurring in two overlapping phases listed below. See <a href="https://www.assembla.com/spaces/file_sender/milestones/1051963-automated-client-side-testing">Automated Client Side Testing milestone</a> for related ticket progress and <a class="wiki_link" href="/wiki/show/file_sender/Test_Workflows" title="Test Workflows">Test Workflows</a> for links to test descriptions for each release.</p>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="706861736520313a2073656c656e69756d2d696465">Phase 1: Selenium-IDE</h2>

<p>&nbsp;</p>

<p>&nbsp;</p>

<h4 id="717569636b20677569646520746f207573696e672073656c656e69756d2d69646520746573742073756974657320666f722066696c6573656e6465722072656c65617365733c62723e">Quick Guide to Using Selenium-IDE test suites for FileSender releases</h4>

<p>Prior to running <a href="http://www.assembla.com/code/file_sender/subversion/nodes/workflowtests/selenium_testsuites">test suites</a>, copy <a href="http://www.assembla.com/code/file_sender/subversion/nodes/workflowtests/selenium_testsuites/vars/vars_custom.html">workflowtests/selenium_testsuites/vars/vars_custom.html</a> as workflowtests/selenium_testsuites/vars/vars_local.html and populate with variables according to your test environment. Then using the latest version of Firefox (<span class="il">Selenium</span> IDE is a Firefox plugin only):</p>

<ol>
	<li>Go to <a href="http://seleniumhq.org/download/" target="_blank">http://seleniumhq.org/download/</a> and download and install the latest <span class="il">Selenium</span> IDE browser plugin. You should then be able to see the plugin listed in Tools &gt; Add-ons &gt; Extensions.</li>
	<li>Open <span class="il">Selenium</span> IDE from Tools &gt; <span class="il">Selenium</span> IDE.</li>
	<li>In the top left-hand corner, slide the bar across from &quot;Fast&quot; to &quot;Slow&quot;, to reduce the rate at which the test will run, so that you can watch each step as it is executed</li>
	<li>In the top right-hand corner, click on the red circle icon to stop recording, which is on by default.</li>
	<li>In Options &gt; Options &gt; General tab, uncheck &quot;Start recording immediately on open&quot; and under &quot;Default timeout value of recorded command in milliseconds [...]&quot; change the value to 60000.</li>
	<li>Open a new browser tab (for Adding recipients, logon to the FileSender test installation first)</li>
	<li>In <span class="il">Selenium</span> IDE, select a test suite from File &gt; Open.</li>
	<li>Click on the &quot;Play entire test suite&quot; button (first play button).</li>
	<li>Enjoy the show! Selenium-IDE highlights steps in green as they pass or red if they fail. Failure of a major step will stop the script. Any errors should appear in red in the pane at the bottom of the Selenium-IDE window. (If the script fails immediately, try clicking on the browser tab in Firefox then try again).</li>
</ol>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="706861736520323a2073656c656e69756d20736572766572">Phase 2: Selenium Server</h2>

<p>Convert and expand Selenium-IDE test scripts for automated running on a server.</p>

<p>&nbsp;</p>

<p>&nbsp;</p>

