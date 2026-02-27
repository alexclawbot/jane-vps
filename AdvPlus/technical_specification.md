# Technical Specification - Advantage Plus v1.0.0

## 1. Introduction

### 1.1 Executive Summary

**Project Overview**
Advantage Plus is a production-grade digital loyalty rewards platform providing tiered access to premium lifestyle venues (gyms, beach clubs, pools) across the UAE. Built on:
- PHP 8.3 / Laravel 12.x
- Vue.js 3
- MariaDB 10.11
- Redis 6.2
- Elasticsearch 8.17.2
- Docker + Nginx Unit

**Business Value:**
- Centralized membership management (single membership number across all venues)
- Streamlined booking and digital check-in via PassKit
- 8 payment gateways (including BNPL: Tabby, Tamara)
- Custom CRM (ParasolCRM V2)
- SOC 2 Type I & II ready

### 1.2 System Overview

**User Groups:**
1. **End Members** - Mobile/Web apps, OAuth2
2. **Backoffice Users** - Admin, CRM, RBAC
3. **Sales Team** - Lead management, pipeline
4. **Club Managers** - Check-in, venue ops
5. **External Programs** - API partners

**Key Capabilities:**
- Member lifecycle (registration → renewal)
- Product catalog (Program → Package → Plan hierarchy)
- Venue/Club management
- Booking & reservations
- Check-in via PassKit (Apple Wallet/Google Pay)
- Multi-gateway payment processing (8 providers)
- CRM & Lead management
- Coupon & referral system
- Content management (blogs, pages, FAQs)

### 1.3 Scope

**In-Scope:**
- Member self-service portal
- Booking checkout (4-step)
- Payment orchestration
- Club check-in system
- CRM pipeline
- Reporting & analytics
- 8 payment gateways
- PassKit integration

**Out-of-Scope:**
- Native mobile apps (separate codebases)
- Real-time chat
- Advanced BI/analytics
- Multi-language CMS
- Inventory/POS systems
- ERP/Accounting integration
- White-label deployments

---

## 2. Product Requirements

### Feature Summary

| Feature ID | Feature Name | Priority | Status |
|------------|--------------|----------|--------|
| F-001 | Member Registration & Onboarding | Critical | Completed |
| F-002 | Member Profile Management | High | Completed |
| F-003 | Family Member Management | High | Completed |
| F-004 | Membership Renewal & Lifecycle | Critical | Completed |
| F-005 | Club Information Management | High | Completed |
| F-006 | Club Check-in System | Critical | Completed |
| F-007 | Club Discovery & Search | High | Completed |
| F-008 | Multi-Step Booking Checkout | Critical | Completed |
| F-009 | Booking Management | High | Completed |
| F-010 | Booking Reminders & Notifications | Medium | Completed |
| F-011 | Multi-Gateway Payment Processing | Critical | Completed |
| F-012 | Recurring Payment Management | Critical | Completed |
| F-013 | Payment Refund Processing | High | Completed |
| F-014 | Financial Reporting & Reconciliation | High | Completed |

---

*Document metadata:*
- Version: 1.0.0
- License: MIT
- Target Market: UAE
- Compliance: GDPR, PLPD (UAE Personal Data Protection Law)
