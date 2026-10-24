# Veyrath AI Studio को Android APK में बदलें

यह प्रोजेक्ट Android APK नहीं, React/Vite वेब ऐप है। इस ZIP में Capacitor सेटअप और GitHub Actions वर्कफ़्लो जोड़ा गया है, जिससे GitHub पर APK बन सकता है।

## फोन से APK बनाने के चरण
1. इस ZIP को GitHub पर नई repository में अपलोड करें (पहले ZIP extract करें और अंदर की फाइलें अपलोड करें)।
2. GitHub में repository खोलें → **Actions** टैब → **Build Android APK** चुनें।
3. **Run workflow** दबाएँ और workflow पूरा होने दें।
4. सफल run खोलें; नीचे **Artifacts** में `veyrath-ai-studio-debug-apk` डाउनलोड करें।
5. ZIP artifact को extract करें और `app-debug.apk` खोलकर इंस्टॉल करें। Android पूछे तो केवल GitHub से डाउनलोड की गई अपनी build के लिए browser/files app को “Install unknown apps” की अनुमति दें। इंस्टॉल के बाद अनुमति वापस बंद कर सकते हैं।

## اہم बातें
- APK debug build ہے، Play Store کے لیے signed release نہیں۔
- Gemini AI features کے لیے API key درکار ہو سکتی ہے۔ ZIP میں `.env.example` ہے، مگر Vite میں secret key کو براہ راست client bundle میں رکھنا محفوظ نہیں؛ production کے لیے server-side API proxy استعمال کریں۔
- اگر build error آئے تو GitHub Actions کے log میں آخری error دیکھ کر درست کریں۔
