YouTube Clone Project Summary

### **Task 1: Comment Translator with Enhancements**
- **Like/Dislike System:** Users can like/dislike comments
- **City Display:** Shows user's location on comments
- **Special Character Filter:** Blocks profanity/spam in comments
- **Language Translation:** Translate comments to different languages

### **Task 2: Video Download with Premium**
- **Razorpay Integration:** Payment gateway for premium subscriptions
- **Access Control:** Free users see "Upgrade to Premium" message when they try to download more than one video per day.
- **Premium Users:** Can download unlimted videos and get the premium badge

### **Task 3: Plan Upgrade System**
- **Time Limits:** Daily usage limits based on plan (Free: 5min, Bronze: 7min, Silver: 10min, Gold: unlimited)
- **Plan Management:** Users can view/upgrade their plans
- **Invoice Generation:** Automatic invoice creation on upgrade
- **Usage Tracking:** Real-time tracking of watch time

### **Task 4: Dynamic Theme & Location OTP**
- **Dynamic Theme:** Dark mode for South Indian users between 10AM - 12PM and Light mode for other states and timezones
- **Location-Based:** Theme changes based on user's location and time
- **OTP Login:** Alternative login using phone number + OTP
- **SMS and GMAIL Integration:** OTP sent via SMS or Gmail service based on the user's location

### **Task 5: Custom Video Player**
- **Gesture Controls:**
  - Single tap center: Play/Pause
  - Double tap left: Rewind 10 seconds
  - Double tap right: Forward 10 seconds
  - Three-taps on middle: next video
- **Custom UI:** Replaced native controls with custom design

### **Task 6: VoIP Video Calls**
- **1-on-1 Video Calls:** Real-time peer-to-peer video communication
- **Screen Sharing:** Share your screen with remote user
- **Recording:** Record calls and download as `.webm` files to `Local` 
- **Controls:** Mute/unmute audio, toggle camera, end call
- **WebRTC + Socket.io:** Used for signaling and peer connections

---

## 📊 Technologies Used

**Frontend:** Next.js, React, TypeScript, Tailwind CSS
**Backend:** Node.js, Express, MongoDB
**Authentication:** Firebase (Google OAuth), Custom OTP
**Payments:** Razorpay
**Video Calls:** WebRTC, Socket.io, simple-peer, RecordRTC
**APIs:** SMS, Email, Translation, Geolocation

---

**Developer:** Durga Sandhya
