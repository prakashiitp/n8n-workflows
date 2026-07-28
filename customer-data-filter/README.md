# Customer Data Filter

A simple n8n workflow that retrieves customer records, restructures the data, and filters records based on whether a country value exists.

## Workflow Preview

![Workflow](workflow.png)

## How it Works

1. Manually triggers the workflow.
2. Retrieves customer data from the n8n Training Customer Datastore.
3. Selects and renames important fields.
4. Checks whether the customer has a country value.
5. Routes the data using an IF node:
   - If Country exists → returns Full Name and Email.
   - Otherwise → returns only the Customer ID.

## Features

- Customer data retrieval
- Data transformation
- Conditional routing
- Field selection
- Beginner-friendly workflow

## Tech Stack

- n8n
- Customer Datastore (Training)
- IF Node
- Edit Fields (Set Node)

## Input

Customer records from the n8n Training Customer Datastore.

## Output

- Customers with a country → Full Name + Email
- Customers without a country → Customer ID

## Files

- `workflow.json` — n8n workflow
- `workflow.png` — Workflow preview
