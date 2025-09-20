# Polymers Recycling Platform Monorepo

Polymers is a **real-time, gamified recycling platform** with smart hardware, blockchain rewards, AR navigation, multiplayer challenges, ESG metrics, and analytics dashboards. Users earn **PLY tokens** and milestone NFTs for sustainable actions.

---

## **Monorepo Structure**

```
/polymers
  /apps
    /web           # Main React + Vite web app (user-facing)
    /dashboard     # Admin & analytics dashboard using Next.js
    /mobile        # React Native mobile app (iOS & Android)
  /packages
    /backend       # Node.js / Express backend with WebSocket/MQTT
    /lib           # Shared Solana SDK wrappers, Helium IoT connectors, AR & ESG utilities
    /hooks         # Shared React hooks for web/mobile apps
    /utils         # Shared utility functions (distance, timestamp, ESG, blockchain)
    /constants     # Shared constants (materials, rewards, bin status types)
    /config        # Shared configuration (API URLs, Solana RPC, Wallet IDs, Mapbox, Helium/Helius keys)
```

---

## **Key Features**

### **Smart Hardware & IoT**

* Smart bins with fill sensors, material recognition, weight detection
* Real-time updates via Helium IoT and WebSocket
* Alerts for full/malfunctioning bins

### **Recycled Items**

* Track item type, material, location, timestamp, reward
* Earn **PLY tokens** and milestone NFTs
* Dashboard & leaderboard integration

### **Blockchain & Solana**

* PLY token rewards
* NFT achievements via **Metaplex**
* Solana Pay integration
* Helius RPC for transaction monitoring
* PYTH feeds for real-time PLY pricing

### **AR Wayfinder**

* Navigate to bins and cleaned areas via AR
* 3D directional arrows or floating markers
* Displays distance, bin type, reward info, ESG impact
* Mobile (iOS/Android) and Web AR support

### **Gamification & Multiplayer**

* Leaderboards: weekly/seasonal rankings
* Multiplayer challenges
* Streaks and milestone rewards

### **Maps & Analytics**

* Mapbox maps with bin status, cleaned areas, hotspots
* Heatmaps for recycling intensity
* Dashboards for tokens, NFTs, recycled items, and IoT usage

### **ESG Metrics**

* Environmental, Social, and Governance tracking
* Optional AR overlay showing real-time ESG impact

### **Settings & Preferences**

* Wallet connect, switch, disconnect
* Notifications, privacy, and gamification options

---

## **Apps Overview**

### **Web (Vite)**

* React + TypeScript web app (user-facing)
* Pages: Home, Game, RecycledItems, ARWayfinder, ESG, Profile, Settings
* Components: MapboxIoT, HardwareBinCard, ScanReward, PLYTokenActions, SolanaPayButton, NFTRewardCard, ARWayfinder, ARMarker, ESGDashboard
* Fast HMR via Vite

### **Dashboard (Next.js)**

* Admin analytics & monitoring dashboard
* Pages: AnalyticsDashboard, IoTDeviceMonitor, Leaderboards, ESGMetrics, CommunityChallenges, RecycledItemsStats
* Components: Heatmaps, ESG Score Cards, Blockchain Activity Panels
* Server-side rendering and API routes via Next.js

### **Mobile (React Native)**

* iOS & Android using Expo or CLI
* Pages/components similar to Web, with ARWayfinder using device camera and orientation sensors
* Push notifications for rewards, bin alerts, and challenges

---

## **Backend**

* Node.js / Express with REST & WebSocket endpoints
* Handles recycled items, rewards, NFT minting, ESG metrics
* Integrates with Solana programs, Helius RPC, PYTH feeds, Helium IoT
* Authentication and role-based access control

---

## **Shared Packages**

* **lib/**: Solana SDK wrappers, IoT connectors, AR utilities, ESG calculators
* **hooks/**: useSettings, useSolanaProgram, usePLYToken, useRecycledItemScan, useHeliusTransactions, useARNavigation, useESGMetrics, useIoTDevices, useMapboxIoT
* **utils/**: Distance/bearing, timestamps, blockchain helpers, ESG scoring, AR positioning
* **constants/**: Material types, reward thresholds, bin status types, API endpoints
* **config/**: API URLs, Solana RPC, Wallet & program IDs, Mapbox, Helium/Helius keys, PYTH feeds

---

## **Environment Variables (.env.example)**

```env
# Solana Programs
REACT_APP_PLY_TOKEN_PROGRAM_ID=YourPLYTokenProgramID
REACT_APP_METAPLEX_PROGRAM_ID=YourMetaplexProgramID
REACT_APP_RECYCLING_REWARD_PROGRAM_ID=YourCustomRewardProgramID

# Blockchain & Wallet
REACT_APP_SOLANA_RPC_URL=https://api.mainnet-beta.solana.com
REACT_APP_SOLANA_PAY_RECIPIENT=YourWalletAddressHere

# APIs & Feeds
REACT_APP_HELIUS_API_KEY=YourHeliusAPIKeyHere
REACT_APP_PYTH_FEED_ID=YourPythFeedIDHere
REACT_APP_MAPBOX_ACCESS_TOKEN=YourMapboxAccessTokenHere
REACT_APP_HELIUM_API_KEY=YourHeliumAPIKeyHere
```

---

## **Tech Stack**

| Layer      | Technology                                                           |
| ---------- | -------------------------------------------------------------------- |
| Web        | React + Vite, TypeScript, Tailwind CSS, Mapbox, Three.js / WebXR     |
| Dashboard  | Next.js, TypeScript, Tailwind CSS, SSR, API routes                   |
| Mobile     | React Native + Expo/CLI, TypeScript, ARWayfinder, Push notifications |
| Backend    | Node.js / Express, WebSocket / MQTT, REST API                        |
| Blockchain | Solana, Solana Pay, PLY token program, Metaplex NFT                  |
| Data Feeds | Helius RPC, PYTH feeds                                               |
| Database   | PostgreSQL / Supabase                                                |
| Analytics  | Recharts, Mapbox heatmaps                                            |
| Shared Lib | Solana SDK wrappers, Helium IoT connectors, AR & ESG utilities       |

---

## **Installation**

```bash
# Clone repo
git clone https://github.com/your-org/polymers.git
cd polymers

# Install dependencies (Nx/Turborepo)
npm install

# Start development servers
# Web (Vite)
cd apps/web && npm run dev
# Dashboard (Next.js)
cd apps/dashboard && npm run dev
# Mobile (Expo)
cd apps/mobile && npm run start
# Backend
cd packages/backend && npm run dev
```

---

## **Roadmap**

* AI-assisted item recognition
* NFT marketplace for milestone rewards
* Multi-chain reward integration
* Predictive analytics for recycling hotspots
* Enhanced AR Wayfinder with path guidance and ESG overlays
* Expanded shared lib/hooks/utils for external integrations
