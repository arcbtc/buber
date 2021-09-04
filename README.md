# BUber
## Outline for BUber taxi service on Nostr

Uber works well, apart from the Uber company.

BUber uses the https://github.com/fiatjaf/nostr network to connect taxis and clients, in a permissionless way.

### Setup:

User opens software and selects whether they are a *taxi* or *customer* (either choice issues Schnoor keypair, or they can add their own pre-existing keypair)

### Workflow:

**Taxi:** Using their private key, the taxi publishes their `geolocation`, `rate`, and `availability` to relays.

**Customer:** Software recieves all taxis in the location of the customer and lists their `rate`, `availability` and `reputation` (if the taxi has `reputation` https://github.com/fiatjaf/nostr/issues/20).

**Customer** Using their private key, the customer publishes a request for a particular taxi and where they want to go.

**Taxi:** The *taxi* receives the *customers* request, and `reputation`, if the *customer* has `reputation` https://github.com/fiatjaf/nostr/issues/20

**Taxi:** Using their private key, the *taxi* accepts the job. `Geolocation` data is sent every few seconds to the customer, so they can track.

**Customer/Taxi:** Service happens, `reputation` is given at the end of the transaction.

> Note: I will build an https://github.com/lnbits/lnbits extension that acts as a Nostr client software for taxi driver and customer, but any client software for BUber will perform the same functions
