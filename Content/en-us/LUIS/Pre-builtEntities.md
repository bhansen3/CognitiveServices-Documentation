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
builtin.datetime.date      |   tomorrow   |```{ "type": "builtin.datetime.date", "entity": "tomorrow", "resolution": {"date": "2015-08-15"} }``` |
builtin.datetime.date      |   january 10 2009   |```{ "type": "builtin.datetime.date", "entity": "january 10 2009", "resolution": {"date": "2009-01-10"} }```|
builtin.datetime.date      |   monday    |```{ "entity": "monday", "type": "builtin.datetime.date", "resolution": {"date": "XXXX-WXX-1"} }```|
builtin.datetime.date      |   next week   |```{ "entity": "next week", "type": "builtin.datetime.date", "resolution": {"date":  "2015-W34"} }```|
builtin.datetime.date      |   next monday   |```{ "entity": "next monday", "type": "builtin.datetime.date", "resolution": {"date": "2015-08-17"} }```|
builtin.datetime.date      |   week of september 30th   |```{ "entity": "week of september 30th", "type": "builtin.datetime.date", "resolution": {"comment": "weekof", "date": "XXXX-09-30"} }```|
builtin.datetime.time      |   3 : 00   |```{ "type": "builtin.datetime.time", "entity": "3 : 00", "resolution": {"comment": "ampm", "time": "T03:00"}	}```|
builtin.datetime.time      |   4 pm     |```{ "type": "builtin.datetime.time", "entity": "4 pm", "resolution": {"time": "T16"}	}```|
builtin.datetime.time      |   tomorrow morning   |```{ "entity": "tomorrow morning", "type": "builtin.datetime.time", "resolution": {"time": "2015-08-15TMO"} }```|
builtin.datetime.time      |   tonight  |```{ "entity": "tonight", "type": "builtin.datetime.time", "resolution": {"time": "2015-08-14TNI"} }```|
builtin.datetime.duration      |    for 3 hours    |```{ "type": "builtin.datetime.duration", "entity": "3 hours", "resolution": {"duration": "PT3H"}	}```|
builtin.datetime.duration      |    30 minutes long   |```{ "type": "builtin.datetime.duration", "entity": "30 minutes", "resolution": {"duration": "PT30M"}	}```|    
builtin.datetime.duration      |    all day    |```{ "type": "builtin.datetime.duration", "entity": "all day", "resolution": {"duration": "P1D"}	}```|
builtin.datetime.set    |   daily   |```{ "type": "builtin.datetime.set", "entity": "daily", {"resolution": "time": "XXXX-XX-XX"}	}```|
builtin.datetime.set    |   every morning   |```{ "type": "builtin.datetime.set", "entity": "every morning", "resolution": {"time": "XXXX-XX-XXTMO"}	}```|
builtin.datetime.set    |   every tuesday   |```{ "entity": "every tuesday", "type": "builtin.datetime.set", "resolution":  {"time": "XXXX-WXX-2"} }```|   
builtin.datetime.set    |   every week   |```{ "entity": "every week", "type": "builtin.datetime.set", "resolution": {"time": "XXXX-WXX"} }```|
