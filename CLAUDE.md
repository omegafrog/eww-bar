# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an Eww (ElKowars wacky widgets) configuration for creating a custom status bar in Hyprland window manager. Eww is a widget system that allows creating desktop widgets using a Yuck configuration language and CSS styling.

## Architecture

- `eww.yuck` - Main configuration file defining widgets, windows, and listeners
- `eww.css` - Styling for the widgets with a lion-themed color scheme
- `scripts/` - Helper scripts for dynamic data collection
  - `get-workspaces` - Monitors Hyprland workspace changes via socket
  - `get-active-workspace` - Tracks currently active workspace

## Key Components

### Workspace Widget
The main functionality is a workspace switcher that:
- Displays available Hyprland workspaces as clickable buttons
- Shows active workspace with distinct styling (gold color)
- Monitors workspace changes in real-time via Hyprland sockets
- Uses `deflisten` for live updates without polling

### Bar Layout
- Left section: workspace indicators
- Center section: placeholder for future widgets
- Right section: placeholder for future widgets

## Common Commands

### Development and Testing
```bash
# Start eww daemon
eww daemon

# Open the bar window
eww open bar

# Reload configuration after changes
eww reload

# Close all windows
eww close-all

# Kill daemon
eww kill

# Watch logs for debugging
eww logs

# Test configuration syntax
eww debug bar
```

### Development Workflow
1. Make changes to `eww.yuck` or `eww.css`
2. Run `eww reload` to apply changes to running widgets
3. Use `eww logs` to debug any issues
4. Test interactivity with `eww debug` for widget structure

## Dependencies

- Eww widget system (installed at `/home/jiwoo/.local/bin/eww/eww`)
- Hyprland window manager
- `jq` for JSON processing in scripts
- `socat` for socket communication
- `hyprctl` for Hyprland commands

## Color Scheme

Lion-themed colors defined in CSS:
- Background: `#1C1C1C` (lion-black)
- Text: `#F5F5DC` (lion-cream)
- Active workspace: `#D4AF37` (lion-gold)
- Workspace buttons: `#2F2F2F` (lion-dark-gray)
- Hover state: `#8B4513` (lion-dark-brown)