# StitchSync

An offline-first command center engineered for cosplayers, prop builders, and convention attendees to track event schedules, budget limits, and cosplay crafting progress.

## Overview

Navigating convention season requires juggling multi-piece costume builds, managing tight material budgets, and navigating severe cellular dead zones inside convention centers. 

StitchSync solves this by serving as a dedicated mobile client built on a local-first storage architecture. All active crafting progress, event lineups, and reference materials remain fully accessible offline and synchronize automatically with a Salesforce backend engine once network connectivity is restored.

## System Architecture

StitchSync is built using a 3-tier hybrid enterprise stack:

* **Mobile Frontend (`/mobile-client`):** Built with React Native and Expo. Implements a local storage cache to guarantee zero-latency offline access on convention floors.
* **Backend Data Engine (`/salesforce-core`):** Powered by the Salesforce Platform utilizing custom objects under the `CSPLN_` metadata package namespace. Handles complex budget rollups, task completion metrics, and custom Apex REST API endpoints optimized for mobile payloads.
* **Middleware & Data Ingestion (`/data-scraper`):** A Node.js background service using JSForce to aggregate, normalize, and ingest public convention event schedules directly into Salesforce.

## Key Technical Features

* **Offline-First Synchronization:** Local client-side caching guarantees uninterrupted access to lineups and references during network outages.
* **Dual-Mode Build Tracking:** Flexible tracking supporting both high-level outfit planning (Simple Mode) and granular itemized expense/task breakdowns (Advanced Mode).
* **Isolated Package Namespace:** Clean metadata separation utilizing strict `CSPLN_` naming standards for enterprise platform stability.
