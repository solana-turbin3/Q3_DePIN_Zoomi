# Zoomi – A DePIN powered smart scooter Rental System

## High Level Description
This project is a DePIN-powered smart scooter rental system that enables 24/7 self-service vehicle access without relying on shopkeeper's time availability. Instead of waiting for a rental shop to open, riders can simply scan a QR code on a scooter, unlock it via an IoT device, pay the rent and deposit the extra collateral and start riding instantly.

## Basic System Integrations
1. **IoT Hardware Devices** - ESP32, GPS (NEO-6M), relay modules, and a 12V solenoid lock to physically secure the scooter via the underseat and also enables real-time tracking through NEO-6M.

2. **Smart Contract** – built on solana to ensure secure payments, deposits, and automated penalties if the rider exceeds the rental period.

3. **Shopkeeper/Fleet Owner Dashboard** - allows shopkeepers to register scooters, monitor rentals in real-time, fueling of the vehicles, and receive payments directly without disputes.

## Value Proposition
- **For Riders**: Instant, keyless scooter rentals anytime, without waiting for shopkeepers.
- **For Shopkeepers**: Automated rental system with secure payments, penalties, and tracking → no manual disputes.
- **For the Network (DePIN)**: Scooters become nodes in a decentralized network, earning rewards for availability and usage of the vehicles and penalizing the users.

## User Stories

### Direct Users (day-to-day)
- **Riders/Customers** → people renting scooters via QR/app.
- **Shopkeepers/Fleet Owners** → owners of scooters who list them on the network.
  - *Responsibilities*: Maintaining vehicles (fuel, cleaning)

### Indirect Users / Beneficiaries
- **Local Communities** → benefit from easier mobility, especially at odd hours when shops are closed.
- **Businesses/Restaurants/Tourism Spots** → increased foot traffic due to easy access to scooters.
- **Urban Planners/Smart Cities** → can use aggregated usage data to design better infrastructure.
- **Delivery Workers/Gig Riders** → who may use these scooters for quick, short-term rentals.

### Administrators / Moderators
- **Platform Developers** → maintain IoT firmware, backend, and smart contract.
- **System Admins** → handle fraud detection, network monitoring, and emergency overrides.
- **Hardware Maintenance Technicians** → ensure solenoid locks, GPS, and IoT devices are functioning on scooters.

### Stakeholders
- **Investors/Token Holders** → fund the project and benefit from network growth.
- **Insurance Providers** → who may offer coverage for scooters or riders.
- **Payment Processors (UPI, Stripe, Crypto Gateways)** → who facilitate fiat + crypto transactions.
- **Government/Regulators** → who care about compliance, transport laws, and taxation.
- **IoT Hardware Vendors** → suppliers of solenoids, GPS modules.
- **Fleet Financing Companies** → who might fund scooters for shopkeepers and benefit from automated income streams.

## Future Considerations
- **Integrate with Aggregators/Platforms (Ola, Uber, Rapido)** → who may integrate and offer the rentals under their umbrella. Value proposition: Ability to onboard local shops into their fleet, expanding supply with minimal capital investment and also reducing operational costs.
- **EV Charging Providers (if extended to EV scooties)** → could integrate for automated charging payments.

