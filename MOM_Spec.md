# Master Object Model Specification for the Total Learning Architure

**Abstract**: This Standard defines a controlled vocabulary and key processes to be followed when communicating learner data between activities, content, devices, systems, platforms, and organizational/institutional boundaries. It utilizes the IEEE Standard xAPI (9274.1.1) and the associated xAPI Profile standard (9274.3.1) to define how components of the Total Learning Architecture (TLA) communicate, store, and propagate learning information between computational and data assets located throughout the Future Learning Ecosystem. It provides a JSON binding of such data that is also conformant to the IEEE xAPI Profile Standard.

**Keywords**: 9274.1.1, 9274.3.1, JavaScript Object Notation, JSON, Experience API, xAPI, Total Learning Architecture, TLA, Profile, xAPI Profile

# Contents
 - [Overview](./MOM_Spec.md#Overview)
      - [Scope](./MOM_Spec.md#Scope)
      - [Purpose](./MOM_Spec.md#Purpose)
      - [Word usage](./MOM_Spec.md#Word-Usage)
 - [Normative references](./MOM_Spec.md#Normative-References)
 - [Definitions, acronyms, and abbreviations](./MOM_Spec.md#DAaA)
      - [Definitions](./MOM_Spec.md#Definitions)
      - [Acronyms and abbreviations](./MOM_Spec.md#AaA)
 - [Conformance](./MOM_Spec.md#Conformance)
      - [TLA conformance level 1](./MOM_Spec.md#Level1)
      - [TLA conformance level 2](./MOM_Spec.md#Level2)
      - [TLA conformance level 3](./MOM_Spec.md#Level3)
      - [TLA conformance level 4](./MOM_Spec.md#Level4)
      - [TLA conformance level 5](./MOM_Spec.md#Level5)
 - [TLA xAPI JSON-binding definition](./MOM_Spec.md#TLA-xAPI)
      - [Statement data requirements](./MOM_Spec.md#Statement-data-requirements)
           - [Waived](./MOM_Spec.md#Waived)
           - [Launched](./MOM_Spec.md#Launched)
           - [Completed](./MOM_Spec.md#Completed) 
           - [Passed](./MOM_Spec.md#Passed)
           - [Failed](./MOM_Spec.md#Failed)
           - [Satisfied](./MOM_Spec.md#Satisfied)
           - [Abandoned](./MOM_Spec.md#Abandoned)
           - [Terminated](./MOM_Spec.md#Terminated)
           - [Initialized](./MOM_Spec.md#Initialized)
           - [Recommended](./MOM_Spec.md#Recommended)
           - [Prioritized](./MOM_Spec.md#Prioritized)
           - [Organized](./MOM_Spec.md#Organized)
           - [Projected](./MOM_Spec.md#Projected)
           - [Planned](./MOM_Spec.md#Planned)
           - [Deselected](./MOM_Spec.md#Deselected)
           - [Requested](./MOM_Spec.md#Requested)
           - [Approved](./MOM_Spec.md#Approved)
           - [Augmented](./MOM_Spec.md#Augmented)
           - [Explored](./MOM_Spec.md#Explored)
           - [Clarified](./MOM_Spec.md#Clarified)
           - [Directed](./MOM_Spec.md#Directed)
           - [Scheduled](./MOM_Spec.md#Scheduled)
           - [Assessed](./MOM_Spec.md#Assessed)
           - [Contextualized](./MOM_Spec.md#Contextualized)
           - [Located](./MOM_Spec.md#Located)
           - [Asserted](./MOM_Spec.md#Asserted)
           - [Validated](./MOM_Spec.md#Validated)
           - [Inferred](./MOM_Spec.md#Inferred)
           - [Qualified](./MOM_Spec.md#Qualified)
           - [Certified](./MOM_Spec.md#Certified)
           - [Verified](./MOM_Spec.md#Verified)
           - [Conferred](./MOM_Spec.md#Conferred)
           - [Recruited](./MOM_Spec.md#Recruited)
           - [Appraised](./MOM_Spec.md#Appraised)
           - [Detailed](./MOM_Spec.md#Detailed)
           - [Mobilized](./MOM_Spec.md#Mobilized)
           - [Employed](./MOM_Spec.md#Employed)
           - [Schooled](./MOM_Spec.md#Schooled)
           - [Promoted](./MOM_Spec.md#Promoted)
           - [Screened](./MOM_Spec.md#Screened)
           - [Selected](./MOM_Spec.md#Selected)
           - [Transitioned](./MOM_Spec.md#Transitioned)
           - [Released](./MOM_Spec.md#Released)
           - [Restricted](./MOM_Spec.md#Restricted)
           - [Voided](./MOM_Spec.md#Voided)
           - [Attended](./MOM_Spec.md#Attended)
           - [Experienced](./MOM_Spec.md#Experienced)
           - [Mastered](./MOM_Spec.md#Mastered)
           - [Resumed](./MOM_Spec.md#Resumed)
           - [Scored](./MOM_Spec.md#Scored)
           - [Suspended](./MOM_Spec.md#Suspended)
           - [Registered](./MOM_Spec.md#Registered)
      - [LRS storage requirements](./MOM_Spec.md#LRS-storage-requirements)
      - [TLA environment reporting requirements](./MOM_Spec.md#TLA-environment-reporting-requirements)
           - [Competency management function](./MOM_Spec.md#Competency-management-function)
           - [Learning event management function](./MOM_Spec.md#Learning-event-management-function)
           - [Activity provider function](./MOM_Spec.md#Activity-provider-function)
           - [Human capital management function](./MOM_Spec.md#Human-capital-managementfunction)
 - [Annex A](./MOM_Spec.md#A40)
 - [Annex B](./MOM_Spec.md#B41)
 - [Annex C](./MOM_Spec.md#C44)
 - [Annex D](./MOM_Spec.md#D46)
 - [Annex E](./MOM_Spec.md#E47)

<a name="Overview"></a>
# Overview
The scope and purpose of this Standard are discussed in 1.1 and 1.2.

<a name="Scope"></a>
## Scope
This Standard defines a set of controlled vocabulary and processes to be followed when the IEEE Standard xAPI (9274.1.1) is used in an environment categorized as conformant to the Total Learning Architecture. It provides a JSON binding of such data that is also conformant to the IEEE xAPI Profile Standard (9274.3.1). This standard defines the structure and constraints of JSON data in this environment. This standard may be used as an xAPI profile in that elements of this standard may be extracted and used in other profiles, or independent of a TLA-conformant technology.

<a name="Purpose"></a>
## Purpose
The purpose of this Standard is to allow the creation of interoperable xAPI instances across learning environments that adopt the TLA. This Standard uses a JSON encoding that is also conformant to the xAPI and xAPI Profile standards, which allows for interoperability and the exchange of xAPI data between all components of the TLA.

<a name="Word-Usage"></a>
## Word usage
The word _shall_ indicates mandatory requirements strictly to befollowed in order to conform to the standard and from which no deviation is permitted (shall equals is required to). <sup>[[1]](#foot-1)</sup> <sup>[[2]](#foot-2)</sup>

The word _should_ indicates that among several possibilities one isrecommended as particularly suitable, without mentioning or excludingothers; or that a certain course of action is preferred but notnecessarily required (should equals is recommended that).

The word _may_ is used to indicate a course of action permissible withinthe limits of the standard (may equals is permitted to).

The word _can_ is used for statements of possibility and capability,whether material, physical, or causal (can equals is able to).

<a name="NormativeReferences"></a>
# Normative references
The following referenced documents are indispensable for the application of this Standard. For dated references, only the edition cited applies. For undated references, the latest edition of the referenced document (including any amendments or corrigenda) applies.

IEEE Std 9274.1.1, Experience API (xAPI) Standard. <sup>[[3]](#foot-3)</sup>

IEEE Std 9274.3.1, Experience API (xAPI) Profile Standard. <sup>[[4]](#foot-4)</sup>

Cmi5 Specification <sup>[[5]](#foot-5)</sup>

RFC 8256: The JavaScript Object Notation (JSON) Data Interchange Format <sup>[[6]](#foot-6)</sup>

<a name="DAaA"></a>
# Definitions, acronyms, and abbreviations
Definitions and acronyms are defined in 3.1 and 3.2, respectively.

<a name="Definitions"></a>
## Definitions
For the purposes of this Standard, the following terms and definitions apply _The Authoritative Dictionary of IEEE Standards Terms_ <sup>[[7]](#foot-7)</sup>
 should be referenced for

terms not defined in this clause.

**actor** : An individual, organization, technology, or other provider of data within a learning experience or acting within the TLA. In an xAPI statement, the &quot;doer&quot; of the statement.

**authoritative LRS:** A classification of LRS that stores a record of learner proficiency that is aligned with an individual&#39;s associated competency frameworks. It has the purpose of disallowing certain persons access to certain types of data. Only an Observer, Instructor, Controller, Supervisor (OICS) can access an authoritative LRS. The Authoritative LRS stores digitally signed xAPI records of conferred credentials and other competency assertions.

**competency:** Formally defined, organized, and structured description of knowledge, skills, attributes, and other characteristics that can be used to manage human capital. Each competency can have a wide range of associated metadata (e.g. description, type, scope, level, and context) and associated resources (e.g. assessments, operations manuals, and training content).

**competency framework:** A data model for describing, referencing, and sharing competency definitions, primarily in the context of learning and development. It provides a formal representation of the key characteristics of a competency, independently of its use in any particular context. It enables interoperability among learning systems that deal with competency information by providing a means for them to refer to common definitions with common meanings.

**Experience API (xAPI):** An IEEE Standard (9274.1.1) that establishes data formats and protocols for learning experience data. Most of the requirements around creation, storage, and retrieval of JSON data.

**JavaScript Object Notation (JSON):** A format of JavaScript that has specific structure and properties. These include use of structured name/value pairs and an ordered list of values.

**Learning Record Provider (LRP):** A system/service that creates xAPI data and sends it to an LRS. An LRP is responsible for the quality and structure of xAPI data.

**Learning Record Store (LRS):** The basic storage and retrieval web service, often implemented as a system, for xAPI data.

**Master Object Model (MOM):** The TLA policy framework includes a Master Object Model (TLA MOM) that specifies event triggers between TLA core components. The TLA MOM is an xAPI profile that defines the activity streams that create the events to manage TLA federation execution.

**noisy LRS -** An LRS without additional data restrictions seen in an Authoritative LRS. This LRS is typically associated with a specific learning activity, device, or system and is used to house all xAPI statements generated by that system. These statements are used to drive additional interventions or functionality within that system but only the TLA MOM verbs are communicated to other TLA components or activities.

**Observer/Instructor/Controller/Supervisor (OICS):** An actor with increased permission to access learner data. The only allowable user of an authoritative LRS.

**profile:** Additional rules to be applied from a base specification. This document is a profile of xAPI, meaning that in order to be conformant to the profile, the technology shall also be conformant to xAPI.

**statement:** A basic unit of learning experience data as defined in the xAPI standard. A statement is formatted using JSON and has among its properties, actor, verb, and object.

**Total Learning Architecture (TLA):** A research and development activity sponsored by the ADL Initiative and conducted in collaboration with stakeholders from across the defense community, professional standards organizations, and commercial industry. The TLA project will result in a collection of policy, specifications (including this document), and standards for connecting &quot;any device, anywhere, any time&quot; to generate learning-related data enabling next-generation learning that is integrated, personalized, and data-driven.

**transactional LRS:** An LRS without additional data restrictions seen in an authoritative LRS. While the noisy LRS collects all xAPI statements, the transactional LRS only collects learner data that is conformant to the TLA Meta Object Model (MOM). This allows learner performance information to be normalized as it is processed by a Competency Management System. A transactional LRS is trusted within TLA.

**verb:** The most defining property in an xAPI statement – the &quot;action&quot; of the statement. A verb is an IRI, often shortened when being described, that uniquely identifies a tracked interaction.

<a name="AaA"></a>
## Acronyms and abbreviations
JSON – JavaScript Object Notation

LPR: Learning Record Provider

LRS: Learning Record Store

OICS: Observer/Instructor/Controller/Supervisor

TLA: Total Learning Architecture

xAPI: Experience API

<a name="Conformance"></a>
# Conformance
Conformance to this Standard is discussed in 4.1 through 4.5. Please see Section 1.3, Word Usage, to determine the nature of requirements found in this section. The TLA proscribes multiple levels of conformance. There are requirements for conformance that are both in scope and out of scope of this document. The requirements for xAPI data are listed in 4.1 through 4.5. It is expected that all TLA systems (LRS, LRP, etc.) follow the requirements appropriate to their function in a TLA environment.

<a name="Level1"></a>
## TLA conformance level 1
An instance of TLA level 1

- Shall conform to the xAPI Standard
- Shall conform to the xAPI Profile Standard
- Should conform to the cmi5 Specification (in regard to xAPI statements)
- Shall implement general requirements as found in 5.1
- Shall implement statements using the &quot;certified&quot; verb with all requirements fulfilled.
- Should implement statements using the &quot;completed&quot; verb. If implemented, shall be done so with all requirements fulfilled.
- Should implement statements using the &quot;passed&quot; verb. If implemented, shall be done so with all requirements fulfilled.
- Should implement statements using the &quot;failed&quot; verb. If implemented, shall be done so with all requirements fulfilled.
- Shall implement statements using the &quot;success&quot; result in at least one of statements that use the &quot;completed&quot;, &quot;passed&quot;, or &quot;failed&quot; verbs.
- May implement statements with verbs found in section 5.1. If implemented, shall be done so with all requirements fulfilled from corresponding section in 5.1
- May implement statements with verbs not found in this specification
- Shall send statements to their appropriate LRS as defined in 5.2
- Should generate statements in appropriate systems as defined in 5.3

<a name="Level2"></a>
## TLA conformance level 2
An instance of TLA level 2

- Shall follow requirements of all TLA level 1
- Shall conform to the cmi5 Specification (in regard to xAPI statements)
- Shall implement statements using the &quot;completed&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;passed&quot; verb with all requirements fulfilled. 
- Shall implement statements using the &quot;passed&quot; verb using the &quot;success&quot; result property if the object type is &quot;assessment&quot;
- Shall implement statements using the &quot;failed&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;failed&quot; verb using the &quot;success&quot; result property if the object type is &quot;assessment&quot;
- Shall implement statements using the &quot;launched&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;initialized&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;waived&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;satisfied&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;abandoned&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;terminated&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;attended&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;experienced&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;mastered&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;resumed&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;scored&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;suspended&quot; verb with all requirements fulfilled.

<a name="Level3"></a>
## TLA conformance level 3
An instance of TLA level 3

- Shall follow requirements of all TLA level 1-2
- Shall implement authority in xAPI statements that use verbs that require an authoritative source, as defined in 5.1.
- Shall implement statements using the &quot;assessed&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;contextualized&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;located&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;captured&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;asserted&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;validated&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;inferred&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;qualified&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;certified&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;verified&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;conferred&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;registered&quot; verb with all requirements fulfilled.

<a name="Level4"></a>
## TLA conformance level 4
An instance of TLA level 4

- Shall follow requirements of all TLA level 1-3
- Shall implement statements using the &quot;organized&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;prioritized&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;curated&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;projected&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;recommended&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;planned&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;deselected&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;requested&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;approved&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;augmented&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;explored&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;clarified&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;directed&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;scheduled&quot; verb with all requirements fulfilled.

<a name="Level5"></a>
## TLA conformance level 5
An instance of TLA level 5

- Shall follow requirements of all TLA level 1-4
- Shall implement statements using the &quot;recruited&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;appraised&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;detailed&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;mobilized&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;employed&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;schooled&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;promoted&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;screened&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;selected&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;transitioned&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;released&quot; verb with all requirements fulfilled.
- Shall implement statements using the &quot;restricted&quot; verb with all requirements fulfilled.

<a name="TLA-xAPI"></a>
# TLA xAPI JSON-binding definition
A TLA solution is &quot;learner-centric&quot;. This means all learner activity should be retrievable from any LRS (e.g. even those with minimally conformant behavior) through querying mechanism in the xAPI standard. This standard describes the reporting portion of a TLA solution, which decentralizing state management within the systems. Most of this management is done through use of xAPI statements. Any TLA data reporting that is not xAPI is beyond the scope of this specification. 5.1-5.3 describe the data requirements of xAPI statements within the TLA. A comprehensive description of use of TLA data can be found in Annex E.

<a name="Statement-data-requirements"></a>
## Statement data requirements
This section describes requirements for xAPI statements within the TLA. An xAPI statement has an actor, verb, and object, and other properties. A statement is from an authoritative source if and only if the authority property is traceable back to the statement provider.

- xAPI statements shall be conformant to the xAPI Standard
- xAPI statements using verbs in this document shall implement properties as described (see Note below) in the templates in 5.1.1-5.1.49
- xAPI statements using verbs in this document may implement properties that are not represented in the templates in 5.1.1-5.1.49
- xAPI statements shall be constructed such that the learner is represented by the actor, object, a specific context extension as represented by the templates in 5.1..1-5.1.49
- The actor in any xAPI statement shall be of objectType &quot;Agent&quot;
- The actor in any xAPI statement shall contain an &quot;account, even if the actor is not the learner&quot;

Each verb in an xAPI statement determines which template to follow, corresponding to a specific piece of learning evidence that is tracked. The naming convention of these verbs indicates an active model, where the actor is the &quot;doer&quot; of the verb. The learner is an integral part of every xAPI statement. When an xAPI statement is sent directly as a result of the learner&#39;s action, such as a user requesting to take a course, the actor of that statement is the learner. When something is happening to the learner as a result of another actor (instructor, system, etc.) the learner is represented in a context extension, such that the activity may remain in the object portion of the statement. The rationale for this design is to minimize the number of necessary extensions within this profile, instead relying on Activity types that the LRS can keep definitions of more easily. All other necessary requirements for xAPIs statement properties, in addition to those in the xAPI Standard, are listed in the xAPI Profile templates listed in 5.1.1-5.1.49. Among these properties are objects with type &quot;activity&quot;, which often represent the learning construct of the statement. More information about each type of object can be found in Annex D.

**Note:** Any property listed in a template with a specific value (including booleans) shall retain that value in a statement created that follows the template. In properties where there is not a specific value, these templates contain in capital letters requirements that shall be followed. These requirements are not &quot;shall&quot;, &quot;should&quot;, or &quot;shall not&quot;, but should be translated as such. The use of &quot;RECOMMENDED&quot; in the template indicates a &quot;should&quot; requirement. The use of &quot;EXCLUDED&quot; in the template indicates a &quot;shall not&quot; requirement. The use of &quot;REQUIRED&quot; in the template indicates a &quot;shall&quot; requirement. These requirements may be accompanied by explanatory text and/or other requirements on the data. Use of brackets indicates a choice of one or more of the elements within the bracket.

<a name="Waived"></a>
### Waived
>**Verb:**
>>**id:** "https://w3id.org/xapi/adl/verbs/waived", \
>>**display:** "waived",\
>>**definition:** "Indicates that the learning activity requirements were met by means other than completing the activity. A waived statement is used to indicate that the activity may be skipped by the actor."
>
>**Object:**
>>**id:** "",\
>>**objectType:** Activity\
>>**definition:**
>>>**type:**
>>>>["https://w3id.org/xapi/tla/activity-types/activity", \
>>>>"https://w3id.org/xapi/tla/activity-types/assessment", \
>>>>"https://w3id.org/xapi/tla/activity-types/competency"]

<a name="Launched"></a>
### Launched
>**Verb:**
>>**id:** "https://adlnet.gov/expapi/verbs/launched", \
>>**display:** "launched", \
>>**definition:** "Indicates the user started a service. This does not always need to be a specific activity but can be a service provider as well."
>
>**Object:**
>>**id:** "",\
>>**objectType:** Activity\
>>**definition:**
>>>**type:**
>>>>["https://w3id.org/xapi/tla/activity-types/activity", \
>>>>"https://w3id.org/xapi/tla/activity-types/assessment", \
>>>>"https://w3id.org/xapi/tla/activity-types/competency"]
>
>**Context:**
>>**Context Activities:** EXCLUDED

<a name="Completed"></a>
### Completed
>**Verb:**
>>**id:** "https://adlnet.gov/expapi/verbs/completed", \
>>**display:** "completed",\
>>**definition:** "Indicates the actor finished or concluded the activity normally"
>
>**Object:**
>>**id:** "",\
>>**objectType:** Activity\
>>**definition:**
>>>**type:**
>>>>["https://w3id.org/xapi/tla/activity-types/activity",\
>>>>"https://w3id.org/xapi/tla/activity-types/assessment"]
>
>**Result:**
>>**Success:** RECOMMENDED\
>>**Duration:** RECOMMENDED

<a name="Passed"></a>
### Passed
>**Verb:**
>>**id:** "https://adlnet.gov/expapi/verbs/passed", \
>>**display:** "passed",\
>>**definition:** "Indicates the actor completed an activity to standard"
>
>**Object:**
>>**id:** "",\
>>**objectType:** Activity\
>>**definition:**
>>>**type:** "https://w3id.org/xapi/tla/activity-types/assessment"
>
>**Result:**
>>**Score:**:
>>>**Scaled:**: RECOMMENDED\
>>>**Success:** TRUE\
>>>**Completion:** TRUE

<a name="Failed"></a>
### Failed
>**Verb:**
>>**id:** "https://adlnet.gov/expapi/verbs/failed", \
>>**display:** "failed",\
>>**definition:** "Indicates the actor did not complete an activity to standard"
>
>**Object:**
>>**id:** "",\
>>**objectType:** Activity\
>>**definition:**
>>>**type:** "https://w3id.org/xapi/tla/activity-types/assessment"
>
>**Result:**
>>**Score:**:
>>>**Scaled:**: RECOMMENDED\
>>>**Success:** FALSE\
>>>**Completion:** TRUE

<a name="Satisfied"></a>
### Satisfied
>**Verb:**
>>**id:** "https://w3id.org/xapi/adl/verbs/satisfied", \
>>**display:** "satisfied",\
>>**definition:** "Indicates that the authority or activity provider determined the actor has fulfilled the criteria of the object or activity by means other than completing the activity"
>
>**Object:**
>>**id:** "",\
>>**objectType:** Activity\
>>**definition:**
>>>**type:**
>>>>["https://w3id.org/xapi/tla/activity-types/activity", \
>>>>"https://w3id.org/xapi/tla/activity-types/assessment"]

<a name="Abandoned"></a>
### Abandoned
>**Verb:**
>>**id:** "https://w3id.org/xapi/adl/verbs/abandoned", \
>>**display:** "abandoned",\
>>**definition:** "Indicates that the AU session was abnormally terminated by a learner's action (or due to a system failure)"
>
>**Object:**
>>**id:** "",\
>>**objectType:** Activity\
>>**definition:**
>>>**type:**
>>>>["https://w3id.org/xapi/tla/activity-types/activity",\
>>>>"https://w3id.org/xapi/tla/activity-types/assessment"]
>
>**Result:**
>>**Duration:** RECOMMENDED
>>>_The duration property should, at a minimum, be set as the total session time, calculated as the time between the "launched" statement and the last statement (of any kind) issued by the exercise. Implementers should also use other (software specific) methods (if available) to determine if the total session time was longer._
>>
>>**Completion:** FALSE

<a name="Terminated"></a>
### Terminated
>**Verb:**
>>**id:** "https://adlnet.gov/expapi/verbs/terminated", \
>>**display:** "terminated",\
>>**definition:** "Indicates the actor has completed their session normally"
>
>**Object:**
>>**id:** "",\
>>**objectType:** Activity\
>>**definition:**
>>>**type:**
>>>>["https://w3id.org/xapi/tla/activity-types/activity",\
>>>>"https://w3id.org/xapi/tla/activity-types/assessment"]
>
>**Result:**
>>**Duration:** RECOMMENDED
>>>_The duration property should, at a minimum, be set as the total session time, calculated as the time between the &#39;launched&#39; statement and the last statement (of any kind) issued by the exercise. Implementers should also use other (software specific) methods (if available) to determine if the total session time was longer._
>>
>>**Completion:** FALSE

<a name="Initialized"></a>
### Initialized
>**Verb:**
>>**id:** "https://adlnet.gov/expapi/verbs/initialized", \
>>**display:** "initialized",\
>>**definition:** "Indicates that the activity was started."
>
>**Object:**
>>**id:** "",\
>>**objectType:** Activity\
>>**definition:**
>>>**type:**
>>>>["https://w3id.org/xapi/tla/activity-types/activity",\
>>>>"https://w3id.org/xapi/tla/activity-types/assessment"]
>
>**Result:** EXCLUDED

<a name="Recommended"></a>
### Recommended
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/recommended", \
>>**display:** "recommended",\
>>**definition:** "Indicates the learner was given the recommendation to follow a career path, work towards a learning objective, or perform a learning activity by the actor"
>
>**Object:**
>>**id:** "",\
>>**objectType:** INCLUDED\
>>**definition:**
>>>**type:**
>>>>["https://w3id.org/xapi/tla/activity-types/activity_cluster",\
>>>>"https://w3id.org/xapi/tla/activity-types/competency",\
>>>>"https://w3id.org/xapi/tla/activity-types/assessment",\
>>>>"https://w3id.org/xapi/tla/activity-types/activity",\
>>>>"https://w3id.org/xapi/tla/activity-types/career",\
>>>>"https://w3id.org/xapi/tla/activity-types/badge",\
>>>>"https://w3id.org/xapi/tla/activity-types/job"]
>
>**Result:** EXCLUDED
>
>**Context:**
>>**Extensions:**
>>>"https://w3id.org/xapi/tla/extensions/learner": INCLUDED
>>>>_shall be the learner to whom this data applies to_

<a name="Prioritized"></a>
### Prioritized
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/prioritized", \
>>**display:** "prioritized",\
>>**definition:** "Indicates the actor filtered goals associated with select content, usually listing what competencies are demonstrated in recently viewed content"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:**
>>>>["https://w3id.org/xapi/tla/activity-types/competency",\
>>>>"https://w3id.org/xapi/tla/activity-types/career",\
>>>>"https://w3id.org/xapi/tla/activity-types/badge",\
>>>>"https://w3id.org/xapi/tla/activity-types/job"]
>
>**Result:** EXCLUDED
>>**Context:**
>>>**Extensions:**
>>>>"https://w3id.org/xapi/tla/extensions/evidence": INCLUDED
>>>>>_This will be an array of the activities that were used in the query_

<a name="Organized"></a>
### Organized
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/organized", \
>>**display:** "organized",\
>>**definition:** "Indicates the actor filtered content that aligns to specific goal"
>
>**Object:**
>>**id:** "",\
>>**objectType:** INCLUDED\
>>**definition:**
>>>**type:**
>>>>["https://w3id.org/xapi/tla/activity-types/activity_cluster",\
>>>>"https://w3id.org/xapi/tla/activity-types/assessment",\
>>>>"https://w3id.org/xapi/tla/activity-types/activity"]
>
>**Result:** EXCLUDED
>>**Context:**
>>>**Extensions:**
>>>>"https://w3id.org/xapi/tla/extensions/evidence": INCLUDED
>>>>>_This will be an array of the viewed/completed Competencies_

<a name="Projected"></a>
### Projected
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/projected", \
>>**display:** "projected",\
>>**definition:** "Indicates the actor was presented a list of goal recommendations over time, based on selected goal with recursive depth, what set of content can achieve mastery in the ordered sub-goals"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:** RECOMMENDED
>
>**Result:**
>>**Extensions:**
>>>"https://w3id.org/xapi/tla/extensions/recommendation_order": INCLUDED
>>>>_This is an array of just activity recommendations statement references, in the order they were provided_

<a name="Planned"></a>
### Planned
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/planned", \
>>**display:** "planned",\
>>**definition:** "Indicates that the actor assigned themselves a new learning goal, without needing approval"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:**
>>>>["https://w3id.org/xapi/tla/activity-types/competency",\
>>>>"https://w3id.org/xapi/tla/activity-types/career",\
>>>>"https://w3id.org/xapi/tla/activity-types/badge",\
>>>>"https://w3id.org/xapi/tla/activity-types/job"]
>
>**Result:** EXCLUDED

<a name="Deselected"></a>
### Deselected
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/deselected", \
>>**display:** "deselected",\
>>**definition:** "Indicates the actor removed specific goal or task"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:**
>>>>["https://w3id.org/xapi/tla/activity-types/career",\
>>>>"https://w3id.org/xapi/tla/activity-types/badge",\
>>>>"https://w3id.org/xapi/tla/activity-types/credential",\
>>>>"https://w3id.org/xapi/tla/activity-types/job_duty_gig",\
>>>>"https://w3id.org/xapi/tla/activity-types/competency",\
>>>>"https://w3id.org/xapi/tla/activity-types/activity"]
>
>**Extensions:**
>>"https://w3id.org/xapi/tla/extensions/instance": recommended
>>>_shall be a pointer to the instance of the goal within the learner profile_

<a name="Requested"></a>
### Requested
>**Verb:**
>>**id:** "https://w3id.org/xapi/adb/verbs/requested", \
>>**display:** "requested",\
>>**definition:** "Indicates the actor needed or demanded an object or another actor. Requested indicates a comment that is shared with peers as a group or Coach as a trainer. The request for coaching or help prompts users to respond giving them coaching credit"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:**
>>>>["https://w3id.org/xapi/tla/activity-types/activity_cluster",\
>>>>"https://w3id.org/xapi/tla/activity-types/assessment",\
>>>>"https://w3id.org/xapi/tla/activity-types/activity"]
>
>**Result:** EXCLUDED

<a name="Approved"></a>
### Approved
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/approved", \
>>**display:** "approved",\
>>**definition:** "Indicates an OICS approved a requested activity for the given learner"
>
>**Object:**
>>**id:** "",
>>>_SHOULD be ID of "Requested" Statement being approved_
>>
>>**definition:**
>>>**type:**
>>>>["https://w3id.org/xapi/tla/activity-types/activity_cluster",\
>>>>"https://w3id.org/xapi/tla/activity-types/assessment",\
>>>>"https://w3id.org/xapi/tla/activity-types/activity"]
>
>**Result:** EXCLUDED
>
>**Context:**
>>**Extensions:**
>>>"https://w3id.org/xapi/tla/extensions/learner": INCLUDED
>>>>_shall be the learner to whom this data applies to_

<a name="Augmented"></a>
### Augmented
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/augmented", \
>>**display:** "augmented",\
>>**definition:** "Indicates the actor searched content on an active learning goal, viewing what other goals/branches can be related based on an active goal tree"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:**
>>>>["https://w3id.org/xapi/tla/activity-types/activity_cluster",\
>>>>"https://w3id.org/xapi/tla/activity-types/assessment",\
>>>>"https://w3id.org/xapi/tla/activity-types/activity"]
>
>**Result:** Excluded
>
>**Context:**
>>**Extensions:**
>>>"https://w3id.org/xapi/tla/extensions/evidence:: INCLUDED
>>>>_should be a resolvable identifier to the learning goal(s) used for this augmented event, but is open-ended to allow future mechanisms_

<a name="Explored"></a>
### Explored
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/explored", \
>>**display:** "explored",\
>>**definition:** "Indicates the actor searched active learning goals related to specific content, viewing what other content may trigger related goals, based on active goal and recently completed content"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:**
>>>>["https://w3id.org/xapi/tla/activity-types/competency",\
>>>>"https://w3id.org/xapi/tla/activity-types/career",\
>>>>"https://w3id.org/xapi/tla/activity-types/badge",\
>>>>"https://w3id.org/xapi/tla/activity-types/job"]
>
>**Result:** EXCLUDED
>>**Context:**
>>>**Extensions:**
>>>>"https://w3id.org/xapi/tla/extensions/evidence": INCLUDED
>>>>>_should be a resolvable identifier to the learning goal(s) used for this explored event, but is open-ended to allow future mechanisms_

<a name="Clarified"></a>
### Clarified
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/clarified", \
>>**display:** "clarified",\
>>**definition:** "Indicates the actor queried what other content may also reinforce the current learning goal, after completing content"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:**
>>>>["https://w3id.org/xapi/tla/activity-types/competency",\
>>>>"https://w3id.org/xapi/tla/activity-types/career",\
>>>>"https://w3id.org/xapi/tla/activity-types/badge",\
>>>>"https://w3id.org/xapi/tla/activity-types/job"]
>
>**Result:** EXCLUDED
>
>**Context:**
>>**Extensions:**
>>>"https://w3id.org/xapi/tla/extensions/evidence": INCLUDED
>>>>_should be a resolvable identifier to the content and goal(s) used for this clarified event, but is open-ended to allow future mechanisms_

<a name="Directed"></a>
### Directed
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/directed", \
>>**display:** "directed",\
>>**definition:** "Indicates the actor was assigned a learning goal by another party"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:**
>>>>["https://w3id.org/xapi/tla/activity-types/competency",\
>>>>"https://w3id.org/xapi/tla/activity-types/career",\
>>>>"https://w3id.org/xapi/tla/activity-types/badge",\
>>>>"https://w3id.org/xapi/tla/activity-types/job"]
>
>**Result:** Excluded
>
>**Context:**
>>**Extensions:**
>>>"https://w3id.org/xapi/tla/extensions/learner": INCLUDED
>>>>_shall be the learner to whom this data applies to_

<a name="Scheduled"></a>
### Scheduled
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/scheduled", \
>>**display:** "scheduled",\
>>**definition:** "Indicates the actor scheduled an activity or lesson"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:**
>>>>["https://w3id.org/xapi/tla/activity-types/activity_cluster",\
>>>>"https://w3id.org/xapi/tla/activity-types/assessment",\
>>>>"https://w3id.org/xapi/tla/activity-types/activity"]
>
>**Result:** Excluded
>
>**Context:**
>>**Extensions:**
>>>"https://w3id.org/xapi/tla/extensions/due_date": RECOMMENDED <sup>[[8]](#foot-8)</sup>
>>>>_shall be the date the object has to be completed_
>>>
>>>"https://w3id.org/xapi/tla/extensions/learner": INCLUDED
>>>>_shall be the learner to whom this data applies to_

<a name="Assessed"></a>
### Assessed
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/assessed", \
>>**display:** "assessed",\
>>**definition:** "Indicates the actor completed assessments in a way that will cause a change in their authoritative learner state"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:** "https://w3id.org/xapi/tla/activity-types/competency"
>
>**Result:**
>>**Duration:** RECOMMENDED\
>>**Completion:** EXCLUDED\
>>**Score:**:
>>>**Scaled:**: RECOMMENDED\
>>>>**Success:** INCLUDED
>
>**Context:**
>>**Extensions:**
>>>"https://w3id.org/xapi/tla/extensions/evidence": INCLUDED
>>>>_shall be a resolvable identifier to the xAPI statement(s) that resulted in this statement_
>>>
>>>"https://w3id.org/xapi/tla/extensions/confidence": INCLUDED
>>>>_shall be a number between -1 and 1 displaying how likely the learner is to have mastered the assessed competency, -1 being sure they have not, and 1 being certain they have_

<a name="Contextualized"></a>
### Contextualized
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/contextualized", \
>>**display:** "contextualized",\
>>**definition:** "Indicates the user performed several connected learning activities that should result in a change in their authoritative learner state"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:** https://w3id.org/xapi/tla/activity-types/competency
>
>**Context:**
>>**Extensions:**
>>>"https://w3id.org/xapi/tla/extensions/evidence": INCLUDED,
>>>>_shall be a resolvable identifier to the xAPI statement(s) that resulted in this statement_
>>>
>>>"https://w3id.org/xapi/tla/extensions/confidence": INCLUDED
>>>>_shall be a number between -1 and 1 displaying how likely the learner is to have mastered the assessed competency, -1 being sure they have not, and 1 being certain they have_

<a name="Located"></a>
### Located
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/located", \
>>**display:** "located",\
>>**definition:** "Indicates the actor&#39;s competency state needs to be updated based on completed content changes in the Competency Framework"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:** "https://w3id.org/xapi/tla/activity-types/competency"
>
>**Result:** EXCLUDED
>
>**Context:**
>>**Extensions:**
>>>"https://w3id.org/xapi/tla/extensions/evidence": INCLUDED
>>>>_shall be a resolvable identifier to the xAPI statement(s) that resulted in this statement_
>>>
>>>"https://w3id.org/xapi/tla/extensions/confidence": INCLUDED
>>>>_shall be a number between -1 and 1 displaying how likely the learner is to have mastered the located competency, -1 being sure they have not, and 1 being certain they have_

<a name="Asserted"></a>
### Asserted
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/asserted", \
>>**display:** "asserted",\
>>**definition:** "Indicates the learner has provided sufficient evidence to update the learner&#39;s measure of competence in a given competency"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:** https://w3id.org/xapi/tla/activity-types/competency
>
>**Result:** EXCLUDED
>
>**Context:**
>>**Extensions:**
>>>"https://w3id.org/xapi/tla/extensions/evidence": INCLUDED
>>>>_shall be the id of the xAPI statement(s) that resulted in this statement_
>>>
>>>"https://w3id.org/xapi/tla/extensions/confidence": INCLUDED
>>>>_shall be a number between -1 and 1 displaying how likely the learner is to have mastered the competency, -1 being sure they have not, and 1 being certain they have_

<a name="Validated"></a>
### Validated
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/validated", \
>>**display:** "validated",\
>>**definition:** "Indicates an OICS approved a change to a competency framework within the TLA that will affect the learners&#39; states"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:** https://w3id.org/xapi/tla/activity-types/competency
>
>**Result:** EXCLUDED
>
>**Context:**
>>**Extensions:**
>>>"https://w3id.org/xapi/tla/extensions/learner": INCLUDED,
>>>>_shall be the learner to whom this data applies to_
>>>
>>>"https://w3id.org/xapi/tla/extensions/evidence": INCLUDED,
>>>>_shall be a resolvable identifier to the xAPI asserted statement was just validated_
>>>
>>>"https://w3id.org/xapi/tla/extensions/confidence": INCLUDED
>>>>_shall be a number between -1 and 1 displaying how likely the learner is to have mastered the competency, -1 being sure they have not, and 1 being certain they have_

<a name="Inferred"></a>
### Inferred
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/inferred", \
>>**display:** "inferred",\
>>**definition:** "Indicates an authoritative source changed a learner&#39;s competency assertions based on a valid competency framework change"
>
>**Object:** 
>>**id:** "",\
>>**definition:**
>>>**type:** https://w3id.org/xapi/tla/activity-types/competency
>
>**Result:** EXCLUDED
>
>**Context:**
>>**Extensions:**
>>>"https://w3id.org/xapi/tla/extensions/learner": INCLUDED
>>>>_shall be the learner to whom this data applies to_
>>>
>>>"https://w3id.org/xapi/tla/extensions/evidence": INCLUDED
>>>>_shall be a resolvable identifier to the xAPI statement(s) that resulted in this statement_
>>>
>>>"https://w3id.org/xapi/tla/extensions/confidence": INCLUDED
>>>>_shall be a number between -1 and 1 displaying how likely the learner is to have mastered the competency, -1 being sure they have not, and 1 being certain they have_

<a name="Qualified"></a>
### Qualified
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/qualified", \
>>**display:** "qualified",\
>>**definition:** "Indicates the learner meets all the requirements for a badge, but hasn&#39;t been awarded the badge yet"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:** https://w3id.org/xapi/tla/activity-types/badge
>
>**Result:** EXCLUDED
>
>**Context:**
>>**Extensions:**
>>>"https://w3id.org/xapi/tla/extensions/evidence": INCLUDED
>>>>_shall be a resolvable identifier to the xAPI statement(s) that resulted in this statement_

<a name="Certified"></a>
### Certified
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/certified", \
>>**display:** "certified", \
>>**definition:** "Indicates the learner received an accreditation by an authoritative source to perform a given job or task"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:** "https://w3id.org/xapi/tla/activity-types/job"
>
>**Result:** EXCLUDED
>
>**Context:**
>>**Extensions:**
>>>"https://w3id.org/xapi/tla/extensions/evidence": INCLUDED
>>>>_shall be a resolvable identifier to the xAPI statement(s) that resulted in this statement_

<a name="Verified"></a>
### Verified
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/verified", \
>>**display:** "verified",\
>>**definition:** "Indicates the authoritative source verified evidence of learning from a non-authoritative source as reliable data"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:** "https://w3id.org/xapi/tla/activity-types/competency"
>
>**Result:** EXCLUDED
>
>**Context:**
>>**Extensions:**
>>>"https://w3id.org/xapi/tla/extensions/evidence": INCLUDED
>>>>_shall be a resolvable identifier to the xAPI statement(s) that resulted in this statement_
>>>
>>>"https://w3id.org/xapi/tla/extensions/confidence": INCLUDED
>>>>_shall be a number between -1 and 1 displaying how likely the learner is to have mastered the competency, -1 being sure they have not, and 1 being certain they have_
>>>
>>>"https://w3id.org/xapi/tla/extensions/learner": INCLUDED
>>>>_shall be the learner to whom this data applies to_

<a name="Conferred"></a>
### Conferred
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/conferred", \
>>**display:** "conferred",\
>>**definition:** "Indicates the OICS conferred a badge to the learner in the learner context extension"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:** "https://w3id.org/xapi/tla/activity-types/badge"
>
>**Result:** EXCLUDED
>
>**Context:**
>>**Extensions:**
>>>"https://w3id.org/xapi/tla/extensions/evidence": INCLUDED,
>>>>_shall be a resolvable identifier to the xAPI statement(s) that resulted in this statement_
>>>
>>>"https://w3id.org/xapi/tla/extensions/confidence": INCLUDED,
>>>>_shall be a number between -1 and 1 displaying how likely the learner is to have mastered the competency, -1 being sure they have not, and 1 being certain they have_
>>>
>>>"https://w3id.org/xapi/tla/extensions/learner": INCLUDED
>>>>_shall be the learner to whom this statement applies to_

<a name="Recruited"></a>
### Recruited
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/recruited", \
>>**display:** "recruited",\
>>**definition:** "Indicates the actor recruited the learner to join the ecosystem"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:** "https://w3id.org/xapi/tla/activity-types/career"
>
>**Result:** EXCLUDED
>
>**Context:**
>>**Extensions:**
>>>"https://w3id.org/xapi/tla/extensions/learner": INCLUDED
>>>>_shall be the learner to whom this data applies to_

<a name="Appraised"></a>
### Appraised
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/appraised", \
>>**display:** "appraised",\
>>**definition:** "OICS indicates the learner met entry criteria for jobs and assigned a career trajectory"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:** "https://w3id.org/xapi/tla/activity-types/career"
>
>**Result:** EXCLUDED

<a name="Detailed"></a>
### Detailed
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/detailed", \
>>**display:** "detailed",\
>>**definition:** "OICS detailed the learner to a specific job"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:** https://w3id.org/xapi/tla/activity-types/career
>
>**Result:** EXCLUDED
>
>**Context:**
>>**Extensions:**
>>>"https://w3id.org/xapi/tla/extensions/location": RECOMMENDED,
>>>>_shall be the physical location the learner has been detailed to_
>>>
>>>"https://w3id.org/xapi/tla/extensions/permanent_change_of_station": RECOMMENDED,
>>>>_shall be a boolean marking if this is a PCS or a different detail event_
>>>
>>>"https://w3id.org/xapi/tla/extensions/unit_identification_code": RECOMMENDED,
>>>>_shall be a unique code for the learner's unit_
>>>
>>>"https://w3id.org/xapi/tla/extensions/learner": INCLUDED
>>>>_shall be the learner to whom this data applies to_

<a name="Mobilized"></a>
### Mobilized
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/mobilized", \
>>**display:** "mobilized",
>>**definition:** "OICS mobilized the learner to a state of on duty"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>   type: "https://w3id.org/xapi/tla/activity-types/career_state"
>
>**Result:** EXCLUDED
>
>**Context:**
>>**Extensions:**
>>>"https://w3id.org/xapi/tla/extensions/location": RECOMMENDED,
>>>>_shall be the physical location the learner has been mobilized to_
>>>
>>>"https://w3id.org/xapi/tla/extensions/unit_identification_code": RECOMMENDED,
>>>>_shall be a unique code for the learner&#39;s unit_
>>>
>>>"https://w3id.org/xapi/tla/extensions/learner": INCLUDED
>>>>_shall be the learner to whom this data applies to_

<a name="Employed"></a>
### Employed
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/employed", \
>>**display:** "employed",\
>>**definition:** "OICS employs the actor such that they started work doing their job"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:** "https://w3id.org/xapi/tla/activity-types/career_state"
>
>**Result:** EXCLUDED
>
>**Context:**
>>**Extensions:**
>>>"https://w3id.org/xapi/tla/extensions/location": RECOMMENDED,
>>>>_shall be The physical location the learner has been employed at_
>>>
>>>"https://w3id.org/xapi/tla/extensions/unit_identification_code": RECOMMENDED,
>>>>_shall be a unique code for the learner&#39;s unit_
>>>
>>>"https://w3id.org/xapi/tla/extensions/learner": INCLUDED
>>>>_shall be the learner to whom this data applies to_

<a name="Schooled"></a>
### Schooled
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/schooled", \
>>**display:** "schooled",\
>>**definition:** "OICS has enrolled the learner in a schooling system"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:**
>>>>["https://w3id.org/xapi/tla/activity-types/competency", \
>>>>"https://w3id.org/xapi/tla/activity-types/career", \
>>>>"https://w3id.org/xapi/tla/activity-types/badge", \
>>>>"https://w3id.org/xapi/tla/activity-types/job"]
>
>**Result:** EXCLUDED
>
>**Context:**
>>**Extensions:**
>>>"https://w3id.org/xapi/tla/extensions/location": RECOMMENDED,
>>>>_shall be the physical location the learner has been employed at_
>>>
>>>"https://w3id.org/xapi/tla/extensions/unit_identification_code": RECOMMENDED,
>>>>_shall be a unique code for the learner&#39;s unit_
>>>
>>>"https://w3id.org/xapi/tla/extensions/learner": INCLUDED
>>>>_shall be the learner to whom this data applies to_

<a name="Promoted"></a>
### Promoted
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/promoted", \
>>**display:** "promoted",\
>>**definition:** "OICS has changed a learner&#39;s rank, either up or down"
>
>**Object:**
>>**id:** "",
>>**definition:**
>>>**type:** "https://w3id.org/xapi/tla/activity-types/rank"
>
>**Result:** EXCLUDED
>
>**Context:**
>>**Extensions:**
>>>"https://w3id.org/xapi/tla/extensions/learner": INCLUDED
>>>>_shall be the learner to whom this data applies to_

<a name="Screened"></a>
### Screened
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/screened", \
>>**display:** "screened",\
>>**definition:** "OICS screened learner for a potentially narrower career trajectory, and passed through a "gate" within their career trajectory"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:** "https://w3id.org/xapi/tla/activity-types/career"
>
>**Result:** EXCLUDED
>
>**Context:**
>>**Extensions:**
>>>"https://w3id.org/xapi/tla/extensions/evidence": RECOMMENDED,
>>>>_The reason the learner screened for a career path should be a resolvable identifier to xAPI data_
>>>
>>>"https://w3id.org/xapi/tla/extensions/epiration": RECOMMENDED,
>>>>_shall be a timestamp of the time the screening expires_
>>>
>>>"https://w3id.org/xapi/tla/extensions/learner": INCLUDED
>>>>_shall be the learner to whom this data applies to_

<a name="Selected"></a>
### Selected
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/selected", \
>>**display:** "selected",\
>>**definition:** "OICS selected learner based on criteria for a potentially wider career trajectory, opening up new career possibilities"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:** https://w3id.org/xapi/tla/activity-types/career
>
>**Result:** EXCLUDED
>
>**Context:**
>>**Extensions:**
>>>"https://w3id.org/xapi/tla/extensions/evidence": RECOMMENDED,
>>>>_The reason the learner was selected for a career path should be a resolvable identifier to xAPI data_
>>>
>>>"https://w3id.org/xapi/tla/extensions/epiration": RECOMMENDED,
>>>>_shall be a timestamp of the time the screening expires_
>>>
>>>"https://w3id.org/xapi/tla/extensions/learner": INCLUDED
>>>>_shall be the learner to whom this data applies to_

<a name="Transitioned"></a>
### Transitioned
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/transitioned", \
>>**display:** "transitioned",\
>>**definition:** "Indicates the actor changed career paths, putting them on a completely different and brand new career trajectory"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:** "https://w3id.org/xapi/tla/activity-types/career_state"
>
>**Result:** EXCLUDED

<a name="Released"></a>
### Released
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/released", \
>>**display:** "released",\ 
>>**definition:** "Indicates OICS released the learner from the learning environment"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:** "https://w3id.org/xapi/tla/activity-types/career_state"
>
>**Result:** EXCLUDED
>
>**Context:**
>>**Extensions:**
>>>"https://w3id.org/xapi/tla/extensions/reason": INCLUDED,
>>>>_shall be text/String that describes the reason the learner has left the learning environment_ 
>>>
>>>"https://w3id.org/xapi/tla/extensions/learner": INCLUDED
>>>>_shall be the learner to whom this data applies to_

<a name="Restricted"></a>
### Restricted
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/restricted", \
>>**display:** "restricted",\
>>**definition:** "Indicates OICS temporarily restricted the learner from some (possibly all) participation within the learning environment"
>
>**Object:**
>>**id:** "",\
>>**definition:**
>>>**type:** https://w3id.org/xapi/tla/activity-types/career_state
>
>**Result:** EXCLUDED
>
>**Context:**
>>**Extensions:**
>>>"https://w3id.org/xapi/tla/extensions/restriction": INCLUDED,
>>>>_shall be text/String that describes the reason the learner has been restricted_
>>>
>>>"https://w3id.org/xapi/tla/extensions/reason": INCLUDED,
>>>>_shall be the timestamp corresponding to when the restriction is lifted. May be NULL(e.g. if the restriction will not expire)_
>>>
>>>"https://w3id.org/xapi/tla/extensions/learner": INCLUDED
>>>>_shall be the learner to whom this data applies to_A

<a name="Voided"></a>
### Voided
>**Verb:**
>>**id:** "http://adlnet.gov/expapi/verbs/voided", \
>>**display:** "voided",\
>>**definition:** "Indicates that the actor has done something to void a previous event"
>
>**Object:**
>>**id:** "",\
>>**objectType:** "StatementRef"
>>>_shall be the statement that is being voided_
>
>**Result:** EXCLUDED

<a name="attended"></a>
### Attended
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/attended", \
>>**display:** "attended",\
>>**definition:** "Indicates that the actor is present at a virtual or physical event or activity"
>
>**Object:**
>>**id:** "",\
>>**definition:** 
>>>**type:** "https://w3id.org/xapi/tla/activity-types/activity", \
>>>**extensions:** "https://w3id.org/xapi/tla/extensions/instance" 
>>>>_This should be a pointer to the an actual session definition_
>
>**Result:**
>>**duration:** RECOMMENDED

<a name="experienced"></a>
### Experienced
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/experienced", \
>>**display:** "experienced",\
>>**definition:** "Indicates the actor encountered a learning situation where a specific achievement or completion is not applicable"
>
>**Object:**
>>**id:** "",\
>>**definition:** 
>>>**type:** 
>>>>["https://w3id.org/xapi/tla/activity-types/activity", \
>>>>"https://w3id.org/xapi/tla/activity-types/assessment"], 
>>>
>>>**extensions:** "https://w3id.org/xapi/tla/extensions/instance"
>>>>_This should be a pointer to the an actual session definition_ 
>
>**Result:**
>>**duration:** RECOMMENDED

<a name="mastered"></a>
### Mastered
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/mastered", \
>>**display:** "mastered",\
>>**definition:** "Indicates the actor has achieved the highest level of comprehension or competency"
>
>**Object:**
>>**id:** "",\
>>**definition:** ""
>>>**type:** 
>>>>["https://w3id.org/xapi/tla/activity-types/credential", \
>>>>"https://w3id.org/xapi/tla/activity-types/job_duty_gig"] 
>
>**Result:**
>>**duration:** EXCLUDED

<a name="resumed"></a>
### Resumed
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/resumed", \
>>**display:** "resumed",\
>>**definition:** "Indicates the actor has continued or reopened a suspended learning activity"
>
>**Object:**
>>**id:** "",\
>>**definition:** ""
>>>**type:** 
>>>>["https://w3id.org/xapi/tla/activity-types/activity", \
>>>>"https://w3id.org/xapi/tla/activity-types/assessment"] 
>
>**Result:**
>>**duration:** EXCLUDED

<a name="scored"></a>
### Scored
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/scored", \
>>**display:** "scored",\
>>**definition:** "Indicates the actor has been given a score on an assement after completion"
>
>**Object:**
>>**id:** "",\
>>**definition:** ""
>>>**type:** 
>>>>["https://w3id.org/xapi/tla/activity-types/activity", \
>>>>"https://w3id.org/xapi/tla/activity-types/assessment"] 
>
>**Result:**
>>**duration:** RECOMMENDED \
>>**score:** INCLUDED

<a name="suspended"></a>
### Suspended
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/suspended", \
>>**display:** "suspended",\
>>**definition:** "Indicates that the actor has temporarily halted an activity and will resume at a later time"
>
>**Object:**
>>**id:** "",\
>>**definition:** ""
>>>**type:** 
>>>>["https://w3id.org/xapi/tla/activity-types/activity", \
>>>>"https://w3id.org/xapi/tla/activity-types/assessment"] 
>
>**Result:**
>>**duration:** RECOMMENDED
>>> _This should be the amount of time spent in the activity before suspending_ \
>>**score:** EXCLUDED

<a name="registered"></a>
### Registered
>**Verb:**
>>**id:** "https://w3id.org/xapi/tla/verbs/registered", \
>>**display:** "registered",\
>>**definition:** "Indicates that the actor has enrolled in a learning activity"
>
>**Object:**
>>**id:** "",\
>>**definition:** ""
>>>**type:** 
>>>>["https://w3id.org/xapi/tla/activity-types/activity", \
>>>>"https://w3id.org/xapi/tla/activity-types/assessment", \
>>>>"https://w3id.org/xapi/tla/activity-types/job_duty_gig"] 
>
>**Result:**
>>**duration:** EXCLUDED \
>>**score:** EXCLUDED


<a name="LRS-storage-requirements"></a>
## LRS storage requirements

Within a TLA environment, there are different levels of trust and access for different types of LRSs. The level of trust, user roles within those systems, and transfer of data between LRSs are out of scope of this document. Brief definitions of the types of LRSs can be found in the 3.1.

The following requirements exist for all LRSs within a TLA environment:

- All LRSs shall conform to the xAPI Standard
- All LRSs may use the voided verb as found in the xAPI Standard. This requirement super cedes other requirements below.
- Noisy LRSs may allow statements that use any verb
- Transactional LRSs should allow all statements with verbs in 5.1 that authoritative LRSs do not allow
  - Note: depending on the conformance level, recommended practices change. For example, at conformance levels 1 and 2, there is no expected authoritative LRS, so all data is stored in the transactional LRS.
- Transactional LRSs shall not allow statements that use any verb not in 5.1.
- Authoritative LRSs shall not allow statements that use any verb except for the following verbs in 5.1:
  - qualified
  - conferred
  - certified
  - validated
  - inferred
  - asserted
  - verified
  - recruited
  - appraised
  - detailed
  - mobilized
  - employed
  - schooled
  - screened
  - selected
  - promoted
  - transitioned
  - released

- Authoritative LRSs should allow statements that use any verb in the list above.

<a name="TLA-environment-reporting-requirements"></a>
## TLA environment reporting requirements

A TLA compliant learning environment is composed of various functional groups. Each TLA functional group serves a different role with different requirements for reporting data (sending statements to an LRS). The functional groups may exist in any number of configurations of software and hardware, as part of distinct from devices used as &quot;learning activities&quot; to conduct learning . It is for this reason that the following are only recommended practices, as defining what a system is or is not simply by what is reported is not sufficient.

For a description of each of the TLA systems, please refer to Annex E.

Only a competency management system shall send statements with the &quot;certified&quot; verb, unless the TLA environment is level 1 or 2.

<a name="Competency-management-function"></a>
### Competency management function

A level 1 or 2 TLA environment does not have a competency management system; rather other undefined systems shall send the required statements.

A competency management system should send statements with the following verbs, as appropriate, and in accordance with the TLA conformance level as defined in 4.1-4.5:

- located
- assessed
- asserted
- validated
- inferred
- qualified
- verified
- conferred
- certified


A competency management system should not send statements that do not contain the verbs stated in the previous requirement.

An OICS may send statements on behalf of a competency management system.

<a name="Learning-event-management-function"></a>
### Learning event management function

A learning event management system should send statements with the following verbs, as appropriate, and in accordance with the TLA conformance level as defined in 4.1-4.5:

- launched
- waived
- satisfied
- abandoned
- recommended
- organized
- deselected
- requested
- approved
- augmented
- clarified
- directed
- prioritized
- projected
- planned
- explored
- captured

A learning event management system should not send statements that do not contain the verbs stated in the previous requirement. Learning event management may be performed by multiple systems, by manual interfaces, wholly or in part by attached learning devices as activity providers that have some kind of contextual or adaptive features, or any combination thereof. The learning event management function may exist as part of, in conjunction with, or in addition to the mechanism used to catalog representative learning experiences (e.g. an activity index, content catalog, or experience index).

An OICS may send statements on behalf of a learning experience event system.

<a name="Activity-provider-function"></a>
### Activity provider function

Activity providers are the devices that generate the learning records (i.e. LRP) in response to learners conducting learning events. Traditional Learning Management Systems (LMS) serving Shareable Courseware Object Reference Model (SCORM) compliant courseware is an example of an activity provider, although simulators, observation tools, and any number of modern mobile learning devices may also be activity providers. Advanced providers like intelligent tutoring systems may include activity provider functions as well as some learning event management functions.

An activity provider should send statements with the following verbs, as appropriate, and in accordance with the TLA conformance level as defined in 4.1-4.5:

- completed
- passed
- failed
- satisfied
- terminated
- initialized
- attended
- experienced
- scored
- suspended

An activity provider should not send statements that do not contain the verbs stated in the previous requirement.

An OICS may send statements on behalf of an activity provider.

<a name="Human-capital-managementfunction"></a>
### Human capital management function

A human capital management system should send statements with the following verbs, as appropriate, and in accordance with the TLA conformance level as defined in 4.1-4.5:

- launched
- waived
- satisfied
- abandoned
- recommended
- organized
- scheduled
- requested
- approved
- augmented
- clarified
- directed
- resumed
- registered

A human capital management system should not send statements that do not contain the verbs stated in the previous requirement.

An OICS may send statements on behalf of a human capital management system.

<a name="A40"></a>
# Annex A
(informative)

**Bibliography**

[B1] IEEE 100, The Authoritative Dictionary of IEEE Standards Terms.

[B2] IETF RFC 2425:1998, MIME Content-Type for Directory Information.

[B3] ISO 8601:2000, Data Elements and Interchange Formats—Information Interchange—Representation of Dates and Times.

[B4] ISO/IEC 11404:1996, Information Technology—Programming Languages, Their Environments and System Software Interfaces—Language-Independent Datatypes.

[B5] W3C Recommendation (04 February 2004), Extensible Markup Language (XML) 1.1.

[B6] W3C Recommendation (04 February 2004), XML Information Set, Second Edition.

<a name="B41"></a>
# Annex B
(informative)

# Intended use of verbs

A learner-centric view of all verbs. Verbs here may appear to be passive to provide context to the intended effect on the learner but will be proper (active) xAPI statements when implemented. The term experience refers to a combination of learning activities (the electronic device or format that is used to conduct the learning -e.g. a kindle) and content (the file or resource that is experienced, (e.g. an electronic publication)

**TLA Level 1:**
- **Certified:**  Indicates the learner received an accreditation by an authoritative source (OICS) to perform a given job or task.
- **Completed:**  Indicates the learner finished or concluded an experience normally. Should include the success result field.
- **Passed:**  Indicates the learner completed an experience to standard. Used in assessment.
- **Failed:**  Indicates the learner failed to complete an experience to standard. Used in assessment.
- **Initialized:**  Indicates that the learner successfully loaded an experience. This is different from &quot;launched&quot;, as it relates to a specific experience (such as a chapter in a book instead of just opening the book).

**TLA Level 2:**
- **Launched:**  Indicates the learner started a service. This does not always need to be a specific experience but can be a service provider as well.
- **Waived** : Indicates that the learning experience requirements were met by means other than completing the experience. A waived statement is used to indicate that the experience may be skipped by the learner.
- **Satisfied** : Indicates that the authority or experience provider determined the learner has fulfilled the criteria of the object or experience by means other than completing the experience.
- **Abandoned** : Indicates that the AU session was abnormally terminated by a learner&#39;s action (or due to a system failure).
- **Terminated** : Indicates the learner has completed their session normally.
- **Planned** : Indicates that the learner assigned themselves a new learning goal, without needing approval from an OICS.
- **Deselected** : Indicates the actor removed specific goal or task.
- **Requested** : Indicates the learner needed or demanded an object or another OICS or learner. Requested indicates a comment that is shared with peers as a group or a coach as a trainer. The request for coaching or help prompts users to respond giving them coaching credit. Can also include a request to take a class or do a course.
- **Directed** : Indicates the learner was assigned a learning goal by an OICS.
- **Approved** : Indicates an OICS approved for a requested experience for the given learner
- **Attended** : Indicates that the actor is present at a virtual or physical event or activity.
- **Experienced** : Indicates the actor encountered a learning situation where a specific achievement or completion is not applicable.
- **Mastered** : Indicates the actor has achieved the highest level of comprehension or competency.
- **Resumed** : Indicates the actor has continued or reopened a suspended learning activity.
- **Scored** : Indicates the actor has received a numerical value related to their performance within a learning activity.
- **Suspended** : Indicates that the actor has temporarily halted an activity and will resume at a later time.

**TLA Level 3:**
- **Assessed** : Indicates the learner completed assessments in a way that will cause a change in their authoritative learner state.
- **Contextualized** : Indicates the learner performed several connected learning activities that should result in a change in their authoritative learner state.
- **Located** : Indicates the learner&#39;s competency state needs to be updated based on completed experiences and changes in the Competency Framework.
- **Asserted** : Indicates the learner has provided sufficient evidence to update the learner&#39;s measure of competence in a given competency.
- **Validated** : Indicates an OICS approved a change to a competency framework within the TLA that will affect learners&#39; states.
- **Inferred** : Indicates an OICS changed a learner&#39;s competency assertions based on a valid competency framework change.
- **Qualified** : Indicates the learner meets all the requirements for a badge but hasn&#39;t been awarded the badge yet.
- **Conferred** : Indicates the learner was given a badge by an OICS.
- **Verified** : Indicates the learner had evidence of learning from a non-authoritative source verified as reliable data by an authoritative source.
- **Registered** : Indicates that the actor has enrolled in a learning activity.

**TLA Level 4:**
- **Organized** : Indicates the learner filtered experience that aligns to a specific goal.
- **Prioritized** : Indicates the learner filtered goals associated with select experience, usually listing what competencies are demonstrated in recently viewed experience.
- **Projected** : Indicates the learner was presented a list of goal recommendations over time, based on a selected goal with recursive depth, what set of experience can achieve mastery in the ordered sub-goals.
- **Recommended** : Indicates the learner was given the recommendation to follow a career path, work towards a learning objective, or perform a learning experience by the actor.
- **Augmented** : Indicates the learner searched for experiences on an active learning goal, viewing what other goals/branches can be related based on an active goal tree.
- **Explored** : Indicates the learner searched active learning goals related to specific experience, viewing what other experience may trigger related goals, based on active goal and recently completed experience.
- **Clarified** : Indicates the learner queried what other experience may also reinforce the current learning goal, after completing experience.
- **Scheduled** : Indicates the learner scheduled an experience or lesson.

**TLA Level 5:**
- **Recruited** : Indicates an OICS recruited the learner to join the ecosystem.
- **Appraised** : Indicates the learner met entry criteria for jobs and was assigned (by an OICS) a career trajectory.
- **Detailed** : Indicates the learner detailed to a specific job.
- **Mobilized** : Indicates the learner mobilized or deployed (i.e. data will be time late) on duty.
- **Employed** : Indicates OICS employs the learner such that they started work doing their job.
- **Schooled** : Indicates OICS has enrolled the learner in a schooling system.
- **Promoted** : Indicates the OICS has changed a learner&#39;s rank, either up or down.
- **Screened** : Indicates the OICS screened learner as passed through a &quot;gate&quot; within their career trajectory to open up restricted opportunities.
- **Selected** : Indicates the learner met the criteria for a potentially wider career trajectory, opening new career possibilities.
- **Transitioned** : Indicates the learner changed career paths, putting them on a completely different and brand-new career trajectory.
- **Released** :  Indicates OICS released the learner from the learning environment.
- **Restricted** : Indicates OICS temporarily restricted the learner from some (possibly all) participation within the learning environment.

<a name="C44"></a>
# Annex C

(informative)

**Expected data flow for formal and informal learning**

Within TLA enabled systems, there is an expected flow of learner state as depicted in _ **Figure 1** _. The flow may include a deliberate or casual configuration of the learner&#39;s environment. In deliberate learning, the sequence begins with the learner setting goals, planning (or being assigned plans) tasks to achieve these goals, scheduling learning events, and then launching learning exercises. Each is represented by a verb within this specification, and the data generated by learning exercise is then stored in the transactional LRS describing the order and context under which the learner, or the learner&#39;s mentor (OICS) configured their own learning environment. The relationship between the goals, tasks, events, records of completion and conferral chain provides a discoverable audit trail or trusted chain of evidence .

![Mom Data Flow](./Logos/MOM_Data_Flow.png)

**Figure 1: Data Flow for Formal and Informal Learning**

Once the learner completes the exercise, all of the newly generated data is contextualized and a trusted source (OICS or trusted system) takes this new information, and from there generates a trusted record of the learner state using verification, conferral, qualification and assertion statements. All of these statements are stored in an authoritative LRS, that only OICSs and trusted systems have access to.

This standard uses a learner-centric vocabulary, which enables the entire TLA compliant environment to run as a stateless system of systems. This means that the learner could interface with TLA data at any stage in the expected object life cycle, and the services comprising the TLA instance will can execute without knowing previous or follow on learner states. This arrangement not only allows for a true ecosystem, since the origin of the statement doesn&#39;t matter, it is resilient to configuration changes with devices or services being added or subtracted over time.

<a name="D46"></a>
# Annex D
(informative)

**Object types**

Object types, also known as activity types (as the object is usually of type &quot;activity&quot;), as found in the statement templates in 5.1.1-5.1.49, are found within each &quot;object&quot; within an xAPI statement. Activity types are the various types of learning constructs present in the TLA. A summary of each activity type can be found below in Table 1.

**Table 1: Object Types**

| **Name** | **Identifier** | **Definition** |
| --- | --- | --- |
| Activity |[https://w3id.org/xapi/tla/activity-types/activity](https://w3id.org/xapi/tla/activity-types/activity) | Any generic activity an actor can interact with, that is not an assessment |
| Assessment | [https://w3id.org/xapi/tla/activity-types/assessment](https://w3id.org/xapi/tla/activity-types/assessment) | Any generic exercise that formally assesses the user&#39;s level of competence |
| Competency | [https://w3id.org/xapi/tla/activity-types/competency](https://w3id.org/xapi/tla/activity-types/competency) | A collection of knowledge, skills, abilities, or other behaviors needed to perform in a given task |
| Activity Cluster | [https://w3id.org/xapi/tla/activity-types/activity\_cluster](https://w3id.org/xapi/tla/activity-types/activity_cluster) | Any generic collection of activities and/or assessment activities |
| Career |[https://w3id.org/xapi/tla/activity-types/career](https://w3id.org/xapi/tla/activity-types/career) | An outline of jobs and their competency and credential requirements in a career, usually used to outline the expected learning path as series of verifiable milestones. |
| Badge |[https://w3id.org/xapi/tla/activity-types/badge](https://w3id.org/xapi/tla/activity-types/badge) | An online badge that is earned after achieving multiple related competencies. In this sense badge is any kind of credential, a badge, a certificate, a degree, a license, etc. |
| Job |[https://w3id.org/xapi/tla/activity-types/job](https://w3id.org/xapi/tla/activity-types/job) | A formal job, duty, legal obligation, permanent or temporary employment that requires a learner to possess some set of competencies and/or credentials |

<a name="E47"></a>
# Annex E
(informative)

**Description of TLA data and systems**
The learner object life cycle is divided into 3 &quot;levels&quot; of data or perspectives about the learner&#39;s learning path: Learner Career states (LC states), depicted in Figure 2; Learner Activity states (LA states), depicted in Figure 3; and Learner Record Provider states (LRP states), depicted in Figure 4. All verbs are divided into Authoritative Data (depicted below in green), Evidence statements (depicted below in blue), and Activity Planning (depicted below in red).

The TLA has many functional requirements for each of the component systems within a TLA environment. Those requirements are beyond the scope of this document, as are some of the components in their entirety. The following limited explanations provide a description of how the system functions within a TLA environment from the standpoint of learning experience data.

**Competency Management System –** is used to CRUD the concept and relationships that define jobs, credentials and competencies, as part of overarching competency frameworks, and calculates based on trust and evidence, the impact of learning events on the competencies and credentials of learners

**Learning Event Management System –** is used to track the completion of the learner data flow. Learning events are conducted as a sequence of launching and completing an experience. The conduct of a learning event exists in context, however, with the preparation and analysis of the learning environment, and includes goal setting, planning, scheduling, capturing, contextualizing, evaluating and locating exercises.

**Activity Provider –** is a creator of xAPI data (a type of LRP in xAPI) that generates a learning event (statement) on its own (on-the-job activity) or provides the context (reader, simulator) under which learning content is experienced.

**Learning Experience** – the combination of learning activities (context for the experience) and content (the resources for the experience) aligned for some educational purpose.

**Learner State –** the hierarchy of learning goals and sequenced subgoals, the tasks defined to satisfy those goals and the events that address the tasks. These link to the assertions of competency and conferral of credentials for which they provide a discoverable audit trail of evidence.

**Human Capital Management System –** is an end to end technical system used to track the recruiting, accession training, detailing, training, certification, promotions, screening and selections of capable manpower according to personnel jobsite definitions throughout the enterprise and over the entire career of personnel.

![MOM Career States](./Logos/MOM_Career_States.png)

**Figure 2 Learner Career States**

![MOM Activity States](./Logos/MOM_Activity_States.png)

**Figure 3 Learner Activity States**

![MOM LRP States](./Logos/MOM_LRP_States.png)

**Figure 4 Leaning Record Provider States**


#Foot Notes

<a name="foot-1">[1]</a>:The use of the word _must_ is deprecated and shall not be used when stating mandatory requirements, _must_ is used only to describe unavoidable situations.

<a name="foot-2">[2]</a>:The use of _will_ is deprecated and shall not be used when stating mandatory requirements, _will_ is only used in statements of fact.

<a name="foot-3">[3]</a>:IEEE publications are available from the Institute of Electrical and Electronics Engineers, Inc., 445 Hoes Lane, Piscataway, NJ 08854, USA ([https://standards.ieee.org/](http://standards.ieee.org/)).

<a name="foot-4">[4]</a>:IEEE publications are available from the Institute of Electrical and Electronics Engineers, Inc., 445 Hoes Lane, Piscataway, NJ 08854, USA ([https://standards.ieee.org/](http://standards.ieee.org/)).

<a name="foot-5">[5]</a>:[https://github.com/AICC/CMI-5\_Spec\_Current/blob/quartz/cmi5\_spec.md](https://github.com/AICC/CMI-5_Spec_Current/blob/quartz/cmi5_spec.md)

<a name="foot-6">[6]</a>:[https://tools.ietf.org/html/rfc8259](https://tools.ietf.org/html/rfc8259)

<a name="foot-7">[7]</a>:The numbers in brackets correspond to those of the bibliography in Annex A.

<a name="foot-8">[8]</a>:Prior to IEEE Standardization of xAPI, the following requirement existed: _This shall be in the same time zone and format as the rest of the timestamps in this statement_

This is still under develiopment and is subject to change.
