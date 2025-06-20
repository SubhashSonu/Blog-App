# 🔐 Authentication Flow

## 1. User Visits Home Page
- **GET** request to render the **Home Page**
- User clicks on:
  - **Sign In** button
  - **Sign Up** button

---

## 2. Sign Up Flow
- User enters:
  - Username
  - Email
  - Password
- Password is **hashed** using a **salt** (for encryption & security)
- Save the user data in the **database**
- Redirect to the **Home Page**

---

## 3. Sign In Flow
- User enters:
  - Email
  - Password
- Check if the user exists in the **database**
- Hash the entered password (same salt technique)
- Compare it with the **stored hashed password**
- If both match:
  - **Create a token** (e.g., JWT)
  - Send the token to the client (via cookie or localStorage)
- Redirect to the **Home Page**

---

## 4. Returning User Flow
- When user revisits the website:
  - Token is sent automatically (in cookie or header)
  - Backend **verifies the token**
  - If token is valid → User is **authenticated**

---

## 🔍 Key Concepts

### ✅ Password Hashing
- Converts a password into a fixed-length cryptographic string
- Plain passwords are **never stored**

### ✅ Salt
- Random string added to the password before hashing
- Prevents rainbow table and dictionary attacks

### ✅ JWT (JSON Web Token)
- A compact, self-contained way to securely transmit identity
- Used for verifying authenticated users without re-login

