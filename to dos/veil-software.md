# Veil Software

**Version:** 1.0  
**Date:** January 27, 2026

## Summary
This document outlines the custom software for the Veil concept

The Veil is a head-mounted wearable that allows the wearer to see the outside world through a display AND to project an image of an AI animated face to an external screen mounted over the wearer's face.

Although simple in presentation, this is complex in execution:
-- [ ] Displays the outside world (OW) in a non-vomit-inducing, stereoscopic way
-- [ ] Captures the faces of nearby humans
-- [ ] (May) use onboard compute to transform captured face image to animated one (LivePortrait)
-- [ ] Communicates with external server for possible support for transformation
-- [ ] Displays animated face on external facing screen
-- [ ] Allows the wearer some level of interaction with underlying system
--- [ ] Choose what face to display
--- [ ] Options for tuning the OW view
--- [ ] Switch cameras (optional)

## OW Display
- [ ] **Latency target**: < 20ms motion-to-photon to prevent nausea.
- [ ] **Passthrough Pipeline**:
-- Pull stream from external camera (USB/CSI).
-- Warp/distort for lens correction (barrel distortion for fresnel lenses).
-- Render to internal display (Pixel 7 Pro screen).
- [ ] **Stereoscopic Handling**:
-- If single camera: Duplicate stream to left/right eyes, simulating depth at infinity OR apply shader for fake depth. 
-- If dual camera: Map Cam L -> Eye L, Cam R -> Eye R.
- [ ] **Fail-safe**: If software crashes, pass-through MUST auto-recover or fail to a "transparent" mode (if hardware allows) or clear warning.

## Face Capture
- [ ] **Detection Loop**:
-- Scan for human faces @ > 5fps (background thread).
-- Extract bounding box and landmarks.
- [ ] **Privacy/Ethics** (Optional):
-- Indicator light when recording/processing faces.
- [ ] **Input Source**: 
-- Share main forward-facing camera stream without blocking OW Display pipeline.

## Face Display (The "Veil")
- [ ] **Rendering Pipeline**:
-- **Input**: Source image (the "Avatar" face) + Driving video (captured face landmarks/params).
-- **Process**: LivePortrait (or similar) inference.
--- *Optimization*: INT8 quantization for RPi 5 / Google Coral / NPU.
-- **Output**: 10.1" TFT Screen.
- [ ] **Performance Targets**:
-- Target 24fps for smooth conversation.
-- Fallback: If local inference is too slow, stream params to external server (GPU PC) and receive frames (Latency check!).
- [ ] **Idle State**:
-- When no face detected: Display neutral "Avatar" state or black (to hide screen edges).

## Interaction
- [ ] **Control Interface**:
-- Web UI hosted on RPi (accessible via phone WiFi).
-- OR Physical buttons (GPIO driven).
- [ ] **Features**:
-- **Avatar Selector**: Swipe/Tap to change the "mask" being used.
-- **Calibration**: Adjust OW Display offset/IPD.
-- **System Status**: Battery level, CPU temp, FPS counter.