[![GitHub Actions - two browser chat](https://github.com/silkroadnomad/decentralized-address-book/actions/workflows/main.yml/badge.svg)](https://github.com/silkroadnomad/decentralized-address-book/actions/workflows/main.yml)
![Vercel](https://therealsujitk-vercel-badge.vercel.app/?app=decentralized-address-book)

# A decentralized address book with OrbitDB and Svelte

## Workflow
1. Alice: Enter your own address  (and store it locally in your browser storage)
2. Bob scans the QR-Code of Alice (QR-Code contains Alice username)
3. Bob requests a Alice vCard via Waku (Alice subscribed on Waku-Network)
4. Alice sends her vCard
5. Bob stores vCard in localstorage currently deleted

## Usage
Browser A)
- under Settings->identity set your name (e.g. Alice) (this is planed for a DID!)
- under MyAddress add Alice own address and mark own address

Browser B)
- under Settings->identity set other name (e.g. Bob)
- under MyAddress add Bobs own address and mark own address 

Browser A)
- under Contacts type "Bob" and click on "Scan Address"

Result: Address of Bob should be added automatically on Alice address book

## Todo
- add confirm modal when requesting address from Bob - add checkout "send my own address"
- add confirm notification on Bob when send-address request arrives - optionally add Address of "Alice"
- add confirm notification on Alice when deliver-address message arrives to add address
- if Alice or Bob updates her/his address send an update-address command - test offline behaviour of recipient. 
- test Waku-Feature "ephemeral: messages"
- store local address book in a local first db (e.g. OrbitDB) so it is replicating with peers with same identity
- refactor network operations to be used with / create new branch for:
  - Peer-to-peer & Local First
    - LibP2P local first / p2p see p2p-playground
    - Automerge: https://automerge.org/
    - Plain IPFS
  - Peer-to-peer & Non Local First 
  - Nostr: https://nostr.com/

## Resources
- https://docs.waku.org/guides/js-waku/light-send-receive/
- https://github.com/waku-org/js-waku

## Done
- 30.12.2023 fix adding full address attributes
