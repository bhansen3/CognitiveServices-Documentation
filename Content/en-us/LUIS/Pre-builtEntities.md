<!-- NavPath: Pre-builtEntities
LinkLabel: Pre-built Entities 
Url: LUIS-api/documentation/Pre-builtEntities
Weight: 90 -->

#Pre-built Entities

LUIS includes a set of pre-built entities. When a pre-built entity is included in your application, its predictions will be included in your published application and be available to you in the LUIS web UI while labeling utterances. The behavior of pre-built entities cannot be modified. Unless otherwise noted, each pre-built entity is available in all LUIS application locales (cultures). 

Below is a table of pre-built entities with example utterances and their return values.

Pre-built entity   |   Example utterance   |   JSON
------|------|------|
 builtin.number     |   ten   |``` { "type": "builtin.number", "entity": "ten" } ```|
 builtin.number     |   3.1415   |```  { "type": "builtin.number", "entity": "3 . 1415" }``` |
 builtin.ordinal     |   first   |```{ "type": "builtin.ordinal", "entity": "first" }``` |
 builtin.ordinal     |   10th   | ```{ "type": "builtin.ordinal", "entity": "10th" }``` |  
 builtin.temperature     |   10 degrees celcius   | ```{ "type": "builtin.temperature", "entity": "10 degrees celcius" }```|   
 builtin.temperature     |   78 F   |```{ "type": "builtin.temperature", "entity": "78 f" }```|
 builtin.dimension     |   2 miles   |```{ "type": "builtin.dimension", "entity": "2 miles" }```|
 builtin.dimension     |  650 square kilometers   |```{ "type": "builtin.dimension", "entity": "650 square kilometers" }```|
 builtin.money     |   1000.00 US dollars   |```{ "type": "builtin.money", "entity": "1000.00 us dollars" }```
 builtin.money     |   $ 67.5 B   |```{ "type": "builtin.money", "entity": "$ 67.5" }```|
 builtin.age   |   100 year old   |```{ "type": "builtin.age", "entity": "100 year old" }```|  
 builtin.age   |   19 years old   |```{ "type": "builtin.age", "entity": "19 years old" }```|
 builtin.datetime | See separate table below | See separate table below |
 builtin.geography | See separate table below | See separate table below |
 builtin.encyclopedia | See separate table below | See separate table below |
 
 The last 3 built-in entity types encompass multiple subtypes. These are covered next.
 
###builtin.datetime

The builtin.datetime pre-built entity has awareness of the current date and time. In the examples below, the current date is 2015-08-14. Also, builtin.datetimeprovides a resolution field that produces a machine-readable dictionary. 

######This pre-built entity has 3 subtypes:

Pre-built entity   |   Example utterance   |   JSON
------|------|------|
