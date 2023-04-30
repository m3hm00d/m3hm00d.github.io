---
layout: post
title:  "Configuring iptables to work with GeoIP"
date:   2023-04-30
categories: linux
---

Install required packages on Debian:

{% highlight shell %}
apt install xtables-addons-dkms
apt install libtext-csv-xs-perl libmoosex-types-netaddr-ip-perl pkg-config
{% endhighlight %}

Download `GeoLite2-Country-CSV_YYYYMMDD.zip` from Maxmind.com. You'd need a free account for that.

Then compile the CSV files into a format `xt_geoip` can understand using:

{% highlight shell %}
mkdir -p /usr/share/xt_geoip/
cd /usr/share/xt_geoip

wget "Download Link from Maxmind"
unzip GeoLite2-Country-CSV_20220125.zip
cd GeoLite2-Country-CSV_20220125

/usr/libexec/xtables-addons/xt_geoip_build_maxmind -D /usr/share/xt_geoip *.csv
{% endhighlight %}

Load the `xt_geoip` module using `modprobe xt_geoip`.

iptables should now be able to understand geoip syntax. For example, we can block all traffic from Germany using:

{% highlight shell %}
iptables -A INPUT -m geoip --src-cc DE -j DROP
{% endhighlight %}
