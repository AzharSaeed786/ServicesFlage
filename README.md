# ServicesFlage
. Service Start Flags
Ye flags startService() method ke sath use hote hain aur onStartCommand() method mein process hote hain.

START_STICKY:

Description: Agar system ne service ko kill kiya toh service ko dubara create kar diya jayega, lekin last delivered intent nahi milega. Service ko explicitly stop karna padta hai.
Use Case: Long-running background tasks jaise music playback.
START_NOT_STICKY:

Description: Agar system ne service ko kill kiya toh service ko dubara create nahi kiya jayega jab tak koi naya intent nahi aata.
Use Case: Short-lived tasks jaise single HTTP request.
START_REDELIVER_INTENT:

Description: Agar system ne service ko kill kiya toh service ko dubara create kar diya jayega aur last delivered intent ko fir se deliver kiya jayega.
Use Case: Tasks jo idempotent hain aur completion ensure karna zaroori hai, jaise data upload.
START_STICKY_COMPATIBILITY:

Description: Ye START_STICKY jaisa hi hai, lekin backward compatibility ke liye use hota hai. Agar system ne service ko kill kiya toh service ko dubara create kiya jayega, lekin intents guarantee nahi kiya jayenge.
2. Intent Flags
Ye flags intents ke sath use hote hain jab aap activities, services ya broadcast receivers ko start karte hain.

FLAG_ACTIVITY_NEW_TASK:

Description: Activity ko nayi task mein start karta hai. Activity agar already exist karti hai, toh uske upar naye instance ko create karta hai.
Use Case: Jab aap ek activity ko context ke bahar se start karna chahte hain, jaise broadcast receiver ya service se.
FLAG_ACTIVITY_CLEAR_TOP:

Description: Agar activity stack mein exist karti hai, toh uske upar ki sabhi activities ko remove kar deta hai aur us activity ko naye intent ke sath re-use karta hai.
Use Case: Notification click ke baad app ko specific state mein restore karna.
FLAG_ACTIVITY_SINGLE_TOP:

Description: Agar activity stack ke top par exist karti hai, toh uske naye instance ko create nahi karta, balki existing instance ko hi re-use karta hai.
Use Case: Reusing the same instance of an activity.
FLAG_ACTIVITY_CLEAR_TASK:

Description: Target activity ke task ko clear karta hai aur us activity ko nayi root activity ke roop mein set karta hai.
Use Case: Complete reset of the app's task stack.
3. Service Binding Flags
Ye flags bindService() method ke sath use hote hain.

BIND_AUTO_CREATE:

Description: Service ko bind karte hi create kar deta hai agar wo already create nahi hui hai.
Use Case: Service ko automatically create karna jab bind ho.
BIND_NOT_FOREGROUND:

Description: Service ko foreground service ke roop mein treat nahi karta, even agar wo bound hai.
Use Case: Background services jo bound hain but unko foreground priority nahi deni hai.
BIND_ABOVE_CLIENT:

Description: Service ko client ke above priority level par run karta hai.
Use Case: Priority increase for bound services.
BIND_ALLOW_OOM_MANAGEMENT:

Description: Service ko system ke OOM killer management mein consider karta hai.
Use Case: Allowing system to manage out-of-memory conditions.
BIND_IMPORTANT:

Description: Service ko high importance priority level assign karta hai.
Use Case: Ensuring service remains active and not killed easily.
BIND_ADJUST_WITH_ACTIVITY:

Description: Service ke lifecycle ko bound activity ke lifecycle ke sath adjust karta hai.
Use Case: Synchronizing the service lifecycle with the activity lifecycle.
