# Next.js 15 App Router JSON.parse Error

This repository demonstrates a common error encountered when using the App Router in Next.js 15, specifically when parsing JSON from `localStorage` in a way that isn't compatible with the app directory's client-component hydration process.  The error message is typically "Failed to parse JSON: Unexpected token 'n' in JSON at position 0".

## Problem

The issue arises because `localStorage.getItem('user')` might return `null` if the item is not present.  Directly parsing `null` with `JSON.parse()` throws an error.  The solution requires careful handling of this edge case.

## Solution

The provided solution modifies the code to check for null before attempting to parse the JSON, thereby preventing the error.

## Setup

1. Clone this repository.
2. Run `npm install`.
3. Run `npm run dev`.
