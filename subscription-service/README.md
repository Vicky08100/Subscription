# Subscription Service Smart Contract

## Overview

This smart contract implements a subscription service on the Stacks blockchain. It allows for the creation and management of subscription plans, user subscriptions, and associated financial transactions.

## Features

1. Subscription Plan Management
   - Add new subscription plans
   - Update existing subscription plans
   - Delete subscription plans

2. User Subscription Management
   - Subscribe to a plan
   - Cancel a subscription
   - Renew a subscription

3. Financial Operations
   - Process payments for subscriptions
   - Withdraw funds from the contract

4. Read-only Functions
   - Get subscription plan details
   - Get user subscription details
   - Check if a user's subscription is active

## Contract Functions

### Admin Functions (Contract Owner Only)

1. `add-subscription-plan`: Add a new subscription plan
2. `update-subscription-plan`: Update an existing subscription plan
3. `delete-subscription-plan`: Delete a subscription plan
4. `withdraw-contract-funds`: Withdraw funds from the contract

### User Functions

1. `subscribe-to-plan`: Subscribe to a specific plan
2. `cancel-user-subscription`: Cancel the current subscription
3. `renew-user-subscription`: Renew the current subscription

### Read-only Functions

1. `get-subscription-plan`: Get details of a specific subscription plan
2. `get-user-subscription-details`: Get details of a user's subscription
3. `is-subscription-active`: Check if a user's subscription is active

## Error Codes

- `ERR-OWNER-ONLY (u100)`: Operation restricted to contract owner
- `ERR-NOT-FOUND (u101)`: Requested item not found
- `ERR-ALREADY-EXISTS (u102)`: Item already exists
- `ERR-INSUFFICIENT-BALANCE (u103)`: Insufficient balance for the operation
- `ERR-EXPIRED (u104)`: Subscription has expired

## Usage

1. Deploy the contract to the Stacks blockchain.
2. As the contract owner, add subscription plans using `add-subscription-plan`.
3. Users can subscribe to plans using `subscribe-to-plan`.
4. Users can manage their subscriptions with `cancel-user-subscription` and `renew-user-subscription`.
5. The contract owner can manage plans and withdraw funds as needed.

## Important Considerations

- Only the contract owner can add, update, or delete subscription plans and withdraw funds.
- Users must have sufficient STX balance to subscribe to a plan or renew their subscription.
- Subscription durations and prices are measured in blocks and micro-STX, respectively.
- The contract uses the current block height for tracking subscription start and end times.

## Security

- The contract includes checks to ensure only authorized operations are performed.
- Balance checks are implemented to prevent insufficient fund issues.
- Proper error handling is in place to manage various scenarios.

## Future Improvements

- Implement a grace period for subscription renewals.
- Add functionality for tiered pricing or discounts.
- Implement a referral system or loyalty rewards.