# Arise Canteen - Online College Canteen Ordering System

Arise Canteen is a comprehensive web-based platform that digitizes the college canteen experience, allowing students and staff to browse menus, place orders, and manage food services efficiently.

## Key Features

- 🍽️ **Multi-User System**: Separate interfaces for Students, Staff, and Administrators
- 📱 **Responsive Design**: Works on desktop and mobile devices
- 🛒 **Shopping Cart**: Add/remove items and adjust quantities before checkout
- 💳 **UPI Payment Integration**: Secure payment processing via UPI
- 📊 **Real-time Order Tracking**: View order status updates (Pending → Preparing → Ready)
- 👨‍💼 **Admin Dashboard**: Full control over menu, users, and inventory
- 🔐 **Role-Based Access**: Secure authentication with Firebase

## Technology Stack

### Frontend
- HTML5, CSS3, JavaScript
- Firebase Authentication
- Firebase Realtime Database
- Font Awesome Icons
- Responsive Design

### Backend
- Firebase SDK
- Firebase Authentication
- Firebase Realtime Database

### Payment Integration
- UPI payment gateway
- QR code generation

## User Roles

### Student
- Browse menu by categories (Breakfast, Lunch, Snacks, Beverages)
- Add items to cart
- Place orders
- View order history
- Secure checkout

### Staff
- View current orders
- Update order status
- Manage item availability (Mark items as Sold Out/Available)

### Administrator
- Full menu management (Add/Edit/Delete items)
- User management (Add/Delete users)
- View all orders
- Set user roles (Student, Staff, Admin)

## Installation

### Prerequisites
- Firebase account
- Web server (or run locally)
- Modern web browser

### Setup Instructions

1. **Firebase Configuration**:
   - Create a new Firebase project
   - Enable Email/Password authentication in Firebase Console
   - Update Firebase configuration in `script.js`:
     ```javascript
     const firebaseConfig = {
       apiKey: "YOUR_API_KEY",
       authDomain: "YOUR_AUTH_DOMAIN",
       databaseURL: "YOUR_DATABASE_URL",
       projectId: "YOUR_PROJECT_ID",
       storageBucket: "YOUR_STORAGE_BUCKET",
       messagingSenderId: "YOUR_SENDER_ID",
       appId: "YOUR_APP_ID"
     };
     ```

2. **Database Rules**:
   - Set up Firebase Realtime Database with appropriate security rules
   - Recommended structure:
     ```
     {
       "menu": {
         "item1": {
           "name": "Item Name",
           "price": 50,
           "category": "breakfast",
           "soldOut": false
         }
       },
       "orders": {
         "order1": {
           "studentId": "user123",
           "items": {
             "item1": {
               "name": "Item Name",
               "price": 50,
               "quantity": 2
             }
           },
           "status": "Pending",
           "createdAt": TIMESTAMP
         }
       },
       "users": {
         "user123": {
           "email": "user@college.edu",
           "type": "student",
           "createdAt": TIMESTAMP
         }
       }
     }
     ```

3. **Deployment**:
   - Upload all files to your web server
   - Ensure all file paths are correct
   - Test all user flows

## Usage

### For Students
1. Login with student credentials
2. Browse the menu by category
3. Add items to cart
4. Proceed to checkout
5. Track order status in "My Orders"

### For Staff
1. Login with staff credentials
2. View current orders in "Orders" tab
3. Update order status as it progresses
4. Manage item availability in "Manage Menu"

### For Administrators
1. Login with admin credentials
2. Add/edit/delete menu items
3. Manage user accounts
4. View system-wide order data


## Security Considerations

- All passwords are securely hashed using Firebase Authentication
- Users can only access features appropriate for their role
- Admin functions require re-authentication for sensitive operations
- Database rules should be configured to prevent unauthorized access

## Limitations

- Currently supports only UPI payments
- No native mobile app (web-only)
- Limited to single canteen management
- No inventory tracking system

## Future Enhancements

- Add cash payment option
- Implement loyalty/rewards program
- Expand to multiple canteens/locations
- Add dietary filters (vegetarian, vegan, etc.)
- Include food ratings and reviews
- Push notifications for order updates

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
