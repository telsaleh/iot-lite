IoT-Lite Ontology
=================

Working Draft
-------------

### Authors

- [Maria Bermudez-Edo](http://www.ugr.es/~mbe/M._Bermudez-Edo/ "Software Engineering Department, University of Granada, Granada, Spain"), [Software Engineering Department](http://www.ugr.es/ "Software Engineering Department, University of Granada, Granada, Spain"), University of Granada

- [Tarek Elsaleh](http://www.surrey.ac.uk/ics/people/tarek_elsaleh/ "Institute for Communication Systems, University of Surrey, Guildford, United Kingdom"), [Institute for Communication Systems](http://www.surrey.ac.uk/ics/ "Institute for Communication Systems, University of Surrey, Guildford, United Kingdom"), University of Surrey

- [Payam Barnaghi](http://www.surrey.ac.uk/ics/people/payam_barnaghi/index.htm "Institute for Communication Systems, University of Surrey, Guildford, United Kingdom"), [Institute for Communication Systems](http://www.surrey.ac.uk/ics/ "Institute for Communication Systems, University of Surrey, Guildford, United Kingdom"), University of Surrey

### Contributors

This work is part of the [EU FP7 FIWARE project](http://www.fiware.org/) and the [EU H2020 FIESTA-IoT project](http://www.fiesta-iot.eu/) at the [Institute for Communication Systems](http://www.surrey.ac.uk/ics/), University of Surrey.

### Publications

- Maria Bermudez-Edo, Tarek Elsaleh, Payam Barnaghi and Kerry Taylor, ["IoT-Lite: A Lightweight Semantic Model for the Internet of Things"](https://doi.org/10.1109/UIC-ATC-ScalCom-CBDCom-IoP-SmartWorld.2016.0035), in Proc. of the IEEE Conferences on Ubiquitous Intelligence and Computing, July 2016, Toulouse, France.

- Maria Bermudez-Edo, Tarek Elsaleh, Payam Barnaghi and Kerry Taylor, ["IoT-Lite: a lightweight semantic model for the internet of things and its use with dynamic semantics"](https://doi.org/10.1007/s00779-017-1010-8), Personal and Ubiquitous Computing (2017).

* * *

You are granted a license to use, reproduce and create derivative works of this document under [Creative Commons Attribution 3.0 Unported License](http://creativecommons.org/licenses/by/3.0/). This copyright applies to the iot-lite ontology specification and RDF. [![Creative Commons License](./iot-lite/figures/80x15.png)](http://creativecommons.org/licenses/by/3.0/)

* * *

Abstract
--------

IoT-Lite ontology is a lightweight ontology to represent Internet of Things (IoT) resources, entities and services. IoT-Lite is an instantiation of the [SSN ontology](http://www.w3.org/2005/Incubator/ssn/ssnx/ssn). The lightweight allow the representation and use of IoT platforms without consuming excessive processing time when querying the ontology. However it is also a meta ontology that can be extended in order to represent IoT concepts in a more detailed way in different domains. It also can be combined with ontologies representing IoT data streams such as [SAO ontology](http://purl.oclc.org/NET/UNIS/sao/sao#). Following best practices in ontology engineering IoT-Lite is meant to be used with a quantity taxonomy, such as [qu-taxo](http://purl.oclc.org/NET/UNIS/fiware/iot-lite/qu-taxo#) or [m3-lite](http://purl.org/iot/vocab/m3-lite#), that allows the discovery and interoperability of IoT resources in heterogeneous platforms using a common vocabulary.

Status of this Document
-----------------------

**This is a work in progress and as such is subject to change.** Comments are very welcome, please send them to [First Author](/cdn-cgi/l/email-protection#cca1aea98cb9abbee2a9bf).

1.  [Introduction](http://iot.ee.surrey.ac.uk/fiware/ontologies/iot-lite#intro)
2.  [Example](http://iot.ee.surrey.ac.uk/fiware/ontologies/iot-lite#sec-examples)
3.  [IoT-Lite Ontology at Glance](http://iot.ee.surrey.ac.uk/fiware/ontologies/iot-lite#sec-glance)
4.  [Cross-reference for IoT-Lite classes and Object Properties](http://iot.ee.surrey.ac.uk/fiware/ontologies/iot-lite#class-reference)


* * *

1\. Introduction
----------------

The Internet of Things (IoT) is machine-to-machine communications and interactions between objects, devices and people. In the near future the communications and information processing will be ubiqutious and performed by IoT systems.

Over the past few years the semantics community has developed ontologies to describe concepts and relationship between different entities in various domains. The Internet of Things (IoT) domain have similar approaches to apply semantics. A key problem is that most of the IoT related semantic descriptions are not as widely adopted as expected. One of the main concerns users and developers have is that semantics increase the complexity and processing time and therefore they are unsuitable for dynamic and responsive environments such as the IoT.

Complex models, although can be applied for querying almost anything about objects, are often difficult to implement and use. They need high processing and therefore they are not suitable for constrained environments. IoT models should consider the constrains and dynamicity of the IoT environments. At the same time, they need to model the relationships and concepts that represent and allow interoperability between IoT entities. Therefore, expressiveness versus complexity is a challenge.

We propose IoT-Lite, a lightweight instantiation of the [semantic sensor network (SSN) ontology](http://www.w3.org/2005/Incubator/ssn/ssnx/ssn) [1](#ref1) to describe the key IoT concepts that allows interoperability and discovery of sensory data in heterogeneous IoT platforms. IoT-lite reduces the complexity of other IoT models describing only the main concepts of the IoT domain. IoT-Lite can be extended by different models to increment it expressiveness.

IoT-Lite describes IoT concepts in three classes. [Objects](#term_Object), [system or resources](http://purl.oclc.org/NET/ssnx/ssn#System) and [services](#term_Service). IoT devices are classified into, although not restricted to, three classes: [sensing devices](http://purl.oclc.org/NET/ssnx/ssn#SensingDevice) [actuating devices](#term_ActuatingDevice) and [tag devices](#term_TagDevice). IoT-Lite is focused on sensing, although it has a high level concept on actuation that allows any future extension on this area. Services are described with a [coverage](#term_Coverage). This coverage represents the 2D-spatial covered by the IoT device.

The figure below depicts the concepts of the ontology and the main relationships between them.

  

![IoT lite Ontology](https://www.dropbox.com/s/8oeous3nmc8f9te/iot-lite_v11_model.png?dl=1)

  
  
IoT Lite Ontology is created to be used with a common [taxonomy](http://purl.oclc.org/NET/UNIS/fiware/iot-lite/iot-taxo#) to describe the [Units](http://iot.ee.surrey.ac.uk/fiware/ontologies/iot-lite#term_Units) and [QuantityKind](http://iot.ee.surrey.ac.uk/fiware/ontologies/iot-lite#term_QuantityUnits) that IoT devices can meassure. This taxonomy represent individuals in the ontology and is based in well-known taxonomies as: [qu](http://www.w3.org/2005/Incubator/ssn/wiki/QU_Ontology) and [qudt](http://www.qudt.org/).

2\. Example
-----------

As an example of a sensor device, let's take the SmartICS IoT Egg.

![Example IoT lite Ontology](https://www.dropbox.com/s/maiy6kup4uy832i/iot-egg.png?dl=1)

  
  

The following is an exemplification of the annotated sensor device.

  
  

![Example IoT lite Ontology](https://www.dropbox.com/s/uf1gnt0wqll7h9t/iot-lite-instance.png?dl=1)

  
  

The example in turtle is:

Example

```turtle   
@prefix :      <http://purl.oclc.org/NET/UNIS/fiware/iot-lite#> .
@prefix iot-lite: <http://purl.oclc.org/NET/UNIS/fiware/iot-lite#> .
@prefix qu:    <http://purl.org/NET/ssnx/qu/qu#> .
@prefix owl:   <http://www.w3.org/2002/07/owl#> .
@prefix fiesta-res: <http://platform.fiesta-iot.eu/srd/registry/v1/> .
@prefix xsd:   <http://www.w3.org/2001/XMLSchema#> .
@prefix rdfs:  <http://www.w3.org/2000/01/rdf-schema#> .
@prefix m3-lite: <http://purl.org/iot/vocab/m3-lite#> .
@prefix ssn:   <http://purl.oclc.org/NET/ssnx/ssn#> .
@prefix geo:   <http://www.w3.org/2003/01/geo/wgs84\_pos#> .
@prefix sc:    <http://smartcampus.iot.ee.surrey.ac.uk/smart-ics#> .
@prefix rdf:   <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xml:   <http://www.w3.org/XML/1998/namespace> .
@prefix qu-rec20: <http://purl.org/NET/ssnx/qu/qu-rec20#> .
@prefix time:  <http://www.w3.org/2006/time#> .

sc:smart-ics  a                 ssn:System ;
        iot-lite:isSubSystemOf  sc:SmartCampus .

fiesta-res:IoT-Node1TEMPERATURE
        a                         ssn:SensingDevice ;
        iot-lite:hasQuantityKind  m3-lite:Temperature ;
        iot-lite:isExposedBy      sc:service#iot-egg-001 ;
        iot-lite:isSubSystemOf    sc:smart-ics ;
        ssn:onPlatform            sc:ICS-Desk1 .

sc:service#iot-egg-001
        a                  iot-lite:Service ;
        iot-lite:endpoint  "http://smart-ics.surrey.ac.uk/fiesta-iot/service/iot-egg-001-temp" .

sc:CII-UNIS-GU2-UK-ICS-Desk1
        a                          geo:Point ;
        iot-lite:RelativeLocation  "ICS-Desk1" ;
        geo:lat                    "51.4" ;
        geo:long                   "-0.51" .

sc:SmartCampus  a  ssn:System .

sc:ICS-Desk1  a       ssn:Platform ;
        geo:location  sc:CII-UNIS-GU2-UK-ICS-Desk1 .

fiesta-res:IoT-Node1  a   ssn:Device ;
        ssn:hasSubSystem  fiesta-res:iot-egg-001-temp .
```        
                            

3\. IoT Lite Ontology at Glance
-------------------------------

An alphabetical index of IoT Lite terms, by class (concepts) and properties are given below. All the terms are hyperlinked to their detailed description for quick reference.

Classes: [ActuatingDevice](#term_ActuatingDevice), [TagDevice](#term_Tag), [Object](#term_Object), [Attribute](#term_Attribute), [Circle](#term_Circle), [Coverage](#term_Coverage), [Device](#term_Device), [Metadata](#term_Metadata), [Polygon](#term_Polygon), [Rectangle](#term_Rectangle), [Service](#term_Service),

Properties: [relativeLocation](#term_relativeLocation), [altRelative](#term_altRelative), [interfaceDescription](#term_interfaceDescription), [endpoint](#term_endpoint), [exposedBy](#term_exposedBy), [hasAttribute](#term_hasAttribute), [hasCoverage](#term_hasCoverage), [hasMetadata](#term_hasMetadata), [hasPoint](#term_hasPoint), [hasQuantityKind](#term_hasQuantityKind), [hasUnit](#term_hasUnit), [id](#term_id), [radius](#term_radius), [interfaceType](#term_interfaceType), [isOnline](#term_isOnline), [isMobile](#term_isMobile),
