# Veil Mechanical

**Version:** 1.0  
**Date:** January 27, 2026

## Summary
This document outlines the physical components and related stuff for the Veil concept

The Veil is a head-mounted wearable that integrates:
- At least one external forward facing camera
- Internal display w/ lenses for projecting outside world
- External LCD screen for displaying faces, etc
- At least one compute device for orchestrating these components
- At least one physical interface for interacting with compute device

## Head
- [ ] Design/build an adjustable frame that can:
-- Comfortably mount on wearer's head
--- Adjustability (inspiration from OR REUSE of a VR headset 'pro' strap)
---- Primarily Worm gear straps
--- Padding
-- [ ] Support .5kg of screens and associated framing (see Shield) over wearer's face
--- Mount points
--- Counterbalance and/or other measures to alleviate fatigue and poor ergonomics
-- [ ] Support compute infrastructure
--- Mount points
--- Wiring conduit
-- [ ] Allows the face-covering componentry to be swiveled up (like a visor)
--- Ball-bearing swivel system https://www.printables.com/model/1056534-detent-with-spring-and-bearing

## Shield
- [ ] Design/build an adjustable frame that can:
-- Be positioned comfortably/accurately on wearer's face
-- [ ] Mount a pixel 7 pro (or similar screen + driver)
--- In front of the wearer's face
--- Easily removed/installed into the Shield
--- Supports power/USB wiring
--- Flat to fresnel lense viewer (no blur)
-- [ ] Mount a stereoscopic (or single lense) camera
--- Above the external facing screen
--- Supports USB wiring to compute
-- [ ] Mount a 10.1" TFT screen
--- Covers wearer's face
--- Supports wiring to driver and display cable to compute

## Infrastructure 
- [ ] Design/build framing that can support the following
-- 10000mAh battery
-- Compute device (raspberry Pi 5)
-- Wiring for
--- Compute 
--- 2x screens
--- 2x driver boards
--- Battery
--- USB Hub 
-- [ ] Comfortable/safe for wearer

## Considerations

### Weight & Ergonomics
- **Risk**: "0.5kg of screens" + RPi 5 + Battery (~200g) creates a very front-heavy device.
- **Mitigation**: Mount the battery and RPi 5 on the back of the head strap to act as a counterweight.
- **Swivel**: Ensure the ball-bearing swivel hinge has sufficient torque/friction to hold the heavy "Shield" in the "up" position without drooping.

### Heat Management
- **Risk**: RPi 5 runs hot; enclosing it or placing it near the head requires thermal management.
- **Mitigation**: Incorporate vent slots or active cooling (small fan) in the framing.

### Power & Wiring
- **Risk**: Powering Pixel 7 Pro, 10.1" TFT, RPi 5, and cameras from a single 10000mAh battery may limit runtime or exceed peak amperage.
- **Mitigation**: Verify peak amperage draw (RPi 5 ~5A). Ensure battery supports high-output PD.

### Optical Path
- **Risk**: "Flat to fresnel lense viewer" alignment with a phone screen is optically complex (IPD, focal length).
- **Mitigation**: Consider reusing an existing VR phone shell/insert for the optics/mounting and building the Veil frame around it to ensure visual clarity.

### Manufacturing (3D Printing)
- **Materials**: 
    - Avoid PLA for parts near the compute/face due to heat deformation (softens at ~60°C).
    - Use **PETG** or **ASA** for structural parts (higher heat resistance, some flex).
    - Use **TPU** (flexible) for any face-contact interfaces if not using foam.
- **Structural**:
    - The "swivel" mechanism is a high-stress point. Print horizontally for layer adhesion strength or use **metal inserts** (heat-set inserts, bearings) rather than relying on plastic threads/friction.
- **Weight Optimization**:
    - Use **Gyroid infill** (10-15%) to maximize strength-to-weight ratio.
    - Increase wall count (3-4 perimeters) rather than infill percentage for rigidity.