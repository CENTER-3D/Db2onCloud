---

copyright:
  years: 2014, 2019
lastupdated: "2018-10-22"

keywords: 

subcollection: Db2onCloud

---

<!-- Attribute definitions --> 
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:important: .important}
{:note: .note}
{:deprecated: .deprecated}
{:pre: .pre}

# High availability (HA)
{: #ha}

{{site.data.keyword.Db2_on_Cloud_short}} high availability plans have excellent availability characteristics with a 99.99% SLA. 
{: shortdesc}

The standard high availability plans without a disaster recovery (DR) node provide seamless failover and rolling updates. They are managed for you by using automatic client reroute (ACR) and portable IPs.

In addition, you can add a Geo-Replicated Disaster Recovery Node. This offsite DR node option gives you the ability to rapidly synchronize your data in real time to a database node in an offsite {{site.data.keyword.Bluemix_notm}} data center of your choice. 

[List of data center locations where DR nodes are available. ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://developer.ibm.com/answers/questions/366888/what-locations-cities-or-countries-is-dashdb-avail.html){:new_window}

{{site.data.keyword.Db2_on_Cloud_short}} uses the Db2 High Availability Disaster Recovery (HADR) technology in `ASYNC` mode to achieve the offsite DR node capability and provides `Read on Standby` on the DR node.

## **Brazil: Supplementary Rule 14** (applies to systems provisioned for the Brazilian federal government)
{: #rule_14}

At this time, the disaster recovery (DR) option for Db2 on Cloud offerings is not available in Brazil for the federal government due to Supplementary Rule 14.

## How to add a Geo-Replicated Disaster Recovery Node
{: #add_dr}

For existing {{site.data.keyword.Db2_on_Cloud_short}} users:
 * You can add an on-demand DR node to existing {{site.data.keyword.Db2_on_Cloud_short}} instances. After clicking your instance in the {{site.data.keyword.Bluemix_notm}} dashboard, you will see an option called **Manage Disaster Recovery**. You can add a Geo-Replicated Disaster Recovery Node from there.
 * If you purchased {{site.data.keyword.Db2_on_Cloud_short}} on contract through a sales representative and do not have an {{site.data.keyword.Bluemix_notm}} subscription, contact your IBM representative to add a DR node.

If you are currently not a {{site.data.keyword.Db2_on_Cloud_short}} user:
 * Order {{site.data.keyword.Db2_on_Cloud_short}} through {{site.data.keyword.Bluemix_notm}}, or speak to your sales representative.
 * You can then add a DR node by using **Manage Disaster Recovery** in the console.
<!--- Through the web console, you can also add a disaster recovery (DR) node located in a datacenter of your choice. -->

## Managing high availability and disaster recovery nodes
{: #manage_ha_dr}

For standard HA nodes, which are not offsite, the failover is managed for you by IBM. IBM monitors the health of your server, failover, and failing back as needed, including rolling updates and scaling to keep uptime as high as possible.

For Geo-Replicated Disaster Recovery (HADR), you must manually fail over by using **Manage Disaster Recovery** in the console. In addition, you can fail over by using an API as described [here ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://developer.ibm.com/answers/questions/457901/where-can-i-find-api-documentation-for-db2-on-clou.html){:new_window}.

## FAQ
{: #faq}

### What are the changes required for an application using Db2 to work with the DR node after takeover? Does the DNS name or the IP address change after takeover?

**A**: No. You are given 2 resolvable host names. If your app is configured to use Db2 ACR (Active Connection Reroute), then your app gets rerouted to the new primary node.

For more information about the Geo-Replicated Disaster Recovery Node, click [here ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://developer.ibm.com/answers/questions/458385/frequently-asked-questions-for-db2-on-cloud-hadr-g.html){:new_window}.
