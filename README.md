# PROV-O BFO Mapping
PROV is to be mapped to, or extended from, the BFO/CCO taxonomy, for the purpose of elevating provenance representation out of the old form, and into an ISO/IEC compliant one.

Both the PROV model and BFO can be had in various serializations, e.g., XML, OWL, etc. BFO is also serialized in Common Logic (CL), which possesses the full expressivity of FOL. For the purpose of the present paper, the OWL serializations of PROV and BFO are used, because the rendering of selected statements in the Terse Triple Language (TTL) format is amenable for both understanding and brevity; moreover, the CCO are only found in TTL format; so, OWL is most useful here. Following are the versions of each ontology utilized in this mapping:

*	PROV-O: recommendation version 2013-04-30
*	BFO: 2020, from 2024-01-29
*	CCO: 1.5, from 2024-02-14

See the mapping paper, [mapping.pdf](mapping.pdf).

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

| Core PROV-O Class | Equivalence or Transformation Rule              |
|-------------------|-------------------------------------------------|
| Activity          | equivalentTo bfo:Process                        |
| Agent             | Introduce as new subclass of bfo:0000023 (Role) |
| Entity            | equivalentTo bfo:Continuant                     |

### PROV-O Expanded Class Mapping
Built atop the Core category of terms, PROV-O Expanded terms allow for more fine-grained provenance descriptions.

| Expanded PROV-O Class | Equivalence or Transformation Rule                                     |
|-----------------------|------------------------------------------------------------------------|
| Organization          | equivalentTo cco:Organization                                          |
| Person                | equivalentTo cco:Person                                                |
| SoftwareAgent         | Introduce as new sub-class of cco:InformationProcessingArtifact        |
| Bundle                | Introduce as new sub-class of bfo:0000002 (Continuant)                 |
| Collection            | equivalentTo bfo:0000115 min 1 bfo:0000002 (Continuant)                |
| EmptyCollection       | equivalentTo bfo:0000115 max 0 bfo:0000002 (Continuant)                |
| Location              | Introduce as  new sub-class of cco:DesignativeInformationContentEntity |

### PROV-O Qualified Class Mapping
The mapping of PROV-O qualified classes is very speculative and requires iterative feedback.

| Qualified PROV-O Class | Equivalence or Transformation Rule |
|------------------------|------------------------------------|
| Influence              | Not directly mappable              |
| EntityInfluence        |                                    |
| Usage                  |                                    |
| Start                  |                                    |
| End                    |                                    |
| Derivation             |                                    |
| PrimarySource          |                                    |
| Quotation              |                                    |
| Revision               |                                    |
| ActivityInfluence      |                                    |
| Generation             |                                    |
| Communication          |                                    |
| Invalidation           |                                    |
| AgentInfluence         |                                    |
| Attribution            |                                    |
| Association            |                                    |
| Plan                   |                                    |
| Delegation             |                                    |
| InstantaneousEvent     |                                    |
| Role                   |                                    |

* Influence is not directly mappable because it is a "broad" term, i.e., an organizational term used to group its sub-influences. If it is to be mapped, it is likely placed best under bfo:0000020 (Specifically Dependent Continuant), perhaps further under bfo:0000017 (Realizable Entity).

## PROV-O Property Mapping

### PROV-O Core Property Mapping

| Core PROV-O Property | Equivalence or Transformation Rule                             |
|----------------------|----------------------------------------------------------------|
| wasGeneratedBy       | Introduce as new sub-property of bfo:0000056 (participates in) |
| wasDerivedFrom       | Import from PROV-O                                             |
| wasAttributedTo      | Not directly mappable                                          |
| startedAtTime        | Introduce as new sub-property of cco:has_datetime_value        |
| used                 | Import from PROV-O                                             |
| wasInformedBy        | Import from PROV-O                                             |
| endedAtTime          | Introduce as new sub-property of cco:has_datetime_value        |
| wasAssociatedWith    | Introduce as new sub-property of bfo:0000056 (participates in) |
| actedOnBehalfOf      | Import from PROV-O                                             |

### PROV-O Expanded Property Mapping

| Expanded PROV-O Property | Equivalence or Transformation Rule                                             |
|---------------------------|-------------------------------------------------------------------------------|
| alternateOf               | Import from PROV-O                                                            |
| specializationOf          | Import from PROV-O                                                            |
| generatedAtTime           | Introduce new sub-property of cco:has_datetime_value                          |
| hadPrimarySource          | Import from PROV-O                                                            |
| value                     | Introduce new data property and set all CCO has_x_value as its sub-properties |
| wasQuotedFrom             | Import from PROV-O                                                            |
| wasRevisionOf             | Import from PROV-O                                                            |
| invalidatedAtTime         | Introduce new sub-property of cco:has_datetime_value                          |
| wasInvalidatedBy          | Import from PROV-O                                                            |
| hadMember                 | owl:equivalentProperty bfo:0000115 (has member part)                          |
| wasStartedBy              | Import from PROV-O                                                            |
| wasEndedBy                | Import from PROV-O                                                            |
| invalidated               | Import from PROV-O                                                            |
| influenced                | Import from PROV-O                                                            |
| atLocation                | Import from PROV-O                                                            |
| generated                 | Introduce new sub-property of bfo:0000057 (has participant)                   |

### PROV-O Qualified Property Mapping
The mapping of PROV-O qualified properties is very speculative and requires iterative feedback.

| Qualified PROV-O Property     | Equivalence or Transformation Rule |
|-------------------------------|------------------------------------|
| wasInfluencedBy               |                                    |
| qualifiedInfluence            | Import from PROV-O                 |
| qualifiedGeneration           | Import from PROV-O                 |
| qualifiedDerivation           | Import from PROV-O                 |
| qualifiedPrimarySource        | Import from PROV-O                 |
| qualifiedQuotation            | Import from PROV-O                 |
| qualifiedRevision             | Import from PROV-O                 |
| qualifiedAttribution          | Import from PROV-O                 |
| qualifiedInvalidation         | Import from PROV-O                 |
| qualifiedStart                | Import from PROV-O                 |
| qualifiedUsage                | Import from PROV-O                 |
| qualifiedCommunication        | Import from PROV-O                 |
| qualifiedAssociation          | Import from PROV-O                 |
| qualifiedEnd                  | Import from PROV-O                 |
| qualifiedDelegation           | Import from PROV-O                 |
| influencer                    |                                    |
| entity                        |                                    |
| hadUsage                      |                                    |
| hadGeneration                 |                                    |
| activity                      |                                    |
| agent                         |                                    |
| hadPlan                       |                                    |
| hadActivity                   |                                    |
| atTime                        |                                    |
| hadRole                       |                                    |

# Not By AI
![](notbyai.png)

https://notbyai.fyi/

Written 100% by humans.
