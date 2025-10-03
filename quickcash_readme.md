# QuickCash - Android Job Marketplace App

![Android Studio](https://img.shields.io/badge/Android-Studio-green.svg) 
![Java 8+](https://img.shields.io/badge/Java-8+-orange.svg) 
![Firebase Auth & Database](https://img.shields.io/badge/Firebase-Auth%2520%2526%2520Database-yellow.svg)  

A comprehensive Android application for a job marketplace with user authentication, password recovery, and secure account management.

---

## App Overview
QuickCash is a mobile application that connects job seekers and employers. It provides:
- Robust user authentication  
- Secure password recovery  
- Clean and intuitive interface  

---

## Features

<details>
<summary>User Authentication</summary>

- Secure email/password registration  
- Firebase Authentication integration  
- Session management  

</details>

<details>
<summary>Account Security</summary>

- Password strength validation  
- Security questions for account recovery  
- Secure password reset flow  

</details>

<details>
<summary>User Dashboard</summary>

- Clean user interface  
- Session management  
- Easy logout functionality  

</details>

<details>
<summary>Password Recovery</summary>

- Email verification  
- Security question authentication  
- Secure password reset  

</details>

---

## Quick Start

### Prerequisites
- Android Studio (Arctic Fox or later)  
- Java JDK 8 or higher  
- Firebase Account  
- Android device/emulator (API 21+)  

### Installation

#### Clone the Repository
```bash
git clone https://github.com/your-username/QuickCash-Android.git
cd QuickCash-Android
```

#### Set Up Firebase
1. Go to Firebase Console  
2. Create new project: `QuickCash`  
3. Add Android app with package: `com.example.quickcash`  
4. Download `google-services.json` and place it in `app/` directory  
5. Enable Authentication → Email/Password  
6. Create Realtime Database in test mode  
7. Update database rules if needed  

#### Build and Run
1. Open project in Android Studio  
2. Sync project with Gradle files  
3. Build project (`Build → Make Project`)  
4. Run on emulator or device  

---

## Project Structure
```
app/
├── src/main/
│   ├── java/com/example/quickcash/
│   │   ├── ui/                    # Activities
│   │   │   ├── CreateAccount.java
│   │   │   ├── LoginActivity.java
│   │   │   ├── Dashboard.java
│   │   │   ├── ForgotPasswordActivity.java
│   │   │   └── ResetPasswordActivity.java
│   │   ├── model/                 # Data Models
│   │   │   ├── UserModel.java
│   │   │   └── SecurityModel.java
│   │   ├── core/                  # Business Logic
│   │   │   └── Users.java
│   │   ├── database/              # Database Layer
│   │   │   └── Firebase.java
│   │   └── validator/             # Validation Logic
│   │       └── Validator.java
│   ├── res/                       # Resources
│   │   ├── layout/                # UI Layouts
│   │   ├── drawable/              # Images & Icons
│   │   └── values/                # Strings, Colors
│   └── AndroidManifest.xml
```

---

## Configuration
<details>
<summary>Firebase Setup</summary>

**Authentication Configuration**
```java
FirebaseAuth auth = FirebaseAuth.getInstance();
```

**Database Rules**
```json
{
  "rules": {
    "Users": {
      "$uid": {
        ".read": "auth != null && auth.uid == $uid",
        ".write": "auth != null && auth.uid == $uid"
      }
    }
  }
}
```

**Environment Variables**  
All Firebase configuration is handled through `google-services.json`.

</details>

---

## Usage Guide

<details>
<summary>For Users</summary>

**Registration**
1. Open the app (starts at Create Account screen)  
2. Fill in username, email, and password  
3. Answer 3 security questions  
4. Click "Create Account"  

**Login**
1. Enter registered email and password  
2. Click "Login" to access dashboard  

**Password Recovery**
1. On login screen, click "Forgot Password?"  
2. Enter registered email  
3. Answer security questions  
4. Set new password  

</details>

<details>
<summary>For Developers</summary>

**Adding New Features**
1. Create new Activity in `ui/` package  
2. Add layout XML in `res/layout/`  
3. Update `AndroidManifest.xml`  
4. Add navigation from existing activities  

**Modifying User Model**
```java
public class UserModel {
    private String username;
    private String email;
    private String password;
    private SecurityModel securityAns;
    // Add new fields here
}
```

</details>

---

## Technical Details

**Dependencies**
```gradle
dependencies {
    implementation 'androidx.appcompat:appcompat:1.6.1'
    implementation 'com.google.android.material:material:1.9.0'
    implementation 'androidx.constraintlayout:constraintlayout:2.1.4'
    implementation 'com.google.firebase:firebase-auth:22.1.2'
    implementation 'com.google.firebase:firebase-database:20.2.2'
}
```

**Architecture**
- MVVM Pattern (Model-View-ViewModel)  
- Firebase Backend (Authentication + Realtime Database)  
- Java for business logic  
- XML for UI layouts  

**Security Features**
- Password strength validation  
- Email format verification  
- Firebase security rules  
- Input sanitization  

---

## Troubleshooting
<details>
<summary>Common Issues</summary>

**"Authentication Failed"**
- Check internet connection  
- Verify Firebase Authentication is enabled  
- Confirm email/password correctness  

**"Database Permission Denied"**
- Check Firebase Database rules  
- Ensure user is authenticated  

**Build Errors**
- Clean project: `Build → Clean Project`  
- Rebuild project: `Build → Rebuild Project`  
- Sync Gradle: `File → Sync Project with Gradle Files`  

**Firebase Issues**
- Ensure `google-services.json` is in correct location  
- Verify package name matches in Firebase console  
- Check Firebase project is on Spark (free) plan  

</details>

---

## Contributing
1. Fork the repository  
2. Create feature branch (`git checkout -b feature/AmazingFeature`)  
3. Commit changes (`git commit -m 'Add AmazingFeature'`)  
4. Push to branch (`git push origin feature/AmazingFeature`)  
5. Open Pull Request  

---

## License
MIT License - see LICENSE file for details.

---

## Acknowledgments
- Firebase for backend services  
- Android Studio development tools  
- Material Design components  

---

## Support
If you encounter any issues:  
- Check Troubleshooting section  
- Review [Firebase Documentation](https://firebase.google.com/docs)  
- Create an issue in GitHub repository  

> Note: This app requires Firebase configuration. The free Spark plan provides sufficient resources for development and small-scale deployment.

<div align="center">
Built using Android Studio and Firebase
</div>

