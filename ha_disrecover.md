---

copyright:
  years: 2018, 2019
lastupdated: "2019-11-30"

keywords: IBM Cloud, API Gateway, API Gateway Lite, API management, HA, high availability, disaster recovery, downtime, down time, failure, catasrophe, region, multizone region, MZR

subcollection: api-gateway

---


{:external: target="_blank" .external} 
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .note}

# High availability and disaster recovery
{: #ha_disrec}

{{site.data.keyword.cloud_notm}} provides high-availability and disaster-recovery solutions to ensure that your APIs remain accessible.
{: shortdesc}

## Deploying highly available APIs
{: #avail_ha_disrec}

Every API managed by {{site.data.keyword.apigw_full}} is deployed across at least three zones within an IBM Cloud MZR (multizone region). This use of multiple zones provides regional high-availability for the API and prevents downtime if one or two of the zones within the region become unavailable.

It is unlikely that an entire region becomes unavailable, but if it does happen then any APIs that are deployed in that region are inaccessible. For critical API traffic, IBM recommends that you deploy an API in at least two regions and globally load balance the regions. You can configure global load balancing with a technology such as {{site.data.keyword.cis_full}} (CIS). CIS provides health checking and routing rules to ensure that API traffic is automatically routed to the nearest healthy region. For more information about global load balancing, see the [Global Load Balancer (GLB) documentation](/docs/infrastructure/cis?topic=cis-global-load-balancer-glb-concepts).


## Recovering from a disaster
{: #recover-ha_disrec}

No customer action is required to restore an API if a disaster occurs.

If an entire MZR becomes inoperative (usually due to a catastrophic disaster or failure), IBM will execute disaster-recovery plans to restore service within 24 hours or less. IBM will restore the service in an alternate MZR from an IBM-managed backup. Existing DNS names will be migrated to the backup deployment. When the disaster recovery process is complete, API traffic will automatically resume.

When the primary MZR is restored, the secondary deployment is migrated back to the primary site. After the migration is complete, the DNS is restored to its original routing.

