# Test Case for User Registration

## Test Case ID: TC-01
### Summary: Registration of a Regular Account
- **Description**: Basic path for registering a regular user with an email account.
- **Preconditions**: The user must have a valid email account.

### Steps
| Step | Action                                | Expected Result                       | Status |
|------|---------------------------------------|---------------------------------------|--------|
| 1    | Click "Register" button               | The registration form appears         | Pass   |
| 2    | Select "Regular Account" option      | Regular account registration form is displayed | Pass   |
| 3    | Fill in required fields with valid data | Fields are filled correctly         | Pass   |
| 4    | Click "Create Account" button         | The account is created successfully   | Pass   |

### Expected Result
- User account is successfully created, and an email is sent for verification.

### Actual Result
- Account created successfully, verification email received.

---

# Test Case for Cart Functionality

## Test Case ID: TC-02
### Summary: Add Product to Cart
- **Description**: Verifying that the user can add products to the cart.
- **Preconditions**: User is logged in, and a product is available in the catalog.

### Steps
| Step | Action                                    | Expected Result                    | Status |
|------|-------------------------------------------|------------------------------------|--------|
| 1    | Browse product catalog                   | Products are listed with images    | Pass   |
| 2    | Select a product                         | Product page opens with details    | Pass   |
| 3    | Click "Add to Cart" button               | Product is added to the cart       | Pass   |
| 4    | Go to the cart                           | Cart contains selected product     | Pass   |

### Expected Result
- The product is added to the cart successfully.

### Actual Result
- The product was successfully added to the cart.

---

# Additional Test Cases
Include at least **10 test cases** for the entire app, covering user registration, cart management, order history, and more.

