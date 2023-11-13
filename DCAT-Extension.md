# DCAT Extensions
## 1.	TIME-BASED PROPERTIES
###1.1.	Timeliness
```dprod:timeliness```

**Cardinality**
**0 – 1**

**Label**
Timeliness of delivery

**Definition**
Specifies the timing of the permitted use or onwards delivery of a Dataset.

**Note**
These intervals are frequently identified as Realtime, Delayed, or Embargoed.

**Note**
Unless explicitly prohibited, Permissions over shorter intervals carry across to longer intervals (e.g. Realtime data also covers Delayed, and Embargoed data)

**Domain**
```dcat:Dataset```

**Range**
```time:ProperInterval```

###1.2.	Update Method
```dprod:updateMethod```

**Cardinality**
0 – 1

Label
Method of update

Definition
Specifies the method by which a Dataset is updated. 

Note
Must have a value of either Snapshot, Streaming, or Time Series

Domain
dcat:Dataset

Range
dprod:UpdateMethod
1.3.	Update Period
dprod:updatePeriod
Cardinality
0 – 1

Label
Period of update

Definition
The period during which the Dataset has been, or continues to be, updated.

Note
If the Dataset is updated while a subscription holds, use the Service Period interval.

Domain	
dcat:Dataset

Range
time:ProperInterval
1.4.	Sample Frequency
dprod:sampleFrequency
Cardinality
0 – 1

Label
Sample Frequency

Definition
Specifies if and how often a data stream is sampled to provide updates to the Dataset 

Note
Must have a value of either Tick-By-Tick or Sampled

Domain
dcat:Dataset

Range
dprod:SampleFrequency
1.5.	Publication Schedule
dprod:publicationSchedule
Cardinality
0 – 1

Label
Publication Schedule

Definition
Specifies the periodicity with which updates to a Dataset are published

Note


Domain
dcat:Dataset

Range
cld:Frequency
1.6.	Temporal
dprod:temporal
Cardinality
0 – 1

Definition
The temporal coverage offered by a dataset.

Scope Note
Usually used to specify the date range of historical data.

Note
If no end-date is specified for the interval, then it is assumed to be “now”.

Label
Temporal coverage

Domain
dcat:Dataset

Range
time:ProperInterval

Sub-property of 
dc:temporal

2.	CONTENT-DESCRIBING PROPERTIES
2.1.	Content Type
dprod:contentType
Cardinality
0 – n

Definition
Specifies the type of content provided in a Dataset or Dataset Series

Label
Content type

Domain
dcat:Dataset, dcat:DatasetSeries

Range
dprod:ContentType

Examples
Indices, trading data, post trade data, fixings, news, economics, people
2.2.	Asset Class
dprod:assetClass
Cardinality
0 – n

Definition
Qualifies the content type of a Dataset or series by the financial asset class it describes.

Label
Asset class

Domain
dprod:ContentType

Range
dprod:AssetClass – preferably using CFI codes as instance data
2.3.	Market Depth
dprod:marketDepth
Cardinality
0 – 1

Definition
Measures the book depth offered by a Dataset.

Label
Depth of market

Domain
dcat:Dataset

Range
dprod:MarketDepth

2.3.1.	Market Depth Constraints
2.3.1.1.	Position From
dprod:positionFrom
Cardinality
0 – 1

Definition
Denotes the bid depth from which the Dataset offers prices.

Label
Position from

Domain
dprod:MarketDepth

Range
xsd:integer
2.3.1.2.	Position To
dprod:positionTo
Cardinality
0 – 1

Definition
Denotes the bid depth up to which the Dataset offers prices (inclusive).

Label
Position to

Domain
dprod:MarketDepth

Range
xsd:integer
2.4.	Spatial
dprod:spatial
Cardinality
0 – n

Definition
The geographic subject matter and focus of a dataset or series.

Scope Note
A characteristic of the dataset or series rather than its source/origin or any limitations on its distribution.

Label
Geographic coverage

Domain
dcat:Dataset, dcat:DatasetSeries

Range
schema:AdministrativeArea - UN M49 Codes for regions and subregions, ISO for countries and country subdivisions

SubProperty Of
dc:spatial
2.5.	Quantity (better word?)
dprod:quantity
Cardinality
0 – 1

Definition
The amount of a Dataset Series made available in a Dataset

Note
If a qualitative measure is all that is needed use the values dprod:Insubstantial or dprod:Substantial. 

Else additionally specify a numeric value (odrl:count) and a unit of count (odrl:unitOfCount).

Label
Amount

Domain
dcat:Dataset

Range
dprod:Quantity 
3.	TIME INTERVALS
3.1.	Realtime
dprod:Realtime
Label
Realtime

Definition
Data received, used, or delivered with minimum latency after its time of origination, publication, or issue. 

Note
The latency can be quantified by specifying the beginning of the interval (time:hasBeginning) and its duration (time:hasXSDDuration).

Subclass Of
time:ProperInterval
3.2.	Delayed
dprod:Delayed
Label
Delayed

Definition
Data received, used, or delivered at or after a specified time interval following its time of origination, publication, or issue. 

Note
The delay can be quantified applying the time:intervalAfter property to the Realtime interval specification.

Subclass Of
time:ProperInterval
3.3.	Historical
dprod:Historical
Definition
Stored data that relates to events in the past. 

Note
Usually held in the form of a time series

Label
Historical

Subclass Of
time:ProperInterval
3.4.	Embargoed
dprod:Embargoed
Label
Embargoed

Definition
Data received, used, or delivered on or after a specified instant or future event. Can be quantified using the time:intervalAfter property with the embargo time specified using the time:hasBeginning property.

Editorial Note
Used to describe end-of-day or after-midnight data.

Subclass Of
time:ProperInterval
3.5.	Service Period
dprod:ServicePeriod
Label
Service period

Definition
The period across which a subscription holds.

Type
time:ProperInterval
 
4.	TIME INSTANTS
4.1.	Origination Time
dprod:originationTime
Label
Origination time

Definition
The moment information condenses into data.

Example
The instant a price is struck and recorded.

Type
time:Instant
4.2.	Publication Time
dprod:publicationTime
Label
Publication time

Definition
The instant data is released by the Originator for distribution

Type
time:Instant
4.3.	Issue Time
dprod:issueTime
Label
Issue time

Definition
The instant data is distributed from the Originator

Type
time:Instant
4.4.	Market Close
dprod:marketClose
Label
Market close

Definition
The time published by the venue specifying when a market closes.

Type
time:Instant 
5.	Update Method
5.1.	Snapshot
dprod:Snapshot
Label
Snapshot

Definition
An update is provided only in response to a request (like an API call). 

Editorial Note
Also known as “one-shot”.

Note
The number of requests (or snaps) permitted can be specified using the count property (odrl:count) and a duration (time:hasXSDDuration).

Subclass Of
dprod:UpdateMethod
5.2.	Streaming
dprod:streaming
Label
Streaming

Definition
Changes are captured and continuously transmitted either individually or in batches.

Subclass Of
dprod:UpdateMethod
5.3.	Time Series
dprod:timeSeries
Label
Time Series

Definition
Multiple updates are delivered together in bulk, often as a file.

Type
dprod:UpdateMethod
 
6.	Sample Frequency
6.1.	Tick by Tick
dprod:tickByTick
Label
Tick-by-tick

Definition
Any and every change in value is provided in an update.

Type
dprod:SampleFrequency

6.2.	Sampled
dprod:sampled
Definition
Updates are sampled and/or conflated.

Note
Only selected updates are delivered at specified intervals or on specific events (e.g. market close or quarterly results).

Note
The sampling frequency of can be specified using the time:hasXSDDuration property.

Label
Sampled

Subclass Of
dprod:SampleFrequency

 
7.	Market Depth
7.1.	Last Trade Price
dprod:lastTradePrice
Definition
The price at which the most recent trade was executed

Label
Last trade price

Subclass Of
dprod:MarketDepth
7.2.	Market Price
dprod:MarketPrice
Definition
Market Price includes the content relating to at least the best bid and best ask/offer in the market.

Editorial Note
Also known as “Level 1” data.

Note
If more prices beyond the best bid are offered, the book depth can be specified by using the dprod:positionTo and dprod:positionFrom properties.

Label
Market price

Subclass Of
dprod:MarketDepth
7.3.	Full Order Book
dprod:FullOrderBook
Definition
The Full Order Book includes content relating to the bids and asks/offers at all price points and from all participants in the market.

Editorial Note
Also known as "market by order", the "detailed order book", or "Level 2"/"Level 3" data.

Note
If more prices beyond the best bid are offered, the book depth can be specified by using the dprod:positionTo and dprod:positionFrom properties.

Label
Full order book

Subclass Of
dprod:MarketDepth
