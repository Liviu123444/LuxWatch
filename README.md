# LuxWatch — Demo Luxury Watches Shop (Deployable)

This repository is a **demo** e-commerce frontend built with **React + Vite** and a simple 3D viewer using **@react-three/fiber**. It ships with placeholder procedural 3D models (primitives) so you can run it immediately and later replace them with `.glb` models.

## Features
- Product listing (Rolex / Hublot / Patek Philippe demo items)
- Client-side cart (add/remove/change qty)
- 3D product viewer (replaceable with GLB/GLTF files)
- Ready for deployment to Vercel/Netlify

## How to run locally

1. Install dependencies:
```bash
npm install
```

2. Start dev server:
```bash
npm run dev
```

Open http://localhost:5173

## How to replace 3D models
- Put your `.glb` or `.gltf` files into `public/models/`
- In `src/components/Product3DViewer.jsx` replace `WatchModel` with a `useGLTF('/models/your.glb')`
- Example (use @react-three/drei):
```jsx
import { useGLTF } from '@react-three/drei'
const { scene } = useGLTF('/models/rolex.glb')
return <primitive object={scene} />
```

## Checkout & Payments
This project contains a demo "Checkout" button only. For real payments:
- Create a serverless function or backend endpoint for Stripe Checkout Sessions or Payment Intents.
- Never include secret keys in frontend code.
- Use Stripe docs: https://stripe.com/docs/payments/accept-a-payment

## Deploy to Vercel
1. Create a new Vercel project and connect this repo (or drag & drop the folder).
2. Build command: `npm run build` and Output directory: `dist`.
3. Add environment variables if you implement a server for payments.

---

**Important:** This is a demo storefront for prototyping and presentation. Replace demo assets, add legal pages (returns, terms, privacy), and secure payment backend before accepting real orders.
