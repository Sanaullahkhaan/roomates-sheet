# Roomates Sheet (₨) 🏠

A production-ready, mobile-first roommate expense settlement web app tailored for flatmates and roommates managing shared living expenses in Pakistan (Currency: **PKR / Rs.**).

Built with **multi-user live sharing**, **instant local-first persistence + Firebase real-time cloud sync**, **exact paisa-precision integer math (Rs. 1 = 100 paisa)**, and an **optimal greedy debt settlement algorithm** (minimizing the number of cash transfers).

---

## 👥 Multi-User Collaboration & Sharing

Every flatmate can now participate from their own phone or laptop:

1. **Personal Identity / User Switcher ("Who is using this device?")**:
   - Tap your name in the header (e.g. `👤 Sanaullah ▼`) to choose your active profile.
   - When **Sanaullah** adds an expense, he is automatically set as the payer.
   - When **Ahmed** opens the app on his phone and chooses "Ahmed", his expenses automatically default to him.
   - Every transaction in the ledger records an audit tag: `by Sanaullah` or `by Ahmed`.

2. **Room Code System (e.g. `FLAT-402`)**:
   - Roommates join the same sheet by entering your shared **Room Code** (e.g., `FLAT-402`, `G11-FLAT`, `HOSTEL-ROOM-12`).
   - Anyone opening `https://<your-app>/?room=FLAT-402&user=Ahmed` automatically joins the room and sets their profile to Ahmed!

3. **WhatsApp Room Invite Link**:
   - Tap **"WhatsApp Room Link"** to send an instant pre-filled invitation to your flat WhatsApp group:
     > *"Hey flatmates! Join our room FLAT-402 on Roomates Sheet to log expenses together and see live debt settlements: [link]"*

4. **Real-Time Live Cloud Synchronization (Google Firebase Firestore)**:
   - Built-in support for real-time bi-directional synchronization via Firebase Firestore.
   - When Sanaullah logs an electricity bill on his phone, Ahmed, Faizan, and Ali's screens update automatically in real time without refreshing!
   - 100% free with Google Firebase Spark plan.

5. **Local Home Wi-Fi Sharing**:
   - If flatmates are connected to the same home Wi-Fi network, they can open the app directly on their phones using your local IP:
     `http://192.168.0.114:8080/`

---

## 🚀 How to Host & Put It Online For Free (Under 2 Minutes)

To share a permanent link with your flatmates anywhere in Pakistan, use any of these free hosting platforms:

### Option A: Vercel (Easiest & Fastest — 30 Seconds)
1. Go to [vercel.com](https://vercel.com) (free signup).
2. Drag and drop the `roomates-sheet` folder.
3. You will immediately receive a live URL like `https://roomates-sheet.vercel.app`!
4. Send the link to your flatmates: `https://roomates-sheet.vercel.app/?room=FLAT-402`.

### Option B: GitHub Pages (100% Free Forever)
1. Create a free GitHub repository (e.g., `roomates-sheet`).
2. Upload `index.html`.
3. In repository **Settings** ➔ **Pages**, set branch to `main`.
4. Your app is live at `https://<username>.github.io/roomates-sheet/`!

### Option C: Firebase Hosting
1. Run `npm install -g firebase-tools`
2. Run `firebase init hosting` and select this folder.
3. Run `firebase deploy`. Live on `<project-id>.web.app` with zero cost.

---

## 📊 Benchmark Verification Suite (Acceptance Criteria)

Dataset: 4 Roommates (`Sanaullah`, `Ahmed`, `Faizan`, `Ali`), 5 Shared Expenses (`Rs. 6,060.00`), 15 Direct Payments (`Rs. 8,730.00`).

### Expected & Verified Net Balances:
- **Faizan**: gets **+Rs. 2,580.84** (`+258,084` paisa)
- **Sanaullah**: gets **+Rs. 840.83** (`+84,083` paisa)
- **Ahmed**: owes **-Rs. 2,999.17** (`-299,917` paisa)
- **Ali**: owes **-Rs. 422.50** (`-42,250` paisa)
- **Net Sum**: **$0.00$ paisa** (Strict Zero-Sum Conservation)

### Optimal Greedy Settlement Transfers (3 Transactions):
1. **Ahmed** $\rightarrow$ **Faizan**: **Rs. 2,580.84**
2. **Ali** $\rightarrow$ **Sanaullah**: **Rs. 422.50**
3. **Ahmed** $\rightarrow$ **Sanaullah**: **Rs. 418.33**
