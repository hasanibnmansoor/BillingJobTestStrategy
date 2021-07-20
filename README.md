# BillingJobTestStrategy
Test Strategy for Background Billing Job of a Landline Telephone System

## Introduction

## Requirement Readout (Brief)
* Billing Background Job runs 1st of every month. If 1st of a particular month is not a weekday (Mon - Fri), job would run on subsequent working day.
* Billing Job would follow the Timezone, and runs at 12 PM.
* Once the billing background job is run, the bills are generated and notified to customers via email real-time.
* Billing Period of Customers is 1st of previous month - last day of previous month. In case of customers subscribed after 1st, bills would be calculated pro-rata basis.
* For customers subscribing post 25th of each month, combine the bill along with subsequent month's bill. Do not generate bill for the current month. For example, if a customer subscribes to the service by 26th of July, the bill should not be generated for this customer on 1st August. But, on 1st September, bill should be generated for 26/7 - 31/7 + 1/8 - 31/8 period combined.

## Test Scope

## Test Assumptions & Prerequisites

## Test Entry & Exit Criteria

## Testing Types

## Testing Tools

## Automation Strategy

## Test Environment & Data Setup

## Test Scenarios

## Risks and Mitigation

