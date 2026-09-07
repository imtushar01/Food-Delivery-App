# FoodDeliveryApp — Low-Level Design (C++)

A compact C++ project demonstrating low-level design (LLD) for a food delivery application. This repository contains core domain models, factories, managers, strategies, and services illustrating common design patterns used in real-world systems (Factory, Strategy, Manager/Controller, etc.).

## Contents
- **Overview:** high-level goals and patterns.
- **Build & Run:** how to compile and execute a simple demo.
- **Project Structure:** summary of folders and key headers.
- **Usage & Extending:** how to add new components.

## Overview

This educational project models a simplified food-delivery system focusing on object-oriented design and clean separation of concerns. Important concepts shown:

- Domain models (`models/`) for `User`, `Restaurant`, `Order`, `MenuItem`, `Cart`, and order variants.
- Factory pattern for creating different `Order` types (`factories/`).
- Manager classes (`managers/`) to coordinate business logic.
- Payment `Strategy` implementations in `strategies/` (e.g., UPI, credit card).
- Notification service abstraction in `services/`.

Use this repository as a learning reference, a starting point for interviews, or a base for adding system-level features like persistence, networking, or a UI.

## Project Structure

Top-level files:

- `main.cpp` — entrypoint / small demo harness.
- `TomatoApp.h` — app-level glue (demo-specific).

Directories:

- `models/` — domain classes: `Cart.h`, `DeliveryOrder.h`, `MenuItem.h`, `Order.h`, `PickupOrder.h`, `Restaurant.h`, `User.h`.
- `factories/` — `OrderFactory.h`, `NowOrderFactory.h`, `ScheduledOrderFactory.h`.
- `managers/` — `OrderManager.h`, `RestaurantManager.h`.
- `services/` — `NotificationService.h`.
- `strategies/` — `PaymentStrategy.h`, `UpiPaymentStrategy.h`, `CreditCardPaymentStrategy.h`.
- `utils/` — utility helpers like `TimeUtils.h`.

If you add new files, follow the existing folder responsibilities: models for state, factories for creation, managers for orchestration, strategies for interchangeable behaviors, and services for infrastructure concerns.

## Build & Run

This project is a header-heavy C++ demo. The simplest way to build and run the demo (macOS / Linux) is with `g++` or `clang++`.

1. From the repository root, compile with C++17 or later:

```bash
g++ -std=c++17 -I. main.cpp -o FoodDeliveryApp
```

2. Run the produced binary:

```bash
./FoodDeliveryApp
```

Notes:

- If your compiler or include setup requires source files split across compilation units, compile each `.cpp` and link them together.
- For IDEs (CLion, VS Code), open the folder and configure a C++ toolchain; include paths should contain the repo root so headers resolve.

## Usage

- Inspect `main.cpp` and `TomatoApp.h` to see a minimal demonstration of object composition and the app flow.
- Create or extend orders via the factories in `factories/`.
- Add payment methods by implementing `PaymentStrategy` in `strategies/` and register them where payments are processed.

## Extending the Project

Possible improvements and experiments:

- Add persistence (SQLite, files) for users, restaurants, and orders.
- Add a networked API layer (REST/gRPC) and a simple frontend.
- Implement an event/notification queue for `NotificationService`.
- Add unit tests (Google Test) and CI configuration.

## Contributing

Contributions are welcome. Open an issue to discuss design changes or send pull requests with focused, well-documented changes.

## License

This repository is provided for educational purposes. Add a license file (e.g., `LICENSE`) if you intend to publish or share the code.

---

If you'd like, I can:

- Add a `CMakeLists.txt` or simple Makefile for reproducible builds.
- Create a small test harness or example run showing typical flows.

Tell me which of those you'd like next.
