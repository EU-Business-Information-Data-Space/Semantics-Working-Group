# Mapping of standards to a common BIDS Vocabulary/Ontology/aka Library of Reusable Semantic Components
In the [Business Information Data Space](BIDS_Rulebook_v0.1.md), like in any data space, all data products need to be modeled using the same semantic foundation aka a common "ontology" or "vocabulary" that is based on concepts that the data space governance body has agreed upon. This ensures the semantic interoperability of all data products regardless of in what technical format they have been implemented or for what concrete business use they have been developed.
<p>The mainstream approach to data space semantics is to refer to "standards" and their use as a solution for enabling both a common understanding and common formats for the data products. However, this is true only if there is only one acknowledged standard that all participants in the data space have agreed to use. In the BIDS context, the data space itself is extremely broad, since it encompasses all types of information that can be considered relevant for "business entities" and "busines activities". There are and will always be a huge number of conflicting artefacts describing sinimilar and sometimes even identical data constructs. From the BIDS perspective and specifically the perspective of a single actor involved in business activities, there's a need for a unifying view of the descriptions of data that is used, produced and exchanged in this context. 
  
### How do we proceed with the creation of this unified view?
In the context of the BIDS, since it is a European Data Space, we should look for guidance in the DSSC Blueprint:
<img src="https://dssc.eu/download/attachments/357075098/image-20240214-145201.png" alt="DSSC Image" width="85%"/>
<p>The different "standards" mentioned previously can in this context be seen as instances of different "vocabulary based ontologies" that need to be mapped together into one "master vocabulary/ontology" for the data space. (The distinction between the terms "vocabulary" and "ontology" is unfortunately not universally accepted, which sometimes leads to confusion.)
<p></p>The Finnish Ministry of Finance and the Digitalization Agency DVV have developed a integrated toolset for the creation of all of the artefacts described in the DSSC modeling approach in the picture. One of the key benefits of this "Interoperability Platform" is the fact that it enables 

- the seamless creation of a "linked chain" of data descriptions, ending not only at the metadata level but leading to actual data products in various technical formats like W3C Verifiable Credentials 
- the linking of external vocabularies and ontologies to the data description artefacts that are modeled manually with the IoP tools; aka linking for instance a class or property in a IoP developed model to a class or property in an external vocabulary/ontology

The process for the creation of data products that are based on "interlinked" data desriptions, which are inheretly semantically interoperable is as follows:

1. Define the essential concepts that are needed for commonly developed descriptions of the data products involved by creating a SKOS Ontology with the Terminologies tool of the IoP
2. Model a Business Information Core Vocabulary (BICV) with the Data Vocabularies tool of the IoP
3. Choose which external standards, vocabularies, reference data models or ontologies the BIDS data product descriptions need to be aligned with (a proposal for a list of these can be found at the end of this document)
4. Link the classes, attributes and associations in the BICV to the relevant classes and properties in the external models (namespaces) decided upon in step 3; NB: actual linking to external namespaces requires that the vocabularies/ontologies are W3C Semantic Web / Linked Data compliant aka have resolvable URIs and have content negotiation enabled on the publication server > this issue needs to be addressed specifically by the BIDS Governance Body
5. Model unique data products as application profiles (SHACL Shapes), reusing the reusable components of the BICV and the accompanying code lists created with the Reference Data tool of the IoP
6. Produce actual data product schemas by using the Export feature of the Data Vocabularies tool; the SHACL Shape application profile is converted to either JSON-LD, JSON, RDF, Turtle, OpenAPI or other necessary technical formats.
7. Outside the scope of the Semantic Group Work; use the created data product descriptions (preferrably as JSON-LD schemas) to map data sets in legacy systems to the semantically interoperable schema and publish the data sharing mechanism in a data catalogue or another applicable format that enables the discovery of the data products that are on offer.

Annex 1: List of external vocabularies/ontologies relevant for BIDS

Directly linkable as W3C Linked Data
- UN/CEFACT BSP Vocabulary
- UN/CEFACT DPP Vocabulary
- Schema.org
- FOAF
- GS1 Vocabulary
- FEDeRATED ontologies
- ELM vocabulary

 Vocabularies/ontologies that need minor or major revisions in order to be compatible
- UN/CEFACT CCL
- IATA One Record
- UBL 2.x
- EU Core Person vocabulary
- EU Core Business vocabulary
- EU Core Location vocabulary
- Core Criterion and Core Evidence Vocabulary
- W3C Registered Organization Vocabulary
- W3C Legal Entity Vocabulary
- W3C Asset Description Metadata Schema
