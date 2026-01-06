# COMPREHENSIVE FEATURE TEST CHECKLIST
**NullClass YouTube Clone - Final Testing Before Submission**

Test systematically in this order. Mark ✅ when working, ❌ when broken.

---

## ENVIRONMENT SETUP
- [ ] Frontend URL: https://nullclass-webdev-yourtubeclone.vercel.app/
- [ ] Backend URL: https://nullclass-webdev-youtubeclone-backend.onrender.com/
- [ ] MongoDB Atlas connected
- [ ] All environment variables set

---

## TASK 1: COMMENT SYSTEM WITH TRANSLATION

### Test Comments Feature:
1. [ ] Open any video page
2. [ ] Sign in with Google or OTP
3. [ ] Scroll to comments section
4. [ ] **Add a comment**: Type a comment and submit
   - Expected: Comment appears immediately
   - Expected: Shows your name and timestamp
5. [ ] **Like a comment**: Click like button on a comment
   - Expected: Like count increases
   - Expected: Like button changes color
6. [ ] **Dislike a comment**: Click dislike button
   - Expected: Dislike count increases
7. [ ] **Delete your comment**: Click delete button on your own comment
   - Expected: Comment is removed
8. [ ] **Reply to a comment**: Click reply and add a response
   - Expected: Reply appears nested under original comment

### Test Translation Feature:
9. [ ] Find a comment in English
10. [ ] Click "Translate" button
    - Expected: Comment translates to another language
11. [ ] Click "Show Original"
    - Expected: Returns to English
12. [ ] Test with multiple comments
    - Expected: Each comment translates independently

**TASK 1 STATUS:** ___________

---

## TASK 2: PREMIUM VIDEO DOWNLOAD FEATURE

### Test Download Restrictions:
1. [ ] Sign out (test as guest)
2. [ ] Try to download a video
   - Expected: Shows "Premium feature" message
   - Expected: Prompts to sign in
3. [ ] Sign in as Free user
4. [ ] Try to download a video
   - Expected: Shows plan upgrade prompt
   - Expected: Options: Silver, Bronze, Gold

### Test Downloads Page:
5. [ ] Navigate to Downloads page (sidebar)
6. [ ] Check if page loads correctly
7. [ ] If you have premium plan:
   - Download a video
   - Expected: Video appears in downloads list
8. [ ] Check invoice generation
   - Expected: Invoice created in backend

**TASK 2 STATUS:** ___________

---

## TASK 3: PLAN MANAGEMENT (FREE, SILVER, BRONZE, GOLD)

### Test Plan Modal:
1. [ ] Click on your profile/avatar
2. [ ] Click "Manage Plans" or similar option
3. [ ] **View all plans**:
   - [ ] Free plan (0/month)
   - [ ] Silver plan with features
   - [ ] Bronze plan with features
   - [ ] Gold plan with features
4. [ ] Each plan shows:
   - [ ] Price
   - [ ] Features list
   - [ ] "Choose Plan" button

### Test Razorpay Integration:
5. [ ] Click "Choose Plan" for Silver
   - Expected: Razorpay payment modal opens
6. [ ] Check payment details:
   - [ ] Correct amount shown
   - [ ] Razorpay test mode active
7. [ ] Complete test payment:
   - Use Razorpay test card: 4111 1111 1111 1111
   - Any future expiry date
   - Any CVV
8. [ ] After payment:
   - Expected: Plan upgraded
   - Expected: Success message
   - Expected: User plan updated in database

### Test Watch Time Tracking:
9. [ ] Play a video for 30 seconds
10. [ ] Check if watch time is being tracked
    - Expected: Watch time increases in user profile
11. [ ] Stop video and check again
    - Expected: Time saved correctly

**TASK 3 STATUS:** ___________

---

## TASK 4: LOCATION-BASED THEME & OTP

### Test Location Detection:
1. [ ] Open browser console (F12)
2. [ ] Look for: `Theme: Dark (StateName, Hour: XX)`
3. [ ] Verify location detected:
   - [ ] City/State name appears
   - [ ] Hour is correct

### Test Theme Application:
4. [ ] **If South India (Karnataka, Kerala, Tamil Nadu, Andhra Pradesh, Telangana) + 10AM-12PM:**
   - Expected: Light/White theme
5. [ ] **All other times/locations:**
   - Expected: Dark theme
6. [ ] **Check all pages**:
   - [ ] Home page: Theme applied correctly
   - [ ] Channel page: Theme applied correctly
   - [ ] Watch page: Theme applied correctly
   - [ ] All text visible (white on dark, black on light)

### Test OTP Login:
7. [ ] Sign out
8. [ ] Click "OTP Login"
9. [ ] **If South India detected**:
   - Expected: Email OTP (required)
   - Expected: Phone optional
10. [ ] **If other region**:
    - Expected: Phone OTP (required via SMS)
    - Expected: Email optional
11. [ ] Enter details and generate OTP
12. [ ] Check email/phone for OTP code
13. [ ] Enter OTP and verify
    - Expected: Successfully logged in
    - Expected: User profile created/loaded

**TASK 4 STATUS:** ___________

---

## TASK 5: CUSTOM VIDEO PLAYER WITH GESTURES

### Test Video Player Controls:
1. [ ] Open any video
2. [ ] **Play/Pause**:
   - Click anywhere on video
   - Expected: Video plays/pauses
3. [ ] **Progress bar**:
   - Drag progress bar
   - Expected: Video seeks to position
4. [ ] **Volume control**:
   - Adjust volume slider
   - Expected: Volume changes
5. [ ] **Fullscreen**:
   - Click fullscreen button
   - Expected: Video enters fullscreen
6. [ ] **Settings**:
   - Click settings gear icon
   - Check quality options
   - Check playback speed options

### Test Gesture Controls:
7. [ ] **Double-tap left side**: Rewind 10 seconds
   - Expected: Video rewinds
   - Expected: Shows "-10s" animation
8. [ ] **Double-tap right side**: Forward 10 seconds
   - Expected: Video forwards
   - Expected: Shows "+10s" animation
9. [ ] **Swipe up (right side)**: Increase volume
   - Expected: Volume bar appears
   - Expected: Volume increases
10. [ ] **Swipe down (right side)**: Decrease volume
    - Expected: Volume decreases
11. [ ] **Swipe up (left side)**: Increase brightness
    - Expected: Brightness overlay appears
12. [ ] **Swipe down (left side)**: Decrease brightness
    - Expected: Brightness decreases

### Test Video Info:
13. [ ] Check video title displayed
14. [ ] Check view count
15. [ ] Check like/dislike buttons work
16. [ ] Check channel name clickable

**TASK 5 STATUS:** ___________

---

## TASK 6: VIDEO CALLING WITH SCREEN SHARE

### Test Call Setup:
1. [ ] Navigate to `/call` page
2. [ ] See "Start a Call" or "Join Call" option
3. [ ] **Start a new call**:
   - Click "Start Call"
   - Expected: Room created
   - Expected: Room ID/URL generated
   - Expected: Your video appears (camera)

### Test Joining Call:
4. [ ] Copy room URL
5. [ ] Open in incognito/another browser
6. [ ] Sign in
7. [ ] Paste room URL and join
   - Expected: Second user's video appears
   - Expected: Both videos visible (2-way call)

### Test Call Controls:
8. [ ] **Mute/Unmute audio**:
   - Click microphone icon
   - Expected: Audio mutes/unmutes
9. [ ] **Turn camera on/off**:
   - Click camera icon
   - Expected: Video stops/starts
10. [ ] **Leave call**:
    - Click leave/end call button
    - Expected: Disconnects properly

### Test Screen Sharing:
11. [ ] Click "Share Screen" button
    - Expected: Screen selection dialog appears
12. [ ] Select screen/window to share
    - Expected: Screen shared to other participant
    - Expected: Other user sees your screen
13. [ ] Stop screen sharing
    - Expected: Returns to camera view

### Test Call Recording:
14. [ ] Click "Record" button
    - Expected: Recording starts
    - Expected: Recording indicator shows
15. [ ] Stop recording
    - Expected: Recording saved
    - Expected: Download available

**TASK 6 STATUS:** ___________

---

## AUTHENTICATION TESTS

### Google Sign-In:
1. [ ] Click "Sign In" button
2. [ ] Click "Continue with Google"
3. [ ] Select Google account
   - Expected: Firebase auth successful
   - Expected: User profile loaded
   - Expected: Profile picture appears in header

### Sign Out:
4. [ ] Click profile icon
5. [ ] Click "Sign Out"
   - Expected: Logged out successfully
   - Expected: Redirected to home

---

## VIDEO UPLOAD TEST

### Upload Video:
1. [ ] Sign in
2. [ ] Go to "Your Channel"
3. [ ] Click "Upload a video" area
4. [ ] Select an MP4 video file (under 100MB)
5. [ ] Wait for file to load
   - Expected: File name and size appear
6. [ ] Enter video title
7. [ ] Click "Upload" button
8. [ ] Watch progress bar
   - Expected: Upload percentage shown
   - Expected: Progress updates
9. [ ] After upload completes:
   - Expected: "Upload successful" message
   - Expected: Form resets
   - Expected: Video appears in channel videos list
10. [ ] Refresh page
    - Expected: Uploaded video still visible

---

## THEME & VISIBILITY TEST

### Dark Theme Check:
1. [ ] Open each page in dark theme
2. [ ] **Check text visibility**:
   - [ ] Home page: All text visible
   - [ ] Channel page: All text visible (name, tabs, uploader)
   - [ ] Watch page: All text visible
   - [ ] Comments: All text visible
   - [ ] Sidebar: All text visible
3. [ ] **Check backgrounds**:
   - [ ] No white backgrounds in dark theme
   - [ ] Proper dark gray backgrounds
4. [ ] **Check inputs**:
   - [ ] Input fields visible
   - [ ] Placeholder text readable
   - [ ] Labels visible

---

## RESPONSIVE DESIGN TEST

### Mobile View:
1. [ ] Press F12 and toggle device toolbar
2. [ ] Test on mobile dimensions (375px width)
3. [ ] Check:
   - [ ] Video grid adjusts (1-2 columns)
   - [ ] Sidebar becomes hamburger menu
   - [ ] Video player fits screen
   - [ ] Comments readable
   - [ ] All buttons accessible

### Tablet View:
4. [ ] Test on tablet dimensions (768px width)
5. [ ] Check:
   - [ ] Video grid shows 2-3 columns
   - [ ] Layout responsive

---

## PERFORMANCE TEST

### Loading Times:
1. [ ] Home page loads in < 3 seconds
2. [ ] Video page loads in < 3 seconds
3. [ ] Video playback starts quickly
4. [ ] No lag when scrolling

### Error Handling:
5. [ ] Try accessing non-existent video
   - Expected: "Video not found" message
6. [ ] Try uploading non-MP4 file
   - Expected: Error message
7. [ ] Try uploading file > 100MB
   - Expected: Size limit error

---

## FINAL CHECKS

### Database:
1. [ ] Check MongoDB Atlas
2. [ ] Verify collections exist:
   - [ ] users
   - [ ] videos
   - [ ] comments
   - [ ] likes
   - [ ] downloads
   - [ ] watchlater
   - [ ] history

### Console Errors:
3. [ ] Open browser console (F12)
4. [ ] Navigate through all pages
5. [ ] Check for errors:
   - No critical errors (red text)
   - No 404 errors
   - No CORS errors

### Cross-Browser Test:
6. [ ] Test on Chrome
7. [ ] Test on Firefox
8. [ ] Test on Edge
9. [ ] All features work on all browsers

---

## SUBMISSION CHECKLIST

Before submitting:
- [ ] All 6 tasks fully tested and working
- [ ] All text visible in dark theme
- [ ] Video upload works
- [ ] Screenshots taken of all features
- [ ] Internship report completed
- [ ] Live URLs working:
  - Frontend: https://nullclass-webdev-yourtubeclone.vercel.app/
  - Backend: https://nullclass-webdev-youtubeclone-backend.onrender.com/
- [ ] GitHub repos updated with latest code

---

## CRITICAL ISSUES TO FIX FIRST

Priority order:
1. ✅ Video upload 500 error - FIXED (waiting for Render redeploy)
2. ⏳ Theme visibility - FIXED (waiting for Vercel redeploy)
3. ⏳ Test all features with this checklist
4. ⏳ Fix any issues found during testing
5. ⏳ Take screenshots
6. ⏳ Submit project

---

**TESTING COMPLETED BY:** ___________
**DATE:** ___________
**OVERALL STATUS:** ___________
**READY FOR SUBMISSION:** [ ] YES [ ] NO


when cicked on download it shows error msg like - 

my location when i comment is showing as 'Boardman' but my location shows as mumbai,maharastra.
