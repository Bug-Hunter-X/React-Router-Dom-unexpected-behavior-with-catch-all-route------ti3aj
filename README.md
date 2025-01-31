# React Router Dom Issue: Catch-all Route Unexpected Behavior

This repository demonstrates an unexpected behavior in React Router Dom v6 where a catch-all route (`/*`) overrides other routes, even the home route (`/`).

## Problem

The issue occurs when a catch-all route is defined in `Routes` alongside other specific routes. It unexpectedly catches all routes, including the home route, leading to the catch-all component always being rendered.

## Solution

The solution is to place the catch-all route at the end of the routes array, to make sure the more specific routes are checked first.  We also ensure that the `path` property is properly set to the correct path.

## How to Reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.

You will observe that navigating to any path always leads to the `Not Found` component.

## How to Fix

Refer to the solution branch for a correct implementation. The key change is to reorder the routes in `Routes` component, to specify the `/*` route only after more specific routes are specified.