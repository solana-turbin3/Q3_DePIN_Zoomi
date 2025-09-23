# Zoomi 
(in progress)

## High Level Description
This project is a DePIN-powered smart scooter rental system that enables 24/7 self-service vehicle access without relying on shopkeeper’s time availability. Instead of waiting for a rental shop to open, riders can simply scan a QR code on a scooter, unlock it via an IoT device, pay the rental fee and deposit the collateral to start riding.


## User Stories and Data Flow
*Main Users*
1. Riders / Costumers
2. Shopkeepers / Fleet Owners

*Rider Use Case*
1) Rider Scans QR Code on selected Scooter
2) QR code sends rider to Website where:
    - user setup account and Verify ID / KYC (if account does not exists)
    - user select time period to rent scooter (scooter ID is fetched from QR code link)
    - 

*Shopkeepers Use Case*


## System Overview
1) Hardware Device to physically secure the scooter and unlock upon payment, enabling real-time GPS tracking
2) Solana Smart Contract
3) Dashboard to allow riders to create account and fleet owners to register scooters and monitor rentals in real-time


### Hardware Device

1) Hardware Requirements:

- ESP32 with wifi connectivity
- GPS module NEO-6M
- Buzzer
- Solenoid lock 12V
- Relay Module 5V
- 12V Battery

2) Hardware Schematics:


3) Software Requirements:

4) Software Architecture:
State Machine



### Solana Protocol

1) State accounts

*Rider Account*
```rust
pub struct Rider {
    pub wallet: Pubkey,         // user wallet address
    pub id_status: bool,        // KYC verification status
    pub points: u32,            // TBD: total points gained ?? (from rentals)
    pub penalties: u32,         // TBD: record history of total rentals with penalties ??
}
```
- PDA derived from wallet + "zoomi"
(or other derivation from ID hash or something to make it only possible one account per user, not per wallet)
- Rider pays for initialization and needs to provide proof of identity via a 3rd-party KYC app that is processed on the backend server and provides a boolean of the verification status that is stored on the account

*Scooter Account*
```rust
pub struct Scooter {
    pub id: u32,                // Scooter id ??
    pub owner: Pubkey,          // Scooter owner
    pub price_tier: u8,         // Princing tier
    pub drop_area_list:         // TBD ?? do we need something like this ?
}
```
- PDA derived from id + "scooter"
- Owner pays for initialization account

*Rental Account*
```rust
pub struct Rental {
    pub rider: Pubkey,          // Rider wallet
    pub scooter_id: Pubkey,     // Scooter Id
    pub start_time: i64,        // Rental start time
    pub end_time: i64,          // Rental end time (as per prepaid to escrow)

}
```
- PDA derived from Rider wallet and Scooter id
- Account is initialized at the moment of rental, payed by the rider and close at the end of rental contract if all is successful

*Escrow State Account*
```rust
pub struct Rental {
    pub rider: Pubkey,          // Rider wallet
    pub scooter_owner: Pubkey,  // Scooter owner wallet
    pub amount: u64,            // Amount of the rental period
    pub collateral: u64,        // Amount of the collateral

}
```