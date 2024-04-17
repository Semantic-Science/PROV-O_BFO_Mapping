# PROV-O BFO Mapping
PROV is to be mapped to, or extended from, the BFO/CCO taxonomy, for the purpose of elevating provenance representation out of the old form, and into an ISO/IEC compliant one.

Both the PROV model and BFO can be had in various serializations, e.g., XML, OWL, etc. BFO is also serialized in Common Logic (CL), which possesses the full expressivity of FOL. For the purpose of the present paper, the OWL serializations of PROV and BFO are used, because the rendering of selected statements in the Terse Triple Language (TTL) format is amenable for both understanding and brevity; moreover, the CCO are only found in TTL format; so, OWL is most useful here. Following are the versions of each ontology utilized in this mapping:

*	PROV-O: recommendation version 2013-04-30
*	BFO: 2020, from 2024-01-29
*	CCO: 1.5, from 2024-02-14

* Placeholder URI base used for demarcating the mapped terms

# Table of Contents
* [Mapping Details](#mapping-details)
* [PROV-O Class Mapping](#prov-o-class-mapping)
  * [PROV-O Core Class Mapping](#prov-o-core-class-mapping)
  * [PROV-O Expanded Class Mapping](#prov-o-expanded-class-mapping)
  * [PROV-O Qualified Class Mapping](#prov-o-qualified-class-mapping)
* [PROV-O Property Mapping](#prov-o-property-mapping)
  * [PROV-O Core Property Mapping](#prov-o-core-property-mapping)
  * [PROV-O Expanded Property Mapping](#prov-o-expanded-property-mapping)
  * [PROV-O Qualified Property Mapping](#prov-o-qualified-property-mapping)

## Mapping Details
The mapping from PROV to BFO is not performed with any specific software tool, or any purpose-written code. As PROV-O and BFO have essentially no lexical overlap, background knowledge is useful to a mapping between them. The present mapping, as it is preliminary for the purpose of renewing interest in provenance in the face of large-scale generative AI, is conducted manually, using lexical analysis of ontology terms and their definitions, as well as the authors’ experience with both ontologies as a form of background knowledge. Lexico-semantic reasoning for every mapping is given so that the method maintains some measure of replicability. Given the subjectivity of this method, the mapping is not declared as prescriptive, but rather, preliminary.

* All PROV-O classes will be mapped to the closest equivalent BFO/CCO class, asserted as sub-classes of the closest parent BFO/CCO class, or otherwise described as a transformation rule
* All PROV-O object and data properties (i.e., relations or predicates) will be mapped to the closest equivalent BFO/CCO property, or otherwise asserted as sub-properties of the closest parent BFO/CCO property 
* Instances (owl:NamedIndividuals) are ignored for the sake of simplicity
* Annotation properties are ignored for the sake of simplicity
* No OWL reasoning is performed, as the mapping is preliminary and, therefore, speculative

## PROV-O Class Mapping

### PROV-O Core Class Mapping
The mapping begins with the three Core, or “Starting Point” classes of PROV-O. The Core classes are the basis of PROV-O, allowing for the creation of simple provenance descriptions.

| Core PROV-O Class | Equivalence or Transformation Rule |
|-------------------|------------------------------------|
| Activity          | equivalentTo bfo:Process           |
| Agent             | Introduce new subclass of bfo:Role |
| Entity            | equivalentTo bfo:Continuant        |

### PROV-O Expanded Class Mapping
Built atop the Core category of terms, PROV-O Expanded terms allow for more fine-grained provenance descriptions.

### PROV-O Qualified Class Mapping

## PROV-O Property Mapping

### PROV-O Core Property Mapping

### PROV-O Expanded Property Mapping

### PROV-O Qualified Property Mapping

# Not By AI
![](notbyai.png)

https://notbyai.fyi/

Written 100% by humans.
