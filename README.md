# Graylog3 supported
``Content Pack for NetFilter Logs with Graylog``  
  
This Content Pack will automatically parses your netfilter logs, and will parse it based on the traffic headers. It appends ``IP_HEADER_``, ``TCP_HEADER_``, and ``UDP_HEADER_`` to all the appropriate fields. It also includes setting GeoIP, so ensure you download the current City db from Maxmind.

### Content Pack includes:

* **GROK patterns**:  
``Defines all new fields to be set when matched in pipeline``
  * NETFILTERHEADER
  * NETFILTERMAC
  * NETFILTERIPHEADER
  * NETFILTERUDPHEADER
  * NETFILTERTCPHEADER
  
* **Pipeline**:  
``Creates Multiple fields to enable stronger queries and analytics``
  * -1 Rules:
    * ``process netfilter logs``
  * 0 Rules:
    * ``process TCP netfilter logs``
    * ``process UDP netfilter logs``
  * 1 Rules:
    * ``Router dst GeoIP Set``
    * ``Router src GeoIP Set``
  
* **Lookup Table\Cache**:
  * geolite2-city (``/etc/graylog/server/GeoLite2-City.mmdb``)
