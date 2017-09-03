<p>To monitor the use of your FileSender installation, other than by examining the various logs in the Administrator view of the Filesender user interface, you can install additional software to gather various kinds of statistics.</p>

<h2 id="webserver_log_analysers">Webserver log analysers</h2>

<p>Log analysers like <a href="http://awstats.sourceforge.net/" target="_blank">AWStats</a> and <a href="http://www.mrunix.net/webalizer/" target="_blank">Webalizer</a> can give you a good general overview of the use of your FileSender webserver, with reports about unique visitors (IP based), type of clients, where they came from and more. Note that these analysers don&#39;t give you exact details about the number of files, uploads, downloads and vouchers over time.</p>

<p>To monitor the more specific FileSender resources, SCRE and AARNet are collecting usage statistics with the <a href="http://www.zabbix.com/" target="_blank">Zabbix</a> and <a href="http://oss.oetiker.ch/mrtg/" target="_blank">MRTG</a> monitoring tools. The following notes and files can get you started.</p>

<h2 id="zabbix">Zabbix</h2>

<p><a href="/spaces/file_sender/documents/cOqOB8lhqr4lhfeJe5cbCb/download?filename=filesender_zabbix.pl">filesender_zabbix.pl</a> - A Zabbix sensor as contributed by Emir Imamagic (SCRE)</p>

<p>Note from Emir:</p>

<pre>
I attached a sensor for Zabbix that we use to get statistics at Srce.

Gathered parameters are:
&quot;filesender.users_total&quot;
&quot;filesender.users_active&quot;
&quot;filesender.files_active&quot;
&quot;filesender.files_total&quot;
&quot;filesender.vouchers_active&quot;
&quot;filesender.vouchers_total&quot;
&quot;filesender.upload_num&quot;
&quot;filesender.upload_size&quot;
&quot;filesender.download_num&quot;
&quot;filesender.download_size&quot;
I think they are pretty self-explanatory, but I can add more text if 
needed :)

By default configuration should be placed in /etc/filesender/config:
HOST=FS_DB_HOST
DB=FS_DB_NAME
USER=FS_DB_USER
PASS=FS_DB_OASS
ZABBIX_HOST=FS_ZABBIX_HOST
ZABBIX_SERVER=CENTAL_ZABBIX_SERVER

Sensor can be executed as Zabbix check or simply from cron. All errors 
are printed to syslog.</pre>

<p>&nbsp;</p>

<h2 id="mrtg">MRTG</h2>

<p><a href="https://bigfiles.assembla.com/spaces/file_sender/documents/download/filesender_grabber.pl">filesender_grabber.pl</a> - A MRTG collector based on the SCRE Zabbix sensor by David Jericho (AARNet).</p>

<p>Note from David:</p>

<pre>
First I use MRTG to collect the stats:

WorkDir: /srv/www/cloudstor.aarnet.edu.au/mrtg/www
Logdir:&nbsp; /srv/www/cloudstor.aarnet.edu.au/mrtg/logs

Options[_]: nopercent,noinfo,growright,noo,gauge
MaxBytes[_]: 10000000000000000000
ShortLegend[_]: &amp;nbsp;
LegendO[_]:
LogFormat: rrdtool

Target[cloudstor.download_size]: `/srv/www/cloudstor.aarnet.edu.au/mrtg/bin/filesender_grabber.pl download_size`
Title[cloudstor.download_size]: Cloudstor Bytes Downloaded
PageTop[cloudstor.download_size]: &lt;h1&gt;Cloudstor Bytes Downloaded&lt;/h1&gt;
YLegend[cloudstor.download_size]: bytes
LegendI[cloudstor.download_size]: &amp;nbsp;Downloaded bytes:

And then finally, I fire off a bunch of rrdtool graphing commands, similar to:

rrdtool graph cloudstor.download_size-year.png -a PNG -A --title=&quot;Total downloaded bytes&quot; \
  --vertical-label &quot;bytes&quot; \
  &#39;DEF:probe1=cloudstor.download_size.rrd:ds0:AVERAGE&#39; \
  &#39;AREA:probe1#00eb0c:bytes&#39; \
  &#39;GPRINT:probe1:LAST:Total downloaded count\: %2.0lf bytes&#39; \
  -s &#39;-1 years&#39;
</pre>

<h2 id="munin">Munin</h2>

<p>Using the SQL from the zabbix-plugin. It uses a limited database-user &quot;filesender_readonly&quot; which has &#39;GRANT SELECT&#39; on everything and nothing else, then it is possible to filter out the lookups on the database (every fve minutes) in the postgresql munin-plugins.</p>

<p>Setup:</p>

<pre>
[filesender*]
user postgres
env.PGPORT 5432
env.PGPASSWORD somepassword
env.PGUSER filesender_readonly
</pre>

<p>This shows numbers of files/vouchers/users that are yet to expire.</p>

<pre>
#!/bin/sh
# -*- sh -*-

if [ &quot;$1&quot; = &quot;autoconf&quot; ]; then
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo yes
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; exit 0
fi

if [ &quot;$1&quot; = &quot;config&quot; ]; then

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;graph_title Filesender active&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;graph_category filesender&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;users_active.label users&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;users_active.type GAUGE&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;files_active.label files&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;files_active.type GAUGE&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;vouchers_active.label vouchers&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;vouchers_active.type GAUGE&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; exit 0
fi

PSQL=&#39;psql -h localhost -U filesender_readonly -At -d filesender -c &#39;

echo &#39;users_active.value&#39; `$PSQL &quot;select count(distinct fileauthuseruid) from files where filestatus = &#39;Available&#39;;&quot;`
echo &#39;files_active.value&#39; `$PSQL &quot;select count(distinct fileuid) from files where filestatus = &#39;Available&#39;;&quot;`
echo &#39;vouchers_active.value&#39; `$PSQL &quot;select count(*) from files where filestatus = &#39;Voucher&#39;;&quot;`
</pre>

<p>This shows totals. Always growing, therefore split into its own plugin.</p>

<pre>
#!/bin/sh
# -*- sh -*-

if [ &quot;$1&quot; = &quot;autoconf&quot; ]; then
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo yes
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; exit 0
fi

if [ &quot;$1&quot; = &quot;config&quot; ]; then

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;graph_title Filesender totals&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;graph_args -l 0 --base 1000&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;graph_category filesender&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;users_total.label users&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;users_total.type GAUGE&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;files_total.label files&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;files_total.type GAUGE&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;vouchers_total.label vouchers&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;vouchers_total.type GAUGE&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;upload_num.label uploads&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;upload_num.type GAUGE&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;download_num.label downloads&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;download_num.type GAUGE&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; exit 0
fi

PSQL=&#39;psql -At -d filesender -U filesender_readonly -h localhost -c &#39;

echo &#39;users_total.value&#39; `$PSQL &quot;select count(distinct fileauthuseruid) from files;&quot;`
echo &#39;files_total.value&#39; `$PSQL &quot;select count(distinct fileuid) from files where filestatus = &#39;Available&#39; or (filestatus = &#39;Closed&#39; and fileexpirydate &lt;&gt; &#39;1970-01-01 01:00:00&#39;);&quot;`
echo &#39;vouchers_total.value&#39; `$PSQL &quot;select count(distinct fileuid) from files where filestatus LIKE &#39;Voucher%&#39; or (filestatus=&#39;Closed&#39; and fileexpirydate = &#39;1970-01-01 01:00:00&#39;);&quot;`
echo &#39;upload_num.value&#39; `$PSQL &quot;select count(*) from logs where logtype=&#39;Uploaded&#39;;&quot;`
echo &#39;download_num.value&#39; `$PSQL &quot;select count(*) from logs where logtype=&#39;Download&#39;;&quot;`

</pre>

<p>This last one shows uploads and downloads.</p>

<pre>
#!/bin/sh
# -*- sh -*-

if [ &quot;$1&quot; = &quot;autoconf&quot; ]; then
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo yes
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; exit 0
fi

if [ &quot;$1&quot; = &quot;config&quot; ]; then

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;graph_title Filesender total up/downloads&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;graph_args -l 0 --base 1000&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;graph_category filesender&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;download_size.type GAUGE&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;download_size.graph no&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;upload_size.label bytes&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;upload_size.type GAUGE&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; echo &#39;upload_size.negative download_size&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; exit 0
fi

PSQL=&#39;psql -At -d filesender -U filesender_readonly -h localhost -c &#39;

echo &#39;upload_size.value&#39; `$PSQL &quot;select coalesce(sum(logfilesize),0) from logs where logtype=&#39;Uploaded&#39;;&quot;`
echo &#39;download_size.value&#39; `$PSQL &quot;select coalesce(sum(logfilesize),0) from logs where logtype=&#39;Download&#39;;&quot;`
</pre>

<h2 id="sql-trick_for_getting_statistics_per_domain">SQL-trick for getting statistics per domain</h2>

<p>Make a view just for log-crunching:</p>

<pre>
CREATE VIEW aggregated_logs AS
  SELECT 
    logs.logid, 
    logs.logtype, 
    split_part(lower(logs.logfrom::text), &#39;@&#39;::text, 1) AS logfrom_user, 
    split_part(lower(logs.logfrom::text), &#39;@&#39;::text, 2) AS logfrom_domain, 
    logs.logdate, 
    logs.logauthuseruid, 
    logs.logfilesize
  FROM logs;
</pre>

<p>You now have the domain in &quot;logfrom_domain&quot; and can GROUP BY it. Preferrably each unique &quot;logfrom_user&quot; should be replaced with a token so as to anonymize the data, this has not been done here. &quot;logauthuserid&quot; is used to check for vouchered users.</p>

