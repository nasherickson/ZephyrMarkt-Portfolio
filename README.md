# ZephyrMarkt

Offline-first POS & inventory system for vendors, booths, and small shops.
Designed to work anywhere no WiFi, no servers, no subscriptions, no headaches.

It’s the system I wish existed when I needed one.  
When nothing out there worked for real vendors,  
I stopped playing by everyone else’s rules and made my own.

---

## Why It Exists

Most tools assume every creator has:  
- a business degree  
- a full-stack developer  
- stable internet  
- and time to fight a POS system while a customer is staring at them  

Reality says otherwise.

ZephyrMarkt was built to solve real-world problems:  
- selling in chaotic convention halls  
- running a shop with unreliable WiFi  
- managing inventory without spreadsheets  
- printing labels & barcodes without special hardware  
- syncing multiple devices without a cloud backend  

This isn’t theory.  
This is field-tested engineering for people who make things.

---

## What It Feels Like

**Elegant.  
Calm.  
Obvious.**

The UI adapts to you.  
Panels ease into focus as you hover.  
The “liquid glass” design keeps your booth looking intentional even when the world on the other side of the table is chaos.

The color choices aren’t an accident.

Every banner, chip, and indicator is chosen to stay steady under stress.  
No screaming reds.  
No panic-coded warnings.

Just clear, neutral signals that keep you grounded —  
and keep customers from sensing anything’s wrong.

It’s a system built to stay quiet when things get loud.  
Readable states. Calm tones.  
Professional, even when you’re juggling three things at once.

---

## Core Features

### Offline-first datastore
- GRDB SQLite  
- replication-friendly event log  
- idempotent inserts  
- unique event UUIDs  
- safe mid-transaction shutdown  

### Peer-to-peer sync
- MultipeerConnectivity  
- hub/follower model  
- auto-discovery  
- heartbeats  
- batch catch-up  
- backoff + jitter  
- conflict-safe idempotency  

### Inventory workflow
- create, import, edit  
- pricing  
- automatic barcodes  
- recent-tag chips  
- bins, shelves, quick-add  

### Shipping
- ULID order IDs  
- fulfillment dashboard  
- label templates  
- queue view  
- PDF & ZPL output  

### Printer pairing
- CoreBluetooth  
- persistent profiles  
- ZPL/PDF generation  
- reprint flow  

### UI
- adaptive grid  
- translucent liquid-glass panels  
- focus fade  
- high-contrast calm colors  
- zero unnecessary chrome  

---

## Architecture Overview

### State Model
A single root `AppState` orchestrates:  
- BoothPeer  
- replication pipeline  
- GRDBStore  
- workspace descriptors  
- device presence  
- shipping queue  
- printer pairing  

### Replication Pipeline
- planned envelope signing  
- idempotent batch apply  
- unique event IDs  
- hub ACKs  
- follower catch-up logic  

### UI Composition
- dashboard grid  
- network, inventory, sales, shipping, backroom panels  
- detailed screens for printers, profiles, roles, orders, item forms  

### Design Philosophy
- state flows downward  
- UI never triggers side effects  
- services own their lifecycle  
- resilience over convenience  

---

## Technical Highlights

### Replication
- duplicate events filtered in GRDB  
- insert-or-ignore persistence  
- in-memory parity store  
- exponential backoff + jitter  

### Persistence
- event-sourced ledger  
- deterministic workspace state  
- lightweight migrations  

### Networking
- peer advertisement  
- presence smoothing  
- workspace mismatch prompts  

### UI
- focus fade  
- dynamic width clamps  
- adaptive columns  
- layered glass effects  
- calm, neutral status chips  

---

## Potential Next Steps
- strengthen replication security  
- Shopify integration (inventory sync, price updates, archives)  
- greater printer abstraction  
- test coverage  
- split AppState into focused services  
- AI-powered “Pocket Zeph” assistant  

---

## Why This Project Matters

ZephyrMarkt wasn’t built to be pretty on a slide deck.  
It was built because real people needed it.

It’s the product of fieldwork, problem solving,  
and refusing to accept “that’s just how POS systems are.”

It’s proof of what I do best.  
**learn fast, design clean, and make tools that actually work.**
