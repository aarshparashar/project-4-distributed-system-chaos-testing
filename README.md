# Distributed System with Chaos Testing

This project is a realistic distributed microservices platform designed to demonstrate reliability engineering, fault tolerance, and chaos testing workflows. It focuses on systems thinking and graceful degradation under failure scenarios.

## System Architecture

The platform consists of several core microservices communicating via HTTP/gRPC:
1.  **API Gateway / Frontend**: Routes incoming traffic and handles basic rate limiting and authentication.
2.  **Worker Service**: Processes asynchronous tasks and background jobs.
3.  **State/Metadata Store**: Manages persistent data with eventual consistency and reconciliation mechanisms.

## Resilience Engineering

The services are built with robust failure-handling mechanisms:
*   **Circuit Breakers**: To prevent cascading failures when downstream services degrade.
*   **Retries with Exponential Backoff**: To handle transient network issues safely.
*   **Timeouts & Idempotency**: Ensuring requests don't hang indefinitely and safe retry execution.

## Chaos Engineering Framework

The repository includes a dedicated `chaos` module to actively test the system's resilience by injecting failure modes:
*   Pod/Process termination (simulating OOM kills or node crashes)
*   Network latency and packet loss injection
*   CPU/Memory pressure

## Local Deployment

*(Instructions for local Kubernetes cluster deployment via Kind or Minikube will be added here)*

## Testing & CI/CD

The CI/CD pipeline automates integration tests alongside configured chaos tests to ensure code changes do not regress the system's overall reliability score.
