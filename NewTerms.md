# To Discus

## Actions for Duties
**md:Notify**

_Sub-class of odrl:Action_

The debtor makes the creditor aware of a relevant change in the state of the world (defined by the action scope).

Where the action scope is md:Usage, the debtor makes the creditor aware that they are using the asset.

<br>**md:Request**

_Sub-class of odrl:Action_

The debtor makes the creditor aware of a desired state of the world (defined by the action scope).

Where the action scope is md:Audit, the debtor requests the creditor to accede to an audit.

Where the action scope is md:ServiceFacilitator, the debtor requests the creditor allow a service facilitator to access the asset.

**md:Report**

_Sub-class of odrl:Action_

The debtor provides a report to the creditor on a relevant state of the world (defined by the action scope).

Where the action scope is md:ResonableSuspicion, the debtor reports a reasonable suspicion that the asset is being misused.

Where the action scope is md:Controls, the debtor reports on their implementation of access controls.

Where the action scope is md:Usage, the debtor reports on their usage of the asset as specified in the duty.

**md:Consent**
_Sub-class of odrl:Action_
The debtor accedes to a desired state of the world (defined by the action scope).

Where the action scope is md:Audit, the debtor consents to be audited by the creditor.

Where the action scope is md:ServiceFacilitator, the debtor consents to the creditor's use of a service facilitator.

**md:Compensate**
_Sub-class of odrl:Action_
The debtor pays the creditor.

**md:Invoice**
_Sub-class of odrl:Action_
The debtor bills the creditor.

**md:Attribute**
_Sub-class of odrl:Action_
The debtor publishes a description of the creditor's relation to the asset.

Where the action scope is md:Ownership, the attribution describes the creditor's ownership of the asset identified by the odrl:target relation.

Where the action scope is md:Disclaimer, the attribution clarifies the creditor's relation to the asset identified by the odrl:target relation.


## Action Scope for Duty Actions
**md:Usage**
_Sub-class of md:ActionScope_
Qualifies actions taken in the context of the assignee's usage of the asset.

**md:ServiceFacilitator**
_Sub-class of md:ActionScope_
Qualifies actions taken in the context of the assignee employing a service facilitator.

**md:Ownership**
_Sub-class of md:ActionScope_
Qualifies actions taken in the context of the assigner's ownership of the asset.

**md:Disclaimer**
_Sub-class of md:ActionScope_
Qualifies actions taken in the context of the assigner's clarification of their relation to the asset. 

**md:Audit**
_Sub-class of md:ActionScope_
Qualifies actions taken in the context of a proposed audit of the assignee by the assigner.

**md:ReasonableSuspicion**
_Sub-class of md:ActionScope_
Qualifies actions taken in the context of a reasonable suspicion that the assignee is misusing the asset.


# Constraints: predicates that test the state of the world
**md:recipient**
_Domain: odrl:Rule  
Range: odrl:Party_
A party with access to the asset

Frequently used to indicate whether the party is internal or external (i.e. a third party) to the assignee

Can be qualified by the role constraint.

**md:role**
_Domain: odrl:Party
Range: md:Role_
The role a party plays in respect of the asset.

Parties can play multiple roles.


## Simple Properties that specify an entity

**md:unitOfCount**
_Domain: odrl:Action
Range: md:UnitOfCount_
The thing to be counted.

Often used to specify the things to be counted (e.g. devices or access IDs) in a usage report or in calculating a payment.

Examples of Unit of Count:
* User ID
* Device
* Person
* Location
* Site
* Client Organisation

# Agreed

# To Do
"*What do we all* [the exchanges] *really care about? It's simple: distribution, non-display uses such as automated trading, and the creation of new financial products*" - CBOT

## AGENTS

### Originator

### Provider

### Consumer

### Vendor

### Service Facilitator
**Description:** External service provider contracted by the Consumer (or its Affiliated Companies) to assist in the delivery of data services.

### Broker
**Description:** Acting on behalf of another person’s name and for another person’s account or acting in one’s own name and for another person’s account i.e. trading to execute orders on behalf of clients.

**Scope Note:** DBAG - Smart order routing is considered to facilitate customer business

### Principle
**Description:** Undertakes activities for their own purposes i.e. acting in one’s own name or for one’s own account - not on someone else's account (like that of a client)

**Example:** Proprietary trading, Trading firms

**Scope Note:** DBAG - Market making is considered to be trading as principal

### Trading Platform
**Description:** A venue on which buy and sell orders from multiple parties are matched

**Scope Note:** Broker crossing networks and dark pools are examples of alternative trading systems (ATS), and are thus trading platforms.

**Scope Note:** Includes alternative trading systems (ATS) as defined by *300a of the SEC regulation on ATS*: any organization, association, person, group of persons, or system that constitutes, maintains, or provides a market place or facilities for bringing together purchasers and sellers of securities or for otherwise performing with respect to securities the functions commonly performed by a stock exchange.

**Scope Note:** Includes multilateral trading facilities (MTF) as defined in *MIFD II*: multilateral systems, operated by an investment firm or a market operator, which bring together multiple third-party buying and selling interests in financial instruments (in the system and in accordance with non- discretionary rules) in a way that results in a contract.

**Scope Note:** Includes organised trading facilities (OTF) as defined in *MIFD II*: multilateral systems which are not a regulated market or an MTF and in which multiple third-party buying and selling interests in bonds, structured finance products, emission allowances, or derivatives are able to interact in the system in a way that results in a contract.

**Scope Note:** Includes systematic internalization as defined in *MIFD II*: dealing on an organised, frequent, systematic, and substantial basis on one's own account when executing client orders outside a regulated market, an MTF, or an OTF, without operating a multilateral system.

## Assets & Resources

### Resource
**Description:** Some commodity (e.g. API calls, bandwidth, data) access to which (or to some part of which) may be controlled.

**Example:** In the context of market data, a resource could be the all the pricing and trading data generated by the trade in one or more financial instruments on an exchange, or indices derived from that data.

**Scope Note:** A resource is independent of the apects of commercialisation and/or delivery including timeliness, method of delivery, or book depth. These properties belong to the Asset. Whether it's realtime or delayed data from a venue, it's the same Resource but a different Asset.

**Scope Note:** A resource can be transformed through some calculation but still remain the same resource. It only becomes a new resource if the transformation is irreversable (i.e. the original data cannot be recovered) and non-substitutive (i.e. the altered data cannot be used in place of the original).

## Actions

### Distribute
**Description:** The onward dissemination of a Resource or any of its parts to a third-party.

### Display
**Description:** The display of data to a person or persons

###  Non-Display Use
**Description:** Usage when the scope and scale of usage is beyond that which could be reasonably expected of a person

**Editorial Note:** CME - Non-viewable use of Information in any system, process, program, machine or calculation other than in order to display or distribute Information for display. Such use may include, but is not limited to, calculation of P&L, portfolio valuation, order processing, use within Automated Trading Systems and automated order routing.

**Editorial Note:** DBAG - Non-Display Information Usage is accessing, processing or consumption of Real-Time Information for purposes other than the support of its display, onward dissemination to third parties or CFD Information-Usage.

**Example:** Automated valuations

**Example:** Calculating risk figures

**Example:** Portfolio valuation

**Example:** Profit and loss calculations

###  Benchmark
**Editorial Note:** The act of benchmarking as defined by the *EU Benchmark Regulation* is where an Index is used to determine the amount payable under a financial instrument or financial contract, or the value of a financial instrument, or is used to measure the performance of an investment fund for the purpose of tracking the return, defining the asset allocation or a portfolio, or computing the performance fees.

###  TradeAutomatically
**Editorial Note:** CME - Non-Display Use of Information by a Licensee Group entity in Automated Trading Systems."@en ,

**Editorial Note:** DBAG - Trading based activities’ include, but are not limited to, semi-automated or automated order/quote generation, order pegging, price referencing for trading purposes, smart order routing to facilitate trading, order management, execution management, market making, ‘black box’ trading, algorithmic trading, program trading and operation of multilateral trading facilities as well as quoting and trading of financial derivatives (including but not limited to futures, options, warrants and certificates linked to the respective underlying market data).

**Example:** Semi-automated or automated order/quote generation

**Example:** Algorithmic or program trading 

**Example:** Black-box trading

**Example:** Order Pegging

**Example:** Price referencing for trading purposes

**Example:** Systematic internalization *[Article 4(1)(20) of MiFID II]*

**Example:** Mid-point trading

**Example:** Smart order routing to facilitate trading

**Example:** Market making

**Example:** Execution Management

**Example:** Quoting and trading of financial derivatives

###  Derive
**Description:** To create a new derivative Resource from an Asset

**Editorial Note:** Derivations are frequently generated for the purposes of risk management, profit and loss calculation, portfolio valuation, quantitative analysis, fund administration, fund accounting, portfolio management or instrument pricing.

**Note:** The output of the derivation can be controlled by using a duty to impose a "next policy" action that points to a new policy that controls the use of the derived resource .


###  CalculateIndex
**Editorial Note:** An index as defined by the *EU Benchmark Regulation* means any figure that is regularly determined either by applying a formula or other calculation or making an assessment on the basis of the value of one or more underlying assets/prices (including estimated prices, actual or estimated interest rates, quotes and committed quotes, or other values or surveys).

###  Price
                                                 
# Hierarchy

    Distribute

    Use

      Display

      Non-Display Use

        Trade Automatically

        Benchmark

        Derive

          Calculate Index

          Price
