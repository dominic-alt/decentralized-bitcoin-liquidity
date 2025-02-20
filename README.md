# Decentralized Bitcoin Liquidity Pool (DLBP)

A secure and efficient liquidity pool protocol built on Stacks Layer 2, enabling seamless Bitcoin liquidity provision with yield generation.

## Overview

DLBP is a state-of-the-art liquidity pool designed for Bitcoin, leveraging Stacks Layer 2 for enhanced scalability and efficiency. The protocol enables users to deposit BTC, earn yield, and participate in a secure, decentralized financial ecosystem.

## Features

### Security

- Emergency pause mechanism with 24-hour cooldown periods
- Strict deposit and withdrawal limits
- Multi-level access control system
- Comprehensive event logging
- Robust error handling

### Yield Generation

- Dynamic APY adjustments (up to 100%)
- Block-height based calculations
- Efficient compound interest implementation
- Automated yield distribution

### Bitcoin Compliance

- Satoshi-based calculations
- Compatible with sBTC bridge
- Layer 2 optimized operations
- Secure transaction handling

## Technical Specifications

### Pool Parameters

- Minimum Deposit: 0.01 BTC (1,000,000 sats)
- Maximum Deposit per User: 10 BTC (1,000,000,000 sats)
- Maximum Pool Size: 1,000 BTC (100,000,000,000 sats)
- Default APY: 5% (500 basis points)
- Block Time: ~10 minutes (Stacks L2)

### State Management

- Real-time liquidity tracking
- User position management
- Yield rate snapshots
- Event history

## Core Functions

### User Operations

#### Deposit

```clarity
(define-public (deposit (amount uint)))
```

- Deposits BTC into the liquidity pool
- Validates deposit amount against pool constraints
- Updates user position and total liquidity
- Triggers yield calculations

#### Withdraw

```clarity
(define-public (withdraw (amount uint)))
```

- Withdraws BTC from the liquidity pool
- Verifies sufficient balance
- Updates user position and total liquidity
- Processes accumulated yield

#### Claim Yield

```clarity
(define-public (claim-yield))
```

- Claims accumulated yield
- Updates user yield metrics
- Resets accumulated yield counter
- Records yield payment

### Administrative Functions

#### Pool Management

```clarity
(define-public (set-pool-active (active bool)))
(define-public (set-pool-parameters (new-min uint) (new-max-per-user uint) (new-max-pool uint)))
(define-public (set-yield-rate (new-rate uint)))
```

- Toggle pool activity
- Update pool parameters
- Adjust yield rates

#### Emergency Controls

```clarity
(define-public (emergency-pause))
(define-public (emergency-resume))
```

- Immediate pool suspension
- Controlled resumption with cooldown
- Emergency event logging

#### Operator Management

```clarity
(define-public (add-operator (operator principal)))
(define-public (remove-operator (operator principal)))
```

- Authorize new operators
- Revoke operator access
- Access control management

### Read-Only Functions

#### User Information

```clarity
(define-read-only (get-user-position (user principal)))
```

- Retrieves user's current position
- Shows deposit amount
- Displays accumulated yield
- Provides historical metrics

#### Pool Statistics

```clarity
(define-read-only (get-pool-stats))
```

- Total liquidity
- Pool status
- Current yield rate
- Parameter settings
- Total yield paid

#### Event Tracking

```clarity
(define-read-only (get-event (event-id uint)))
```

- Event details
- Transaction history
- User actions
- Administrative changes

## Error Handling

The contract implements comprehensive error handling with specific error codes:

- Pool state validation
- Access control verification
- Balance checks
- Parameter validation
- Operation constraints

## Events System

All significant actions are logged with:

- Event type
- User principal
- Amount involved
- Block height
- Sequential event ID

## Security Considerations

### Access Control

- Owner-only administrative functions
- Operator authorization system
- Multi-level permission checks

### Safety Measures

- Emergency pause mechanism
- Cooldown periods
- Deposit/withdrawal limits
- Pool size restrictions

### Yield Protection

- Rate limits
- Calculation verification
- Balance validation
- Overflow prevention

## Development and Testing

### Prerequisites

- Clarity CLI
- Stacks 2.4 or later
- Bitcoin node (optional)
- Testing framework

### Deployment

1. Deploy to Stacks Layer 2
2. Initialize pool parameters
3. Add initial operators
4. Activate pool

## Contributing

Contributions are welcome! Please read our contributing guidelines before submitting pull requests.
