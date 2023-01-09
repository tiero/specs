# Specs

BitsApp specifications (BAS in short) stand for **BitsApp Implementation Specifications**. Specs are written to provide open and accessible documentation for [BitsApp](https://bits.app) implementation details.

- [BAS-01: One-directional channels](01.md)
- [BAS-02: Expiring channel addresses](02.md)
- [BAS-03: Silent swaps](03.md)
- [BAS-04: Swap factories](04.md)
- [BAS-05: Swap initiation protocol](05.md)
- [BAS-06: Swap credit protocol](06.md)
- [BAS-07: Swap settlement protocol](07.md)
- [BAS-08: Swap statuses](08.md)
- [BAS-09: Payment statuses](09.md)
- [BAS-10: Interactive swap invoices](10.md)
- [BAS-11: Non-interactive swap invoices](11.md)
- [BAS-12: Permenant channel addresses](12.md)
- [BAS-13: Encumbered silent swaps](13.md)
- [BAS-14: Inbound swap settlement protocol](14.md)
- [BAS-15: Silent swaps trees](15.md)
- [BAS-16: Swap settlement credits](16.md)
- [BAS-17: Channel backups](17.md)
- [BAS-18: Channel recovery](18.md)
- [BAS-19: Swap service](19.md)
- [BAS-20: Routing service](20.md)
- [BAS-21:  Service provider federation](21.md)

## Event Kinds

| kind        | description                 | NIP                    |
|-------------|-----------------------------|------------------------|
| 0           | Metadata                    | [1](01.md), [5](05.md) |
| 1           | Text                        | [1](01.md)             |
| 2           | Recommend Relay             | [1](01.md)             |
| 3           | Contacts                    | [2](02.md)             |
| 4           | Encrypted Direct Messages   | [4](04.md)             |
| 5           | Event Deletion              | [9](09.md)             |
| 6           | Repost                      | [18](18.md)            |
| 7           | Reaction                    | [25](25.md)            |
| 40          | Channel Creation            | [28](28.md)            |
| 41          | Channel Metadata            | [28](28.md)            |
| 42          | Channel Message             | [28](28.md)            |
| 43          | Channel Hide Message        | [28](28.md)            |
| 44          | Channel Mute User           | [28](28.md)            |
| 45-49       | Public Chat Reserved        | [28](28.md)            |
| 10000-19999 | Replaceable Events Reserved | [16](16.md)            |
| 20000-29999 | Ephemeral Events Reserved   | [16](16.md)            |


## Message types

### Client to Relay
| type  | description                                         | NIP        |
|-------|-----------------------------------------------------|------------|
| EVENT | used to publish events                              | [1](01.md) |
| REQ   | used to request events and subscribe to new updates | [1](01.md) |
| CLOSE | used to stop previous subscriptions                 | [1](01.md) |

### Relay to Client
| type   | description                                             | NIP         |
|--------|---------------------------------------------------------|-------------|
| EVENT  | used to send events requested to clients                | [1](01.md)  |
| NOTICE | used to send human-readable messages to clients         | [1](01.md)  |
| EOSE   | used to notify clients all stored events have been sent | [15](15.md) |
| OK     | used to notify clients if an EVENT was successuful      | [20](20.md) |

Please update these lists when proposing NIPs introducing new event kinds.

When experimenting with kinds, keep in mind the classification introduced by [NIP-16](16.md).

## Criteria for acceptance of NIPs

1. They should be implemented in at least two clients and one relay -- when applicable.
2. They should make sense.
3. They should be optional and backwards-compatible: care must be taken such that clients and relays that choose to not implement them do not stop working when interacting with the ones that choose to.
4. There should be no more than one way of doing the same thing.
5. Other rules will be made up when necessary.

## License
