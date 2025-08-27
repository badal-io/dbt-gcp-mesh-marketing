# dbt Mesh Marketing

This is the marketing domain of the Jaffle Shop dbt mesh architecture, responsible for customer and location analytics.

## Overview

This dbt project provides marketing-focused data models and analytics for the Jaffle Shop e-commerce platform. It implements a dbt mesh pattern where this domain owns marketing-related data marts while consuming data from other domains in the mesh.

## Data Models

### Marts (`models/marts/`)

- **customers** - Customer overview data mart with lifetime metrics including order counts, spending totals, and customer segmentation (new vs returning customers). One row per customer.
- **locations** - Store location dimension table with location details, tax rates, and opening dates. One row per location.

## Domain Configuration

- **Domain**: Marketing (`marketing` group)
- **Owner**: Ben Jaffleck (ben.jaffleck@jaffleshop.com)
- **Access Level**: Protected (controlled access to consuming domains)
- **Materialization**: Tables (for performance)

## Dependencies

This project depends on:
- `stg_customers` - Customer staging data
- `orders` - Order transaction data  
- `order_items` - Order line item details
- Cross-domain dependency: `jaffle_shop_mesh_platform.stg_locations` - Location data from platform domain

## Key Features

- Customer lifetime value calculations
- Customer segmentation (new vs returning)
- Location-based analytics
- dbt contracts enforced for data quality
- Comprehensive testing and documentation