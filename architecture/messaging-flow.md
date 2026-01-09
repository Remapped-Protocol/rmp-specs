# Messaging verification flow

## Design objective
Enable message integrity and verification in degraded, offline, or adversarial environments.

RMP does not store message content on-chain.
Instead, it stores minimal attestations that allow later verification.

## High-level flow
1. A user/device produces a message payload (off-chain)
2. The message is signed (off-chain)
3. The signed message is transported via any channel (offline/delay-tolerant allowed)
4. An attestation is written on-chain (hash/metadata, not content)
5. Any party can verify the message later using the signature + chain attestation

## What is on-chain
- Minimal attestation records (e.g., hashes, timestamps/sequence, issuer identifiers)
- No plaintext message content

## What is off-chain
- Message content and transport
- Signature generation and storage
- Store-and-forward delivery mechanisms

## Non-goals
- On-chain message storage
- Monetizing access to messaging
- Token-gated messaging privileges
