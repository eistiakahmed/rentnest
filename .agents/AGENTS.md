# RentNest Development Guidelines & Rules

## Project Scope
RentNest is a Next.js App Router application for a rental property marketplace with 3 roles: TENANT, LANDLORD, and ADMIN.

## Core Rules & Architecture
1. **Styling & Aesthetics**:
   - Built using Tailwind CSS v4 with modern, vibrant, dark/light mode adaptable colors, sleek cards, glassmorphism accents, and smooth hover micro-animations.
   - Using Google Font (Inter/Outfit) aesthetics, clean typography, dynamic status badges, and skeleton loading states.
2. **Component Architecture**:
   - Reusable UI primitives live in `src/components/ui/` (`button.tsx`, `input.tsx`, `select.tsx`, `badge.tsx`, `avatar.tsx`, `modal.tsx`, `card.tsx`).
   - Shared layout components live in `src/components/layout/` (`Navbar.tsx`, `Footer.tsx`, `ProfileDropdown.tsx`, `DashboardSidebar.tsx`, `DashboardHeader.tsx`).
3. **Role-Based Access & Dynamic UI**:
   - Dynamic navbar & profile avatar dropdown adapt based on active user role (`TENANT`, `LANDLORD`, `ADMIN`).
   - Status Badges use standard color coding:
     - `PENDING`: Yellow / Amber (`bg-amber-100 text-amber-800 border-amber-300`)
     - `APPROVED`: Blue (`bg-blue-100 text-blue-800 border-blue-300`) -> Shows "Pay Now" CTA for tenants.
     - `REJECTED`: Red (`bg-rose-100 text-rose-800 border-rose-300`)
     - `ACTIVE`: Green (`bg-emerald-100 text-emerald-800 border-emerald-300`) -> Shows "Leave Review" CTA for tenants.
     - `COMPLETED`: Gray (`bg-slate-100 text-slate-800 border-slate-300`)
     - `BANNED`: Red badge in admin tables.
4. **TypeScript & API Integration**:
   - Strict typing for `User`, `Property`, `RentalRequest`, `Payment`, and `Review`.
   - Next.js middleware and route handlers handle role protection and backend API communication.
