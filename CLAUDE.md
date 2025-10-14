# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a standalone investment calculator web application built as a single HTML file with embedded CSS and JavaScript. It calculates and visualizes monthly income potential based on investment parameters.

## Architecture

**Single-file structure**: [investment-calculator.html](investment-calculator.html) contains the entire application:
- HTML structure with responsive grid layout
- CSS styling with mobile-first design
- Vanilla JavaScript with OOP pattern (InvestmentCalculator class)
- Custom canvas-based charting implementation (no external dependencies)

**Core calculation logic**:
- `calculateTotalCapital()` (lines 157-166): Implements compound interest formula for monthly contributions
- `calculateInvestmentData()` (lines 137-155): Generates 30-year projection dataset
- Formula: FV = PMT × ((1 + r)^n - 1) / r, where r is monthly rate and n is total months

**Chart rendering**: Custom canvas drawing methods:
- `drawAxes()`: X-axis (years) and Y-axis (€ income)
- `drawData()`: Line chart with filled area and data points
- `drawLabels()`: Axis labels with proper positioning

## Development

To run the application:
```bash
# Open directly in browser
open investment-calculator.html

# Or serve with a local server
python3 -m http.server 8000
# Then navigate to http://localhost:8000/investment-calculator.html
```

The application has no build process, dependencies, or compilation steps.

## Key Implementation Details

- Real-time updates: Chart redraws on any input change
- Responsive: Grid layout collapses to single column on mobile (<768px)
- Calculation range: 1-30 years of saving
- Currency: Euro (€) hardcoded in display
- Default values: 10% annual return, €300 monthly savings
