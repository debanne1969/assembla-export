
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      <p><span style="font-size: 100%;">This page outlines the upgrade notes for the FileSender </span><b style="font-size: 100%;">1.6 release</b></p><h2>Upgrading to FileSender 1.6</h2><p>These
 upgrade notes document upgrading from version 
1.5 to version 1.6.  If you are currently running an older version please consult the <a href="https://www.assembla.com/spaces/file_sender/wiki/Upgrade_notes_to_1-5">Upgrade notes for the 1.5 release</a></p><h2>What changed?</h2><ul><li><b>New: high-speed upload module 'TeraSender' (#891)</b></li><li><b>New: auto-complete in the To: field (#821) </b></li><li><b>New: refactored MyFiles, file downloaded dates provide audit trail when download Cc:s switched off<br></b></li><li>New: support for configurable footer via language file (#871)</li><li>New: support for optional Subject and Message in guest use voucher (#637, #774)  <br></li><li>New: support for multiple From: addresses from authentication source (#184)</li><li><span style="background-color: rgb(255, 255, 255);">New: configurable option '<i>download_confirmation_to_downloader</i>' for sending download email receipt to file recipients  (</span><span style="background-color: rgb(255, 0, 0);"><font color="#ffffff">default '<i>true</i>'</font></span><span style="background-color: rgb(255, 255, 255);">) (#985)</span></li><li>New: download pause/resume now possible with browsers supporting partial download (most notably Firefox, IE11, curl and wget) (#1076)<br></li><li>New: support for SQLite (#898) </li><li>New language: Finnish (#981) </li><li>Change: logout.php is now called in the same way as all other pages, practical for header/footer.  <font color="#ffffff"><span style="background-color: rgb(255, 0, 0);"><b>Change your site_logouturl!</b></span> </font>(#904)<br></li><li><b>Change: Upgrade JQuery and JQueryUI to 1.10.2, Upgrade Smoothness to 1.10.2. (#819)</b></li><li>Fix: non-HTML5 uploads with a single quote in filename fail (#895)</li><li>Fix: saml_uid_attribute used in fileuid field (breaks with large uid_attribute values) (#884) </li><li>Fix<b>: </b>prevent logfile pollution by detecting bad requests before switching to https (#970)<br></li></ul><h2>The upgrade process summarized</h2><p>You can use the <b>same database</b> and <b>file store you used</b> for the previous 
FileSender version.  The 1.6 release requires no database changes.  Nevertheless a database backup is a good measure before doing an upgrade.</p><p><br></p><p>What you'll need to do to upgrade is:<br></p><ol><li>backup your database</li><li>backup your filesender installation, especially if you've made local modifications to pages or code</li><li>install the 1.6 code from packages or by unpacking the tarball<br></li><li>create a fresh configuration file with sane defaults from the config/config-dist.php template<br></li><li>make local modifications, pay special attention to changed config file directive semantics, and the help and about <br></li></ol><h2>Upgrade your database definitions</h2>No database changes from 1.5 to 1.6<br><h2>Avoid surprises and start with a fresh configuration file<br></h2><p>New
 configuration directives have been added, others depcrecated and at 
least one changed semantics.  Avoid surprises and start with a fresh 
configuration file.  <b>Copy config/config-dist.php to config/config.php.  This will ensure you start with sane defaults.<br></b></p><h2>Configuration file changes you need to be aware of</h2><p> </p><p>Check the <a href="https://www.assembla.com/spaces/file_sender/wiki/Administrator_reference_manual">Administrator Reference Guide</a> for details about the individual directives.<br></p><h4>New: <br></h4><pre style="max-width: 897px;"><span><span>    // autocomplete in To: field<br>    $config["autocomplete"] = true; (if not present, autocomplete is switched off)<br><span>    </span>$config["autocompleteHistoryMax"] = ""; // "" - unlimited or integer, number of results displayed to user in autocomplete list<br></span></span><span><span></span> <br></span><span><span>    </span>// new high speed upload module 'terasender'<br><span>    </span>$config['terasender'] = false; // true/false - terasender upload module on/off</span><br><span>    </span>$config['terasenderadvanced'] = false; // true/false - terasender advanced - show advanced settings
    $config['terasender_chunksize'] = 5;        // default (5) terasender chunk size in Mb
    $config['terasender_workerCount'] = 6;        // default (6) webworker count
    $config['terasender_jobsPerWorker'] = 1;    // default (1) jobs per worker

    $config["cron_cleanuptempdays"] = 7; // Use cron job to cleanup temp folder for terasender chunks configured number of days

    // configurable default subject for voucher email
    $config['voucherissuedemailsubject'] = 'Voucher';

    // send copy of download confirmation to downloader (true/false, default true)
    $config['download_confirmation_to_downloader'] = true ; (<span style="background-color: rgb(255, 0, 0);"><font color="#ffffff">you probably want to change this to false, we defaulted it to true to ensure your site doesn't change behaviour all of a sudden</font></span>)

</pre><h4> </h4><h4>Changed:</h4><pre style="max-width: 897px;">$config['site_logouturl'] changed, the logout page is now generated in the same way as all other pages.  <font style="background-color: rgb(243, 243, 243);" color="#ff0000"><br><br></font><font style="background-color: rgb(255, 0, 0);" color="#ffffff"><b>If you don't apply this change your logout page will be broken</b></font><span style="background-color: rgb(243, 243, 243); color: rgb(255, 0, 0);"> </span><br><br>old: $config['site_logouturl'] = $config['site_url'] . '<span class="code-deleted">logout.php</span>';<br><b>new: $config['site_logouturl'] = $config['site_url'] . '<span class="code-added">?s=logout</span>';<br><br></b>$config['voucherissuedemailbody'] email template has been changed to incorporate an optional personal message<span></span><br></pre><br><h4>Moved from config.php to language files: </h4><pre style="max-width: 897px;"><span>none</span><span></span><span></span></pre><h4> </h4><h4>New labels in language files:<br></h4><pre style="max-width: 897px;"><span> // Footer to display<br> $lang["_SITE_FOOTER"] = "";<br> Example: $lang['_SITE_FOOTER']='Version '.FileSender_Version::VERSION;<br><br> // New items for My Files<br> $lang["_DOWNLOADED"] = "Downloaded";<br> $lang["_SHOW_ALL"] = "Show/Hide Details";<br> $lang["_DETAILS"] = "Details";<br> <br> // Terasender Advanced Settings<br> $lang["_TERA_ADVANCED_SETTINGS"] = "Advanced Settings";<br> $lang["_TERA_CHUNKSIZE"] = "Chunksize (MB)";<br> $lang["_TERA_WORKER_COUNT"] = "Worker count";<br> $lang["_TERA_JOBS_PER_WORKER"] = "Jobs per workers";<br> <span>    <br></span></span></pre><br><h4>Deprecated:</h4><pre style="max-width: 897px;">none</pre><h4> </h4><h4>Obsoleted:</h4><pre style="max-width: 897px;">$config['site_downloadurl'] has not been used since beta 0.1.15 but was wrongly labeled as deprecated.  Now removed from config file</pre><br>
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
