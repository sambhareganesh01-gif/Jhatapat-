# झटपट ऐप — Flutter सोर्स कोड

यह झटपट ऐप का पूरा Flutter सोर्स कोड है। नीचे दिए स्टेप्स फॉलो करके आप इसे अपने कंप्यूटर पर APK में बदल सकते हैं।

## आपके कंप्यूटर पर क्या इंस्टॉल करना होगा

1. **Flutter SDK** — https://docs.flutter.dev/get-started/install से डाउनलोड करें (Windows/Mac/Linux — जो भी आपका सिस्टम हो, वही चुनें)
2. **Android Studio** — https://developer.android.com/studio से डाउनलोड करें (इसमें Android SDK अपने आप आ जाता है)
3. इंस्टॉल के बाद टर्मिनल/कमांड प्रॉम्प्ट में चलाएं:
   ```
   flutter doctor
   ```
   यह बताएगा कि कुछ बाकी तो नहीं है (जैसे Android licenses accept करना — उसके लिए `flutter doctor --android-licenses` चलाएं)

## APK बनाने के स्टेप्स

1. इस पूरे `jhatpat_app` फ़ोल्डर को अपने कंप्यूटर में किसी जगह रखें
2. टर्मिनल/कमांड प्रॉम्प्ट में उस फ़ोल्डर के अंदर जाएं:
   ```
   cd jhatpat_app
   ```
3. ज़रूरी पैकेज डाउनलोड करें:
   ```
   flutter pub get
   ```
4. APK बनाएं:
   ```
   flutter build apk --release
   ```
5. बनने के बाद APK यहां मिलेगी:
   ```
   build/app/outputs/flutter-apk/app-release.apk
   ```

## फोन में इंस्टॉल कैसे करें

1. यह `app-release.apk` फाइल अपने Android फोन में भेजें (USB केबल, WhatsApp, Google Drive — जो सुविधाजनक हो)
2. फोन पर फाइल खोलें → "Unknown apps installation" की अनुमति मांगेगा तो Allow करें
3. Install पर टैप करें

## अभी इस कोड में क्या-क्या बना है

- होम स्क्रीन (स्टोरीज़, कमाई बैनर, 11 फीचर्स का ग्रिड)
- बॉटम नेविगेशन (होम, वीडियो, +, चैट, प्रोफाइल)
- वीडियो/रील्स स्क्रीन — असली सैंपल वीडियो चलते हैं (ऊपर-नीचे स्वाइप करें)
- बाकी सभी फीचर्स (चैट, शॉप, कॉलिंग, प्रोफाइल आदि) की डेमो/मॉक स्क्रीन

## आगे क्या जोड़ना बाकी है (असली प्रोडक्ट के लिए)

- लॉगिन/अकाउंट सिस्टम (Firebase Auth या खुद का backend)
- असली चैट व कॉलिंग (Firebase/Agora/Twilio जैसी सर्विस)
- यूज़र्स के अपने वीडियो अपलोड करने की सुविधा (वीडियो स्टोरेज + बैकएंड)
- शॉप के लिए पेमेंट गेटवे (Razorpay/Paytm आदि)
- कमाई का असली हिसाब-किताब backend से जुड़ना

## ऐप का नाम/आइकॉन बदलना (Play Store पर डालने से पहले)

- ऐप का नाम: `pubspec.yaml` में ऊपर `name:` लाइन में बदलें
- ऐप आइकॉन: `flutter_launcher_icons` पैकेज इस्तेमाल करें (गूगल पर सर्च करें "flutter launcher icons setup")
- Package ID: `android/app/build.gradle` में `applicationId` बदलें (जैसे `com.yourname.jhatpat`)
