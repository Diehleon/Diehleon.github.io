---
title: "Low-Power ESP32 Sensor Node"
designator: "PRJ-001"
date: 2026-05-14
status: "Shipped"
summary: "Battery-powered environmental logger that wakes on a timer, publishes over MQTT, and runs eleven months on a single 18650."
tags: ["ESP32", "ESP-IDF", "MQTT", "Low power"]
mcu: "ESP32-C3"
toolchain: "ESP-IDF v5.2"
repo: "https://github.com/Diehleon"
# cover: /assets/img/sensor-node.jpg
specs:
  - label: "Sleep current"
    value: "14 µA"
  - label: "Uplink"
    value: "Wi-Fi / MQTT"
---

This is a sample entry so you can see the layout working. Delete this file once you've
added a real project — or copy it and overwrite the fields.

## The problem

Start with what wasn't working before this existed. One short paragraph is enough.
Readers decide whether to keep going based on this section.

## Design

Explain the decisions you made and why. This is the part hiring managers actually read —
it shows how you think, not just what you built.

- **Power budget first.** Every part was chosen against a µA budget before anything was routed.
- **Deep sleep between samples.** The RTC timer drives the wake cycle; the radio only comes up when there's a payload.
- **Watchdog on the network stack.** A failed association reboots rather than hanging.

## Firmware

```c
// Configure the wake timer and drop into deep sleep.
esp_sleep_enable_timer_wakeup(SAMPLE_PERIOD_US);
esp_deep_sleep_start();
```

## Results

Give numbers if you have them: current draw, uptime, throughput, cost per unit. Numbers
make a project credible in a way adjectives never do.

## What I'd change

Being honest about limitations reads as confidence, not weakness. Name the one thing
you'd fix in the next revision.
