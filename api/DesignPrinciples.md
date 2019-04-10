# REC API Design Principles

As decided at the API development workshop held 2019-04-10 at Vasakronan (participants: Karl Hammar, Erik Wallin, Per Karlberg, Håkan Eriksson, Peter Hartlev, Robert Barlin and Mats Mogren). Subject to approval from REC Consortium Board.

* A new API group will be established within the REC consortium, including:
  * Karl Hammar
  * Per Karlberg
  * Peter Hartlev
  * Robert Barlin
  * Håkan Eriksson
  * ...?
* The API group will collaborate via the REC Slack workspace, in the #api channel.
* The REC API shall be version managed and released in tandem with new REC ontology versions.
* API URI:s will be based on REC classes, e.g. /api/Room/, /api/Sensor/, /api/Building/, etc.
* The API will accept and return JSON-LD representations.
* The API will implement basic subsumption reasoning, such that it will return instances of subclasses and subproperties when superclasses and superproperties are requested.
  * However, only such properties as are relevant to the requested superclass will be returned for its subclass instances.
* API reasoning will operate under Closed World and Unique Name Assumptions -- i.e., messages will be expected to adhere to exactly the cardinalities and structures defined in the ontology, and nodes with different identifiers will not be collapsed to one identity (with the exception of explicit sameAs or equivalentClass/equivalentProperty declarations).
* The API documentation (and possibly in the future also reference implementations) will be generated semi-automatically from the ontology.
  * Human editing may however be need to filter the generated documentation, as we may otherwise end up with a very unwieldy/extensive documentation which is inaccessible to the target developer-users.
* The API will support pagination of returned data.
* The API will support filtering and sorting of data.
* The API will support some mechanism for synchronous calls throughout the whole system/stack, i.e., such that calling clients can call for an actuation and once that actuation has been carried out, be informed of this. How specifically this is implemented remains to be decided; options include but are not limited to:
  * Some callback reference being returned from the API upon reciept of a new Actuation object
  * Some predicate on Observation objects linking them to Actuation objects that caused said Observation
* (LOW priority) -- The API will, in time, support modularity in the underlying ontology, e.g., such that implementers can choose which REC ontology modules to load. 
* (LOW priority) -- The API will, in time, support multilinguality, i.e., such that users can request which language representations of string literals to return, and in which order.
