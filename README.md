# **🎓 EduTrack Pro**

A modern, secure academic portal designed to bridge the gap between students and educators. EduTrack Pro offers real-time assignment tracking, instant grading feedback, and an automated intelligent email notification system.

## **✨ Features**

* **Role-Based Dashboards:** Distinct interfaces for 'Students' and 'Teachers'.  
* **Real-Time Cloud Sync:** Powered by Firebase Firestore, assignments and grades sync instantly across all devices.  
* **OTP Email Verification:** Secure registration using a 6-digit one-time password sent directly to the user's inbox.  
* **Smart Automated Alerts:** \* ⏰ **Due Tomorrow:** Alerts students when a deadline is approaching.  
  * 🚨 **Overdue:** Warns students of missed deadlines.  
  * ✅ **Submission Receipts:** Instantly emails a confirmation when work is submitted.  
* **Interactive UI/UX:** Features a beautiful modern landing page with scroll-triggered fade animations, floating SVG badges, and responsive glassmorphism navigation.  
* **Teacher Evaluation:** Teachers can review submitted Google Drive/Doc links and instantly assign scores and constructive feedback.

## **🛠️ Tech Stack**

* **Frontend:** HTML5, CSS3 (Custom styling, CSS animations), Vanilla JavaScript (ES6 Modules).  
* **Backend / Database:** Firebase v11 (Firestore Cloud Database, Anonymous Authentication).  
* **Email Service:** EmailJS SDK for automated transaction and notification emails.  
* **Design:** Inter Font, Unsplash Assets, SVG Animations.

## **🚀 Setup & Installation**

To run this project locally or fork it for your own use, you will need to configure your own Firebase and EmailJS accounts.

### **1\. Firebase Setup**

1. Create a project in the [Firebase Console](https://console.firebase.google.com/).  
2. Go to **Authentication** \-\> **Sign-in Method** and enable **Anonymous** sign-in.  
3. Go to **Firestore Database** and create a new database.  
4. Update the Firestore Rules to allow read/write access:  
   rules\_version \= '2';  
   service cloud.firestore {  
     match /databases/{database}/documents {  
       match /{document=\*\*} {  
         allow read, write: if true;  
       }  
     }  
   }

5. Replace the firebaseConfig object in the index.html file with your own Firebase project credentials.

### **2\. EmailJS Setup**

1. Create a free account at [EmailJS](https://www.emailjs.com/).  
2. Add your email provider (e.g., Gmail) under **Email Services** and note your Service ID.  
3. Create **two templates**:  
   * **OTP Template:** Must include {{passcode}}, {{time}}, and {{to\_name}}.  
   * **Notification Template:** Must include {{subject}} and {{message}}.  
   * *Make sure the "To Email" field in both templates is set to {{to\_email}}.*  
4. Update the index.html file with your specific EmailJS Public Key, Service ID, and Template IDs.

## **💻 Running the App**

Since this is a vanilla HTML/JS application, no build steps or node modules are required\! Simply open the index.html file in your preferred web browser, or use an extension like VS Code's "Live Server" to view it locally.

## **📜 License**

This project is open-source and available under the [MIT License](https://www.google.com/search?q=LICENSE).