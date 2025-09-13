# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Medieval Stick Fighter is a browser-based 2-player fighting game implemented as a single HTML file with embedded JavaScript and CSS. The game features stick figure characters battling in different arenas with various medieval weapons.

## Architecture

### Single-File Application
The entire game is contained in `index.html` (1292 lines) with:
- Embedded CSS styles for UI and animations
- Complete game logic in vanilla JavaScript
- HTML5 Canvas for rendering

### Core Game Systems

#### Player System (`Player` class)
- Manages character state (position, health, velocity)
- Handles movement physics with gravity and platform collision
- Weapon switching between sword, axe, spear, and mace
- Attack animations and hitbox generation
- Bow aiming and shooting mechanics
- Walking animation cycles

#### Combat System
- Multiple weapon types with unique damage, range, and cooldown values
- Projectile system for arrows with physics simulation
- Hit detection using calculated weapon hitboxes
- Visual hit effects with particle systems
- Stun mechanics on damage

#### Map System
- Three selectable maps: Classic Arena, Platform Battle, Sky Islands
- Platform class for creating floating/cloud platforms
- Dynamic platform collision detection

#### Game States
- Main menu with map selection
- Active gameplay loop
- Game over screen with restart/menu options

## Key Components

### Canvas Rendering (1000x500)
- Background with gradient sky and ground
- Platform rendering with cloud style support
- Character stick figure drawing with animated limbs
- Weapon visualization based on type and attack angle
- Projectile and hit effect rendering

### Physics Implementation
- Gravity system (0.65 acceleration)
- Jump mechanics (power: 15)
- Movement with friction (0.85 multiplier)
- Platform collision with ground detection
- Player-to-player collision with push mechanics

### Input System
- Dual player keyboard controls
- Player 1: WASD for movement, S for attack, Q for weapon switch, E for bow
- Player 2: Arrow keys for movement, Down for attack, / for weapon switch, . for bow

## Development Notes

### Game Balance
- Weapon stats are carefully tuned for variety:
  - Sword: balanced (15 damage, 60 range)
  - Axe: slow but powerful (25 damage, 50 range)
  - Spear: long reach (10 damage, 80 range)
  - Mace: medium stats (20 damage, 40 range)
- Bow deals 12 damage with targeting preview system

### Performance Considerations
- Single game loop using requestAnimationFrame
- Efficient collision detection with early returns
- Particle effects cleaned up when inactive
- Platform collision checks only when necessary

## Running the Game

Simply open `index.html` in any modern web browser. No build process or dependencies required.