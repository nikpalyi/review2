# Highlevel demo of Accepting RAMPID's for SUSPEND/LOCK commands

## What is BPA
The **Bet Pattern Alarm** app is an application utilized by Fanduel traders to monitor betting patterns.  
When a suspicious pattern is detected, traders can use the BPA app to send market suspend and lock messages to Event State via ESAG, using the RAMP Market ID as the market identifier.

## What is ESAG and ES
**Event State API Gateway** is an API upstream of Event State designed to facilitate the publication of messages from client applications to Event State through a simple Rest API. In turn, Event State acts as a central hub, aggregating data from the Trading Tribe's sports models and feeds, and providing a delta feed of changes to Events, Markets, and Selections.

## What have we achieved so far?
We have implemented a process that allows traders to respond swiftly to unusual betting patterns.  
When the BPA app identifies a risky bet pattern, the affected market can be immediately suspended.  
The command used for this action is known as "suspend market," and it requires a specific market identifier, which is typically the RAMP Market ID, although there are exceptions such as Alium markets which generate their own identifiers.  
To enable this functionality, the following flow has been established: BPA → ESAG → ES.

<img src=rampid.png alt="RAMPID FLOW" width="600" height="300" />

## Wrap up
Through the integration of BPA, ESAG, and Event State, Fanduel traders now have the capability to swiftly suspend and lock markets using RAMP Market IDs, ensuring immediate action can be taken to maintain the integrity of the betting environment.  
This integration highlights the commitment to proactive risk management and the enhancement of trader efficiency.
