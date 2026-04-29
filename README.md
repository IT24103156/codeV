
------------------- frontend & backend ------------------------
npm install
npm run dev

-------------------- before add mongodb url -----------------------------
npm install mongodb

connect mongodb 

----------- git hub------------------------------------
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git push -u origin main

--------------------------- app -- ------------------------------last---------------------------
https://69f20ff27c2c0c22df8db298--wmtp.netlify.app/

----------------------------------------- backend---------------------------------------- ---
https://labtestpractice-production-ed2e.up.railway.app/

---------------------------------- frontend deploy codes ----------------------------------
Build settings

Runtime: Not set
Base directory: .
Package directory: Not set

Build command:
cd frontend && npm install --include=dev && node ./node_modules/vite/bin/vite.js build

Publish directory:
./frontend/dist

Functions directory:
./netlify/functions

Deploy log visibility:
Logs are public

Build status:
Active

# ==============================----------------------------------------------------------------------------------------------------------------------------

# 🚀 RAILWAY DEPLOYMENT GUIDE (MERN BACKEND)

# ==============================

# 1️⃣ SIGN IN

* Go to: https://railway.app
* Click "Login with GitHub"
* Authorize access

# ==============================

# 2️⃣ CREATE PROJECT

# ==============================

* Click: New Project
* Select: Deploy from GitHub repo
* Choose your repo: mern-item-manager

# ⚠️ IMPORTANT:

# Set ROOT DIRECTORY correctly

Root Directory:
backend

# If not set → ERROR:

# "Service offline" ❌

# ==============================

# 3️⃣ CONFIGURE SERVICE

# ==============================

# Start Command (auto usually works):

npm start

# If not → manually set:

Start Command:
npm start

# ==============================

# 4️⃣ ADD ENV VARIABLES (CRITICAL)

# ==============================

Go to: Variables tab → Add:

MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/myDatabase?retryWrites=true&w=majority

PORT=5000

# ⚠️ COMMON ERROR:

# Missing MONGO_URI → Backend crash ❌

# ==============================

# 5️⃣ MONGODB FIX (VERY IMPORTANT)

# ==============================

Go to MongoDB Atlas:

Network Access → Add IP:

0.0.0.0/0   (Allow access from anywhere)

# ❌ If not added:

# "MongoDB connection failed" ❌

# ==============================

# 6️⃣ FIX PORT ISSUE (CODE)

# ==============================

# In server.js MUST use:

const PORT = process.env.PORT || 5000;

app.listen(PORT, () => {
console.log(`Server running on port ${PORT}`);
});

# ❌ DO NOT use:

# app.listen(5000)

# ==============================

# 7️⃣ DEPLOY

# ==============================

* Railway auto deploys after setup
* If changes made:

git add .
git commit -m "fix backend"
git push

# ==============================

# 8️⃣ GET LIVE URL

# ==============================

Go to:
Settings → Networking → Generate Domain

Example:
https://mern-item-manager-production.up.railway.app

# ==============================

# 9️⃣ TEST BACKEND

# ==============================

Open in browser:

https://your-url/api/items

✔ If JSON response → SUCCESS
✔ If error → check logs

# ==============================

# 🔟 COMMON ERRORS & FIXES

# ==============================

# ❌ Service offline

→ Fix: Set Root Directory = backend

# ❌ MongoDB not connecting

→ Fix: Add 0.0.0.0/0 in Atlas

# ❌ App crashed

→ Fix: Check Logs tab

# ❌ Env not working

→ Fix: Add variables correctly

# ❌ Wrong API URL

→ Fix: Use /api/items route

# ==============================

# 🎯 FINAL RESULT

# ==============================

✔ Backend running online
✔ MongoDB connected
✔ API working
✔ Ready for frontend connection

# ==============================

# DONE 🔥

# ==============================


# ==============================------------------------------------------------------------------------------------------------------------------------------

# 🌐 NETLIFY DEPLOYMENT GUIDE (MERN FRONTEND)

# ==============================

# 1️⃣ SIGN IN

* Go to: https://netlify.com
* Click: Login with GitHub
* Authorize access

# ==============================

# 2️⃣ IMPORT PROJECT

# ==============================

* Click: Add new site → Import from Git
* Choose: GitHub
* Select repo: mern-item-manager

# ==============================

# 3️⃣ BUILD SETTINGS (CRITICAL)

# ==============================

# Option A (Recommended for MERN project structure)

Base Directory:
.

Build Command:
cd frontend && npm install --include=dev && node ./node_modules/vite/bin/vite.js build

Publish Directory:
frontend/dist

# ⚠️ WHY THIS SETUP:

# - Project has frontend + backend

# - Build must run inside frontend folder

# - node command avoids vite permission error

# ==============================

# 4️⃣ API CONNECTION (IMPORTANT)

# ==============================

# In frontend/src/api/itemApi.js:

const API = axios.create({
baseURL: "https://your-railway-url/api",
});

# Example:

https://mern-item-manager-production.up.railway.app/api

# ⚠️ COMMON ERROR:

# ❌ /api/items/items (duplicate path)

# ✔ Correct: /api + /items

# ==============================

# 5️⃣ DEPLOY

# ==============================

* Click: Deploy site
* Wait 1–2 minutes

# ==============================

# 6️⃣ REDEPLOY (AFTER FIXES)

# ==============================

* Go to: Deploys tab
* Click: Trigger deploy → Clear cache and deploy

# OR push code:

git add .
git commit -m "fix frontend"
git push

# ==============================

# 7️⃣ COMMON ERRORS & FIXES

# ==============================

# ❌ vite: Permission denied

→ Fix:
Use build command:
node ./node_modules/vite/bin/vite.js build

# ❌ Blank page

→ Fix:
Check API URL (no localhost)

# ❌ Data not loading

→ Fix:
Correct backend URL in frontend

# ❌ Build fails (few packages installed)

→ Fix:
Use:
npm install --include=dev

# ❌ Wrong publish directory

→ Fix:
Use:
frontend/dist (NOT dist if base is ".")

# ❌ Page refresh shows 404

→ Fix (optional):
Add _redirects file in frontend/public:

/* /index.html 200

# ==============================

# 8️⃣ TEST LIVE SITE

# ==============================

Open:
https://your-site-name.netlify.app

✔ Page loads
✔ Add item works
✔ Data saved
✔ Data displayed

# ==============================

# 9️⃣ FINAL SUBMISSION CHECK

# ==============================

Take screenshots:

✔ Netlify deploy success
✔ Website homepage
✔ Add item working
✔ Data showing

# ==============================

# 🎯 FINAL RESULT

# ==============================

✔ Frontend deployed
✔ Connected to Railway backend
✔ Full MERN app working online

# ==============================

# DONE 🔥

# ==============================

# ==============================---------------------------------------------------------------------------------------------------------------------------------

# 🍃 MONGODB ATLAS CONNECTION GUIDE

# ==============================

# 1️⃣ Create MongoDB Atlas Account

* Go to: https://www.mongodb.com/atlas
* Sign up (use Google or email)

# 2️⃣ Create Cluster

* Click "Create" → Choose FREE tier (M0)
* Select region (closest: Singapore)
* Click "Create Cluster"

# 3️⃣ Create Database User

* Go to: Database Access
* Click "Add New Database User"
* Username: admin (or anything)
* Password: admin123 (or your own)
* Role: Read and Write to Any Database
* Click "Add User"

# 4️⃣ Allow Network Access (VERY IMPORTANT)

* Go to: Network Access
* Click "Add IP Address"
* Click "Allow Access from Anywhere"
* It will add:
  0.0.0.0/0
* Click Confirm

# 5️⃣ Get Connection String

* Go to: Clusters → Click "Connect"
* Choose: "Drivers"
* Copy connection string like:

mongodb+srv://admin:admin123@cluster0.xxxxx.mongodb.net/?retryWrites=true&w=majority

# 6️⃣ Modify Connection String

* Replace password and DB name:

mongodb+srv://admin:admin123@cluster0.xxxxx.mongodb.net/myDatabase?retryWrites=true&w=majority

# 7️⃣ Add to Railway ENV Variables

* Go to Railway → Your Project → Variables
* Add:

MONGO_URI=mongodb+srv://admin:admin123@cluster0.xxxxx.mongodb.net/myDatabase?retryWrites=true&w=majority

PORT=5000

# 8️⃣ Backend Code (already correct)

mongoose.connect(process.env.MONGO_URI)

# 9️⃣ Redeploy

* Push code OR click "Deploy" in Railway

# ==============================

# ✅ TEST

# ==============================

* Open:
  https://your-railway-url/api/items

✔ If no error → MongoDB connected
✔ If error → check IP access or password

# ==============================

# DONE 🔥

# ==============================



admin2
admin

PORT=5000
MONGO_URI=mongodb+srv://admin2:admin@cluster0.wjmgi90.mongodb.net/?appName=Cluster0

mongodb+srv://sathurstiga_s:SVahi6@cluster0.uhi1cnv.mongodb.net/itemDB?retryWrites=true&w=majority


if mongo db doesnt work---------------------------------server.js--------------------------------------------------------
import dns from "dns";

// Force Google DNS
dns.setServers(["8.8.8.8", "8.8.4.4"]);
