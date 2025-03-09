# **Employee Rotation Schedule - Frontend Development Guide**

## **Overview**

This frontend web application manages employees on a rotating schedule, allowing both employees and managers to log in, view schedules, and manage requests. The application includes a feature that allows employees to define their **unavailable times** (e.g., only available for night shifts), which helps managers avoid conflicts while assigning shifts. Additionally, employees can modify their unavailable times, and managers will receive a pop-up alert if they attempt to assign shifts during these restricted times.

---

## **Key Features**

- **Employee and Manager Logins**
  - Employees can view their schedules and manage requests.
  - Managers can create, modify schedules, manage holiday requests, and assign roles to employees (including managerial roles).
  
- **Unavailable Times for Employees**
  - **Employees** must define their unavailable times during **account creation** (e.g., night shift only).
  - Employees can update their unavailable times from their profile page at any time.
  - **Managers** can still assign shifts during unavailable times, but a **pop-up alert** will notify them of conflicts.

- **Notifications for Schedule Updates and Requests**
  - **Employees** will be notified of schedule updates and request changes.
  - **WhatsApp/Email** notifications will initially be used, transitioning to a mobile app notification system in the future.

- **Logout Functionality**
  - **/logout** - Secure logout for all users.

---

## **Routes Guide**

### **Authentication**

- **/login** - Login page for both employees and managers.
- **/register** - Registration page for employees, including defining unavailable times during sign-up.
- **/forgot-password** - Allows users to reset their password.
- **/logout** - Secure logout for users.

---

### **Dashboard**

- **/dashboard** - Main dashboard after login.
  - **Employee View**: Displays the employee's schedule, pending requests, and the option to update unavailable times.
  - **Manager View**: Displays an overview of employee schedules, pending requests, team status, and managerial functions.

---

### **Schedules**

- **/schedule** - View weekly/monthly schedule.
  - **Employee**: View their shifts and request changes.
  - **Manager**: View and modify shifts for all team members.
  
- **/schedule/manage** - **(Manager Only)** Modify schedules, assign shifts, and review employees’ unavailable times.
- **/schedule/notifications** - View notifications for schedule updates, changes, and new shifts.

---

### **Requests**

- **/requests/holidays** - Employees can request holidays; managers can approve or reject requests.
- **/requests/schedule-change** - Employees can request schedule changes; managers can approve or reject requests.
- **/requests/pending** - Managers can view all pending holiday and schedule change requests.

---

### **User Management**

- **/profile** - User profile page to update email, phone number, and manage unavailable times.
  - Employees can define and edit their unavailable times (e.g., only available for night shifts).
  
- **/team** - **(Manager Only)** View and manage employee roles and promote employees to managerial roles.
- **/team/manage** - Promote/demote employees to managers and review their unavailable times for shift assignments.

---

### **Notifications & Communication**

- **/notifications** - View notifications related to schedule changes, approvals, and updates.
- **/contact** - Employees can reach out to managers via a messaging system for scheduling queries or support.

---

## **Development Notes**

### 1. **Authentication System**
   - Implement **session persistence** and **role-based authentication** (JWT or cookies).
   - Ensure proper **logout functionality** to clear sessions.

### 2. **State Management**
   - Use **React Context** or **Redux** to manage state across the frontend.
   - Maintain the state for employee schedules, requests, and availability.

### 3. **Responsive Design**
   - Ensure compatibility across all devices, focusing on a **mobile-first approach** for accessibility.

### 4. **Unavailable Times Handling**
   - **Employee Account Creation**: Prompt employees to define their unavailable times.
   - **Profile Management**: Allow employees to edit unavailable times.
   - **Manager's View**: Display employees’ unavailable times and prevent schedule conflicts, notifying managers via pop-up alerts.

### 5. **API Integration**
   - Fetch all data dynamically from the backend API for schedules, requests, and user management.
   - Integrate external APIs for **WhatsApp/Email notifications**.

### 6. **Security Considerations**
   - Protect routes to ensure that only authorized users can access sensitive data and perform certain actions (e.g., modifying schedules).

---

## **Future Enhancements**

1. **Mobile App Integration**
   - Transition notifications to the mobile app for enhanced access and real-time updates.

2. **Automated Shift Recommendations**
   - Implement intelligent recommendations for shifts based on employees’ availability and preferences.

3. **Analytics for Work Hours and Performance**
   - Track work hours, shift patterns, and performance metrics for manager reviews.

---

This guide outlines the complete structure and development considerations for creating a frontend solution for employee schedule management. The platform ensures a smooth experience for both employees and managers, making scheduling, shift assignments, and request management efficient and conflict-free.
