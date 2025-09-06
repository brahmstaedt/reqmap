# Requirements Mapper

## Problem
When designing a product, manufacturers need to obey externally defined requirements in the form of norms, standards, guidelines, checklists etc. Those are issued from multiple sources such as regulatory authorities, standardization organizations, industry best-practices etc. Those sources often contain duplicate content and may even contradict each other. A manufacturer needs to identify applicable sources of external requirements and then consolidate those. The consolidation is an time consuming effort that needs to be spent by every manufacturer again

## Goals 
Manufacturers would benefit from collaborating in the area of external requirements in a number of ways:
* Reducing duplicate efforts across manufacturers
* Defining a common understanding by manufacturers 
* Driving the harmonization towards providers of sources

## General mechanics
To approach the problem, the following steps are needed:
* Relevant sources external requirements need to be identified
* Each source must be provided in a machine-readable document that allows to reference individual requirements
* A document containing the internal requirements needs to be created
* A mapping table contains references between the internal and external requirements
* For a specific set of external requirement sources, a computer program shall
  * compile a list of internal requirements that implement these sources
  * compile a compliance record that shows traceability for each requirement in each external source towards the internal requirements as well as the coverage 

Additional constraints need to be considered when implementing this approach:
* Information created as part of this initiative can be public or can be shared just among a closed group of manufacturers that have chosen to collaborate in for a specific subset of activities
* Some external sources of requirements are not public but require licensing. Their contents cannot be published as part of this initiative but must remain locally with those users that have licensed the content.
* Requirements are not static over time but may change both in general interpretation as well as by addendums release from the source
* Individual manufacturers may disagree with the general interpretation of external requirements and may not even want to share their internal understanding publicly. A mechanism must exist that allows local overrides of the general interpretation.
* The compiled list of internal requiments must be provided in both a machine-readable format for further processing as well as in a human-readable format for closer inspection. It must be possible to structure that document into chapters. e.g. by tagging the internal requiremnts
* An external source of requirements may not be applicable fully, but only certain subsets of it. The source may for example define security levels 1-4 but only the requirements in levels 1 and 2 may be applicable.
* Multiple external sources may define the same requirement but with a variable content; for example the minimum key length of a crypto algorithm. This should be represented by only one internal requirement containing a variable and the application should be able to calculate the consolidated minimum required key length

## Repository contents
When completed, this repository shall contain the following content
* `/src`  - the source code of the application to compile lists and traceability
* `/data/source/`  - the source documents, one for each external norm, standard, etc.
* `/data/sink/`   - files containing the internal requirements
* `/data/mapping/`  - files containing the mapping between external and internal requirements
* `/doc`   - documentation for this initiative and processes

## Next steps
* Define dummy data for the source, sink and mapping to showcase examples and determine a minimum file format
* Implement an application that, can create the intended output