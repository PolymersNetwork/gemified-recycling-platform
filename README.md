# Polymers Recycling Platform Monorepo

Polymers is a **real-time, gamified, eco-action platform** with smart hardware, blockchain rewards, AR navigation, multiplayer challenges, ESG metrics, crowdfunding, and analytics dashboards. Users earn **PLY tokens** and milestone NFTs for verified sustainability actions.

---

## **Monorepo Structure**

```
/polymers
  /apps
    /web           # React + Vite web app (user-facing)
    /dashboard     # Next.js admin analytics & campaign dashboard
    /mobile        # React Native app (iOS & Android)
  /packages
    /backend       # Node.js / Express backend (REST + WebSocket/MQTT)
    /lib           # Shared Solana SDK wrappers, Helium IoT connectors, AR & ESG & Eco-action utilities
    /hooks         # Shared React hooks for web/mobile apps
    /utils         # Distance, timestamp, blockchain, ESG, eco-action helpers
    /constants     # Material types, reward thresholds, bin & eco-action status
    /config        # API URLs, Solana RPC, Wallet IDs, Mapbox, Helium/Helius keys, PYTH feeds
```

---

## **Key Features**

### **Eco-Action Tracking**

* **Recycling Submissions**: Submit plastic/metal/paper waste with photo verification
* **Tree Planting**: GPS-verified tree planting submissions
* **Solar Energy**: Track solar energy generation & usage
* **Carbon Footprint**: Calculate CO₂ savings from all eco-actions

### **Rewards & Tokenomics**

* **PLY Token Rewards**: Earn tokens for verified eco-actions
* **NFT Milestones**: Unlock exclusive NFTs for sustainability achievements
* **Leaderboards**: Compete globally and locally with eco-champions
* **Swap Integration**: Exchange PLY tokens for USDC/SOL

### **Crowdfunding & Campaigns**

* **Eco-Campaigns**: Create and fund environmental projects
* **Escrow Smart Contracts**: Secure fund management through Solana Anchor programs
* **Impact Tracking**: Real-time monitoring of campaign outcomes
* **Community Governance**: DAO-based voting for platform improvements

### **Blockchain Integration**

* **Solana Network**: Fast, low-cost transactions for all platform activities
* **Anchor Programs**: Custom smart contracts for escrow, rewards, and governance
* **Multi-Wallet Support**: Phantom, Solflare, Backpack integration
* **Helius RPC**: Real-time blockchain transaction monitoring
* **PYTH Feeds**: Live PLY token price updates

### **AR Wayfinder**

* Navigate to bins and cleaned areas via AR markers
* Distance, bin type, reward info, ESG overlay
* Works on mobile (React Native) and Web (WebXR/Three.js)

### **IoT & Analytics**

* Monitor smart bins via Helium IoT
* Mapbox heatmaps for recycled items, solar, tree planting
* Real-time dashboards for ESG metrics and campaign progress

---

## **Apps Overview**

### **Web (Vite)**

* Pages: Home, Game, RecycledItems, ARWayfinder, ESG, Profile, Settings, EcoCampaigns
* Components: MapboxIoT, HardwareBinCard, RecycledItemCard, ScanReward, PLYTokenActions, SolanaPayButton, MetaplexNFTMint, ARWayfinder, ARMarker, ESGDashboard, ESGScoreCard, CampaignCard

### **Dashboard (Next.js)**

* Pages: AnalyticsDashboard, IoTDeviceMonitor, Leaderboards, ESGMetrics, CommunityChallenges, RecycledItemsStats, CampaignsManagement
* Components: Heatmaps, ESG Score Cards, Blockchain Activity Panels, CampaignProgressCard

### **Mobile (React Native)**

* Pages/components similar to web
* ARWayfinder using camera & orientation sensors
* Push notifications for rewards, bin alerts, challenges

---

## **Backend (Node.js / Express)**

* REST APIs and WebSocket endpoints
* Manages eco-actions, recycled items, rewards, NFT minting, ESG metrics
* Integrates Solana programs, Helius RPC, PYTH feeds, Helium IoT
* DAO & escrow smart contract management
* Authentication & role-based access

---

## **Shared Packages**

**lib/** – Solana SDK wrappers, IoT connectors, AR utilities, ESG calculators, Eco-action helpers
**hooks/** – useSettings, useSolanaProgram, usePLYToken, useRecycledItemScan, useHeliusTransactions, useARNavigation, useESGMetrics, useIoTDevices, useMapboxIoT, useEcoCampaigns
**utils/** – Distance/bearing, timestamps, blockchain helpers, ESG scoring, AR positioning, eco-action helpers
**constants/** – Material types, reward thresholds, bin & eco-action status, tokenomics constants
**config/** – API URLs, Solana RPC, Wallet & program IDs, Mapbox, Helium/Helius keys, PYTH feeds

---

## **Environment Variables (.env.example)**

```env
# Solana Programs
REACT_APP_PLY_TOKEN_PROGRAM_ID=YourPLYTokenProgramID
REACT_APP_METAPLEX_PROGRAM_ID=YourMetaplexProgramID
REACT_APP_RECYCLING_REWARD_PROGRAM_ID=YourCustomRewardProgramID
REACT_APP_ESCROW_PROGRAM_ID=YourEscrowProgramID

# Blockchain & Wallet
REACT_APP_SOLANA_RPC_URL=https://api.mainnet-beta.solana.com
REACT_APP_SOLANA_PAY_RECIPIENT=YourWalletAddressHere
REACT_APP_WALLET_SUPPORTED=Phantom,Solflare,Backpack

# APIs & Feeds
REACT_APP_HELIUS_API_KEY=YourHeliusAPIKeyHere
REACT_APP_PYTH_FEED_ID=YourPythFeedIDHere
REACT_APP_MAPBOX_ACCESS_TOKEN=YourMapboxAccessTokenHere
REACT_APP_HELIUM_API_KEY=YourHeliumAPIKeyHere
```

---

## **Tech Stack**

| Layer      | Technology                                                                  |
| ---------- | --------------------------------------------------------------------------- |
| Web        | React + Vite, TypeScript, Tailwind CSS, Mapbox, Three.js / WebXR            |
| Dashboard  | Next.js, TypeScript, Tailwind CSS, SSR, API routes                          |
| Mobile     | React Native + Expo/CLI, TypeScript, ARWayfinder, Push notifications        |
| Backend    | Node.js / Express, WebSocket / MQTT, REST API                               |
| Blockchain | Solana, Solana Pay, PLY token program, Metaplex NFT, Anchor programs        |
| Data Feeds | Helius RPC, PYTH feeds                                                      |
| Database   | PostgreSQL / Supabase                                                       |
| Analytics  | Recharts, Mapbox heatmaps                                                   |
| Shared Lib | Solana SDK wrappers, Helium IoT connectors, AR & ESG & Eco-action utilities |

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

* AI-assisted eco-action recognition (image + GPS validation)
* NFT marketplace for milestone rewards
* Multi-chain reward integration
* Predictive analytics for recycling & tree planting hotspots
* Enhanced AR Wayfinder with path guidance & ESG overlays
* Expanded shared lib/hooks/utils for external integrations
