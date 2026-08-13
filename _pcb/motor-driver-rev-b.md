---
title: "Dual H-Bridge Motor Driver — Rev B"
designator: "PCB-004"
date: 2026-04-02
status: "Fabricated"
summary: "Four-layer 12 V dual motor driver with current sensing, isolated logic, and a thermal pour that survived the stall test."
tags: ["KiCad", "4-layer", "Power", "DRV8871"]
layers: "4 (Sig / GND / PWR / Sig)"
dimensions: "62 × 45 mm"
eda: "KiCad 8"
repo: "https://github.com/Diehleon"
# cover: /assets/img/motor-driver.jpg
specs:
  - label: "Input"
    value: "9–16 V"
  - label: "Continuous"
    value: "3.6 A / channel"
---

Sample board entry — replace it with one of your own designs.

## Requirements

State the constraints the board had to meet: voltage rails, current, board outline,
connector positions, cost target. Constraints are what make layout decisions interesting.

## Schematic

Walk through the blocks: power input and protection, regulation, the driver stage,
sensing, and the logic interface. Note anything non-obvious — a snubber, a sense-resistor
placement, a deliberate part substitution.

## Layout notes

| Concern | Approach |
| --- | --- |
| Thermal | Copper pour tied to the driver pad with a 3 × 3 via stitch |
| Noise | Star ground at the sense resistor return |
| Assembly | All hand-solderable packages; no BGA |

## Rev A → Rev B

The most useful thing you can publish is what went wrong. List the failures found on the
first spin and what changed because of them.

## Fabrication

Fab house, stack-up, finish, quantity, and cost per board. Add photos of the bare and
assembled board to the `gallery` field in the front matter.
