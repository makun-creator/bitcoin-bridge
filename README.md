# Bitcoin Bridge Smart Contract

A secure and decentralized bridge enabling trustless transfers between Bitcoin and Stacks networks.

## Features

- Multi-validator consensus mechanism
- Secure deposit verification
- Atomic swaps with configurable confirmation thresholds
- Emergency controls and safety measures
- Row-level security and access controls
- Comprehensive input validation

## Architecture

The bridge operates through a multi-step process:

1. **Deposit Initiation**: Validators monitor Bitcoin transactions and initiate deposits
2. **Confirmation**: Multiple validators confirm deposits after required Bitcoin confirmations
3. **Minting**: Confirmed deposits trigger balance updates on Stacks
4. **Withdrawal**: Users can withdraw funds by providing Bitcoin addresses
5. **Emergency Controls**: Contract owner can pause operations and handle emergencies

## Quick Start

```clarity
;; Initialize bridge
(contract-call? .btc-bridge initialize-bridge)

;; Add validator
(contract-call? .btc-bridge add-validator 'SP2J6ZY48GV1EZ5V2V5RB9MP66SW86PYKKNRV9EJ7)

;; Initiate deposit
(contract-call? .btc-bridge initiate-deposit
    0x1234567890abcdef  ;; Bitcoin transaction hash
    u100000             ;; Amount in satoshis
    'SP2J6ZY48GV1EZ5V2V5RB9MP66SW86PYKKNRV9EJ7  ;; Recipient
    0x02...            ;; Bitcoin sender public key
)
```

## Security

- Multi-signature validation required for deposits
- Configurable confirmation thresholds
- Emergency pause functionality
- Comprehensive input validation
- Rate limiting on deposits/withdrawals
- Regular security audits required

## Testing

Run tests using Clarinet:

```bash
clarinet test tests/btc-bridge_test.ts
```
