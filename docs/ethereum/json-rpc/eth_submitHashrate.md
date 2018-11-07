# eth_submitHashrate

Used for submitting mining hashrate.

### REQUEST

`POST https://<network>.infura.io/v3/YOUR-PROJECT-ID`

#### HEADERS

`Content-Type: application/json`

#### REQUEST PAYLOAD
- `HASHRATE` _[required]_ - a hexadecimal string representation (32 bytes) of the hash rate
- `ID` _[required]_ - a string representing a random hexadecimal (32 bytes) ID identifying the client

#### EXAMPLE
```bash
## JSON-RPC over HTTPS POST
## Replace YOUR-PROJECT-ID with a Project ID from your Infura Dashboard
## You can also replace mainnet with a different supported network
curl https://mainnet.infura.io/v3/YOUR-PROJECT-ID \
    -X POST \
    -H "Content-Type: application/json" \
    -d '{"jsonrpc":"2.0","method":"eth_submitHashrate","params":["0x0000000000000000000000000000000000000000000000000000000000500000", "0x59daa26581d0acd1fce254fb7e85952f4c09d0915afd33d3886cd914bc7d283c"],"id":1}'

## JSON-RPC over websockets
## Replace YOUR-PROJECT-ID with a Project ID from your Infura Dashboard
## You can also replace mainnet with a different supported network
wscat -c wss://mainnet.infura.io/ws/v3/YOUR-PROJECT-ID
>{"jsonrpc":"2.0","method":"eth_submitHashrate","params":["0x0000000000000000000000000000000000000000000000000000000000500000", "0x59daa26581d0acd1fce254fb7e85952f4c09d0915afd33d3886cd914bc7d283c"],"id":1}
```

### RESPONSE

#### RESULT FIELDS
- `SUCCESS` - returns true if submitting went through succesfully and false otherwise.

#### BODY

```json
{
  "id":1,
  "jsonrpc":"2.0",
  "result": true
}
```
