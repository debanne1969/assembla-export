
      
      
      
      
      <p>This page contains instructions for installing the statistics module on an already existing FileSender instance.</p>
<h2>New database table</h2>
<p>The module makes use of a new <b>stats</b> database table which holds anonymised log data used for generating charts. Use the following SQL syntax for creating this table.</p>
<h4>PostgreSQL<span style="color: #0000ff;"><b></b></span><br></h4>
<pre><b><span style="color: #0000ff;">CREATE TABLE</span></b> stats<br><span style="color: #000080;"><b>(</b></span><br>  statid <span style="color: #0000ff;"><b>integer NOT NULL DEFAULT nextval</b></span><span style="color: #000080;"><b>(</b></span><span style="color: #808080;">'log_id_seq'</span><b><span style="color: #000080;">::</span></b>regclass<span style="color: #000080;"><b>),</b></span><br>  statfileuid <span style="color: #0000ff;"><b>character varying</b></span><span style="color: #000080;"><b>(</b></span><span style="color: #ff8000;">60</span><span style="color: #000080;"><b>),</b></span><br>  statlogtype <span style="color: #0000ff;"><b>character varying</b></span><span style="color: #000080;"><b>(</b></span><span style="color: #ff8000;">60</span><span style="color: #000080;"><b>),</b></span><br>  statfromdomain <span style="color: #0000ff;"><b>character varying</b></span><span style="color: #000080;"><b>(</b></span><span style="color: #ff8000;">250</span><span style="color: #000080;"><b>),</b></span>
  statfromhashed <span style="color: #0000ff;"><b>character varying</b></span><span style="color: #000080;"><b>(</b></span><span style="color: #ff8000;">64</span><span style="color: #000080;"><b>),</b></span>
  stattodomain text,
  statdate timestamp without time zone,
  statfilesize bigint,
  statsessionid character varying(60),
  statvoucheruid character varying(60),
  statauthuseruid character varying(500),
  CONSTRAINT stats_pkey PRIMARY KEY (statid)
);</pre>
<h4>MySQL</h4><div>Be warned: the statistics module code does not yet support MySQL databases and will not work correctly.</div>
<pre><span style="color: #0000ff;"><b>CREATE TABLE</b></span> `stats` <span style="color: #000080;"><b>(</b></span><br>  `statid` <span style="color: #0000ff;"><b>int</b></span><span style="color: #000080;"><b>(</b></span><span style="color: #ff8000;">11</span><span style="color: #000080;"><b>)</b></span> <b><span style="color: #0000ff;">NOT NULL AUTO_INCREMENT</span>,</b><br>  `statfileuid` <b><span style="color: #0000ff;">varchar</span><span style="color: #000080;">(</span></b><span style="color: #ff8000;">60</span><span style="color: #000080;"><b>)</b></span> <span style="color: #0000ff;"><b>DEFAULT NULL</b></span><span style="color: #000080;"><b>,</b></span><br>  `statlogtype` <span style="color: #0000ff;"><b>varchar</b></span><span style="color: #000080;"><b>(</b></span><span style="color: #ff8000;">60</span><span style="color: #000080;"><b>)</b></span> <span style="color: #0000ff;"><b>DEFAULT NULL</b></span><span style="color: #000080;"><b>,</b></span><br>  `statfromdomain` <span style="color: #0000ff;"><b>varchar</b></span><span style="color: #000080;"><b>(</b></span><span style="color: #ff8000;">250</span><span style="color: #000080;"><b>)</b></span> <span style="color: #0000ff;"><b>DEFAULT NULL</b></span><span style="color: #000080;"><b>,</b></span>
  `statfromhashed` <span style="color: #0000ff;"><b>varchar</b></span><span style="color: #000080;"><b>(</b></span><span style="color: #ff8000;">64</span><span style="color: #0000ff;"><b>) DEFAULT NULL,</b></span>
  `stattodomain` text DEFAULT NULL,
  `statdate` timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  `statfilesize` bigint(20) DEFAULT NULL,
  `statsessionid` varchar(60) DEFAULT NULL,
  `statvoucheruid` varchar(60) DEFAULT NULL,
  `statauthuseruid` varchar(500) DEFAULT NULL,
  PRIMARY KEY (`statid`)
) ENGINE=InnoDB AUTO_INCREMENT=10 DEFAULT CHARSET=utf8;</pre>
<p>Note that you may need to grant access privileges on the new table to your database user.</p>
<h2>Files changes</h2>
<p>The following files and folders are either new or changed.</p>
<ul>
<li>classes/Functions.php <span style="color: rgb(255, 0, 0);">(modified, apply patch)</span><br></li>
<li>config/config.php <span style="color: rgb(255, 0, 0);">(modified, follow installation notes)</span><br></li>
<li>cron/cron_stats.php <span style="color: rgb(255, 0, 0);">(new)</span><br></li>
<li>language/en_AU.php <span style="color: rgb(255, 0, 0);">(modified, apply patch)</span><br></li>
<li>pages/customchart.php <span style="color: rgb(255, 0, 0);">(new)</span><br></li>
<li>pages/stats.php <span style="color: rgb(255, 0, 0);">(new)</span><br></li>
<li>scripts/filesender_db.sql (modified, follow installation notes)<br></li>
<li>scripts/mysql_filesender_db.sql (NOT COMPLETED)<br></li>
<li>www/index.php (modified, apply patch)<br></li>
<li>www/css/default.css (modified, apply patch)<br></li>
<li>www/stats/index.php (new)<br></li>
<li>www/stats/css/jquery.jqplot.min.css (new)<br></li>
<li>www/stats/data/ (<i>this folder needs to exist and be accessible</i>) (new)<br></li>
<li>www/stats/js/excanvas.min.js (new)<br></li>
<li>www/stats/js/jqplot.canvasAxisLabelRenderer.min.js (new)<br></li>
<li>www/stats/js/jqplot.canvasTextRenderer.min.js (new)<br></li>
<li>www/stats/js/jqplot.dateAxisRenderer.min.js (new)<br></li>
<li>www/stats/js/jqplot.highlighter.min.js (new)<br></li>
<li>www/stats/js/jqplot.logAxisRenderer.min.js (new)<br></li>
<li>www/stats/js/jquery.jqplot.min.js (new)<br></li>
</ul>
<h2>Configuring the statistics module</h2>
<p>There are many different configurable parameters for the statistics module. These can be found in config/config.php.</p>
<pre>$config['stats_access_level'] = 'public';<br>$config['stats_access_level_updown'] = 'public';<br>$config['stats_access_level_filesizes'] = 'public';<br>$config['stats_access_level_vouchers'] = 'public';<br>$config['stats_access_level_totalupdown'] = 'public';</pre>
<p>These parameters dictate who is able to access the various statistics pages. The first one is for the statistics module as a whole, the other four are for access to the individual charts. Possible values:</p>
<ul>
<li>'public' - viewable by anyone, no login required. This is the default value.</li>
<li>'user' - accessible to any signed-in user.</li>
<li>'admin' - can only be accessed by signed-in users who have administrator privileges.</li>
<li>'disabled' - not accessible at all.</li>
</ul>
<div>
<pre>$config['excluded_domains'] = array('uninett.no', 'gmail.com');</pre>
The domains listed here are excluded from all of the statistics. This can be useful e.g. for hiding irrelevant test data from the charts. Use commas for separating multiple domains. Note: only "FROM" domains (that is, the uploader / sender) will be excluded.</div>
<pre>$config['stats_available_frequencies'] = array('year', 'month', 'week', 'day');<br>$config['stats_default_frequency'] = 'week';</pre>
<p>The various interval frequencies that are available for each graph, and the interval frequency that is displayed by default when viewing the statistics overview. Accepted values are 'year', 'month', 'week' and 'day'.</p>
<pre>$config['stats_offset_year'] = array('year' => 5, 'mon' => 0, 'mday' => 0);<br>$config['stats_offset_month'] = array('year' => 1, 'mon' => 0, 'mday' => 0);<br>$config['stats_offset_week'] = array('year' => 0, 'mon' => 6, 'mday' => 0);<br>$config['stats_offset_day'] = array('year' => 0, 'mon' => 0, 'mday' => 7);</pre>
<p>These parameters describe the starting point from which each of the interval frequencies will display data. For example, by default a graph with the 'week' frequency setting will display data from 6 months back in time.</p>
<h2>Running cron</h2>
<p>Before the statistics module is operational, it is necessary to run the cron/cron.php script. This script is responsible for retrieving statistics data from the database and preparing it for presentation. Please see the <a href="/spaces/file_sender/wiki/Installation_-_LInux_Source_-_version_1_5#configure_cron">installation notes</a> for instructions on how to set up a periodic cron job if you haven't already done so.</p>
<p>Also note that changes to many of the above configuration parameters will not take effect until the next time the cron/cron.php script is executed. Use the following command from a terminal if you need to run the cron script manually:</p>
<pre>php -q /var/www/filesender/cron/cron.php</pre>
<h2>Accessing the statistics pages</h2>
<p>That's it. You should now be able to view the statistics pages by browsing to https://yourfilesenderinstallation/stats/.</p>
<div></div>
<div></div>
<div></div>
<div></div>
    
    
    
    
    
