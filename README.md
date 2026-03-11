# User Management Screen - UI Specification

## Overview

This document describes the **User Management Interface** used by administrators to manage system users.  
The interface allows administrators to:

- View existing users
- Add new users
- Enable or disable users
- Assign roles to users
- Filter users

This document defines the UI components and their behavior for developers implementing the interface.

---

# Page Layout

The page is divided into two main sections:

1. **User List Panel (Left Side)**
2. **User Form Panel (Right Side)**

---

# Initial Page State

When the page is loaded:

- The **User List Table** is displayed with all users.
- The **Hide Disabled User** checkbox is checked by default.
- The **New User form is empty**.
- No user is selected.

---

# UI Components

## 1. Add New User Button

Button Label: **+ New User**

### Behavior

When clicked:

- Clears the form on the right side
- Prepares the form for creating a new user
- Enables the **Save User** button

---

# Hide Disabled User Checkbox

Checkbox Label: **Hide Disabled User**

### Behavior

If checked:

- Users with **Enabled = false** will not appear in the table.

If unchecked:

- All users are displayed.

---

# User List Table

The table displays the existing users.

### Columns

| Column | Description |
|------|-------------|
| ID | Unique user identifier |
| User Name | System username |
| Email | User email address |
| Enabled | Indicates whether the user is active |

### Behavior

- Clicking a row loads that user's data into the **User Form Panel**
- Selected row becomes highlighted

---

# User Form Panel

Used for **creating or editing users**.

### Fields

**Username**

Text input  
Required field

---

**Display Name**

Text input  
Required field

---

**Phone**

Text input  
Optional field

---

**Email**

Text input  
Required field  
Must contain valid email format

---

**User Roles**

Dropdown selection.

Possible values:

- Guest
- Admin
- SuperAdmin

Multiple roles may be supported depending on system configuration.

---

**Enabled**

Checkbox

- Checked → User is active
- Unchecked → User is disabled

---

# Save User Button

Button Label: **Save User**

### Behavior

When clicked:

1. Validate all required fields
2. If validation fails:
   - Show error message
3. If validation succeeds:
   - Save the user
   - Update the user list table
   - Display success notification

---

# Validation Rules

| Field | Rule |
|-----|------|
Username | Cannot be empty |
Display Name | Cannot be empty |
Email | Must be valid email format |

---

# Notifications

System messages should be displayed for:

- Successful user creation
- Successful user update
- Validation errors
- System errors

---

# Summary

The **User Management Screen** allows administrators to efficiently manage system users through a simple interface including:

- User listing
- User creation
- Role assignment
- User activation control
