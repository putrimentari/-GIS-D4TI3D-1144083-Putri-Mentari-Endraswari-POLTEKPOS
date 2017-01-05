A Proxy is a proxy folder open source for geospatial data. This cache to accelerate and change data from existing map services and cater to every desktop or web GIS client.

Server folder is to transform the vector file shp geospatial web services into the picture.

Name : Putri Mentari E

Class : D4 TI 3D

NPM ; 1144083

Codingan :

services:

  demo:

  tms:

    use\_grid\_names: true

    # origin for /tiles service

    origin: &#39;nw&#39;

  kml:

      use\_grid\_names: true

  wmts:

    # use restful access to WMTS

    restful: true

    # this is the default template for MapProxy

    restful\_template: &#39;/{Layer}/{TileMatrixSet}/{TileMatrix}/{TileCol}/{TileRow}.{Format}&#39;

    # and also allow KVP requests

    kvp: true

    md:

      # metadata used in capabilities documents for WMTS

      # if the md option is not set, the metadata of the WMS will be used

      title: Awangga GeoMap

      abstract: This is the Awangga GeoMap.

      online\_resource: http://www.awangga.net/

      contact:

        person: Rolly Maulana Awangga

        position: Software Engineer

        organization: Belant Persada

        address: Jl. Ligar Nyawang No.2

        city: Bandung

        postcode: 40191

        country: Indonesia

        phone: +62(0)813-12000-300

        fax: +62(0)813-12000-300

        email: rolly@awang.ga

      # multiline strings are possible with the right indention

      access\_constraints:

        This service is intended for Sekretariat Negara Only.

        The data is under development on Sekretarian Negara Republik Indonesia.

        (http://setneg.go.id/)

      fees: &#39;None&#39;

  wms:

    md:

      title: MapProxy WMS Proxy

      abstract: This is a minimal MapProxy example.

layers:

  - name: agm

    title: Awangga Geo Map - www.awangga.net

    sources: [agm\_cache]

caches:

  agm\_cache:

    grids: [webmercator]

    sources: [agm\_source]

sources:

  agm\_source:

    type: mapserver

    req:

      layers: roads

      map: /var/mapdata/mapfile/agm.map

    coverage:

      bbox: [94.5011475, -11.007385, 141.01947, 6.076721]

      srs: &#39;EPSG:4326&#39;

    mapserver:

      binary: /usr/libexec/mapserver

      working\_dir: /var/mapdata/tmp

    supported\_srs: [&#39;EPSG:4326&#39;]

grids:

    webmercator:

        base: GLOBAL\_WEBMERCATOR

globals:

