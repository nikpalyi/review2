# Highlevel demo of PCS - 23/01/24

## What is PCS
It stands for `Product Catalogue Service` !
It's original intention was enable services to integrate with it via a backend technology, `gRPC`, supplying a given events `latest state` & `updates`.
With it's endpoints all returning data in **bytes format**.
```bash
$ curl "https://dmpcs-nxt.trading-dev.aws.private/app/get_state/34022233" --output -
```


## Where is PCS going ?

It's scope has expanded and now it supports `HTTP Websocket` technology & its endpoints can return state in **json format**.
We are currently working on **PCS**, supporting the **DOM** team who are creating a new **MPM Search UI**, which uses **PCS** as its backend.
This represents a shift for **PCS**, in that it is the first time it is supporting a front end service, using frontend technologies.

These changes are all part of ongoing work to enable **PCS** to replace **ESS** which is a component within **MPM**.


## What is MPM & ESS

**MPM** or more precisely `Manual Product Management` is a **UI** with suite of services that support traders via live updates.
During the creation of **GTT**, **MPM** had no clear ownership but has since been "re-homed" with **GPD** as it is a strategic fit.
It's backend suite of services were all written in `.Net`.
**PCS** is intended to replace **ESS** - `Event Subscription Service`, enabling **GPD** to provide greater support due to **PCS** being in scala.
Plus support in providing an all round better experience for Users.

## What have we acheived so far ?

**PCS Docs**: [documentation](https://fluttergroup.atlassian.net/wiki/spaces/GTT/pages/4292423822687/GPD+-+Product+Catalogue+Services+DMPCS#HTTP-Endpoints)


**MPMUI Search**: [search](https://iap.prf.internal/mpmf/search)


**Demo**:
* `websockets`
```bash
# open WS connection
websocat wss://dmpcs-nxt-ext.trading-dev.aws.private:8443/app/subscribe

# create a subscription
{"CreateEventSubscription":{"eventId":34022233,"subscriptionId":"esports"}}
```

* `json endpoint`
```bash
$ curl "https://dmpcs-nxt.trading-dev.aws.private/app/get_state/34022233?format=json"
```

## Wrap up
We see **PCS** having a lot of potential to help support other services & use cases in the future.
