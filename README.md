# dapnet_mowas_bbk

This project was created to transmit messages from the Federal Office for Civil Protection and Disaster Assistance to a local group of radio amateurs via pager and digital radio.

An RSS feed can be accessed via the BBK-Bund website. The feed applies to each district and can be configured via the following link: https://warnung.bund.de/meldungen 

The script can be executed every 5 minutes using a cron job, for example. Several districts are currently being “monitored” over several scripts, time-delayed.

The scripts are to be stored in folders per county. A dapnet_rss.latest file will be created. The processed reports are saved here so that no duplicate reports are sent.

The script is from do6uk, https://github.com/do6uk/dapnet_news

In this version, messages are sent to RICs or their names in plain text, unlike the version above, which works with rubrics.


## requirements

* Python3
* pip3 install feedparser (used by dapnet_rss.py)


## get them running

* put in your dapnet-credentials under **## CONFIG**
* create an rss-feed at https://warnung.bund.de/meldungen 
* define a receiver as given at dapnet-core
* define a owner-callsign
* set *msg_offset* to decide after which *Number* at the rubric we start to send the news
* set *msg_max* to decide how many messages we will send


## cli-arguments

**--local *or* -l**  don't send news to dapnet (for testing)

**--verbose *or* -v**  we will see what happens

**--silent *or* -s**  we won't see anything

**--force *or* -f**  force an upload even if no new data is present

**--json *or* -j**  save uploaded data as .json (for checking what has been uploaded)
