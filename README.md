# Production Simulator - Phase 4: Resilience Engineering

This phase focuses on making the system more resilient during failures.

The goal was to simulate how production systems handle faults instead of failing immediately when problems occur.

## Features Implemented

- Circuit Breaker Pattern
- Retry Mechanism
- Recovery Logic
- HALF_OPEN State Handling
- Service Failure Simulation

## How It Works

When repeated failures occur, the Circuit Breaker moves from CLOSED to OPEN state and blocks incoming requests.

After a recovery period, the Circuit Breaker enters HALF_OPEN state and allows a limited test request.

If the test request succeeds, the Circuit Breaker closes and normal traffic resumes.

If the request fails, the Circuit Breaker reopens and continues protecting the system.

## Retry Logic

When a transient failure occurs, the system retries the operation up to 3 times before returning an error.

This helps handle temporary failures without immediately impacting users.

## Learning Outcomes

- Fault Tolerance
- Circuit Breaker Pattern
- Retry Strategies
- Recovery Mechanisms
- Production Resilience Concepts
- State Management

## Example Flow

Service Failure
      ↓
Retry Attempt 1
      ↓
Retry Attempt 2
      ↓
Retry Attempt 3
      ↓
Circuit Breaker Opens
      ↓
Recovery Timer
      ↓
HALF_OPEN State
      ↓
Test Request
      ↓
Success
      ↓
Circuit Breaker Closes
