# ASG Airlines — End-to-End Data Engineering Pipeline

## Project Overview

This project implements an end-to-end data engineering pipeline for ASG Airlines flight, booking, passenger, and payment data.

The pipeline covers data ingestion, data quality assessment, cleaning, standardization, transformation, analytical data modelling, KPI analysis, and Power BI dashboard development.

## Dataset

The source dataset contains four related tables:

- Flights
- Bookings
- Passengers
- Payments

The relationships are based on flight ID, passenger ID, and booking ID.

## Data Engineering Pipeline

Data Ingestion
→ Data Profiling
→ Data Cleaning
→ Data Standardization
→ Data Transformation
→ Analytical Data Model
→ KPI Analysis
→ Power BI Dashboard

## Data Quality and Cleaning

The following issues were identified and handled:

- Missing airline values
- Missing payment amounts
- Missing and invalid booking statuses
- Exact duplicate flight records
- Duplicate/conflicting flight IDs
- Invalid flight timestamp
- Passenger records with missing last names
- Repeated passenger IDs with conflicting details
- Invalid payment amounts
- Text and date standardization

The invalid flight timestamp for flight SJ192 was corrected using its recorded flight duration.

Conflicting flight ID 6F250 was flagged as ambiguous rather than guessing which record was correct.

## PII Protection

The dataset contains sensitive passenger and booking information including Aadhaar numbers, passport numbers, phone numbers, email addresses, and emergency contact details.

Sensitive raw data was excluded from the GitHub repository. Analytical datasets were minimized to the fields required for reporting.

## Analytical Model

The main analytical table is `fact_bookings`.

Supporting tables include:

- `dim_flights`
- `dim_passengers`
- `dim_payments`

The booking table acts as the central business-event table connecting flights, passengers, and payments.

## Key KPIs

The final analytical model provides:

- Total flights
- Total bookings
- Total routes
- Average flight duration
- Average booking amount
- Total revenue
- Airline distribution
- Route traffic
- Booking status distribution
- Booking lead-time analysis
- Data-quality and anomaly indicators

## Power BI Dashboard

The Power BI report contains:

### Executive Overview
Provides KPI cards, airline distribution, booking status, booking lead-time analysis, and interactive filters.

### Route & Duration Analysis
Provides top route performance, average duration by airline, duration categories, and airline filtering.

### Data Quality & Anomaly Insights
Highlights missing payments, missing booking statuses, ambiguous flight IDs, overnight flights, and other data-quality observations.

The dataset does not contain scheduled versus actual flight times, so a reliable delay KPI could not be calculated.

## Tools Used

- Python
- Pandas
- OpenPyXL
- Jupyter Notebook
- Power BI
- Git/GitHub

## Project Files

- `01_data_inspection.ipynb` — data inspection, cleaning, transformation, and analytical preparation
- `ASG_Airlines_Dashboard.pbix` — Power BI dashboard
- `data/processed/` — processed analytical datasets
- `requirements.txt` — Python dependencies
- `documentation/` — project documentation

## Final Outcome

The project produces clean, structured, analytical-ready airline data and an interactive Power BI dashboard for operational and business analysis.