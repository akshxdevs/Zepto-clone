Zepto Clone
===========

A responsive e-commerce web app cloning Zepto's quick grocery delivery platform. Powered by Next.js, Tailwind CSS, and Framer Motion for ultra-fast UI interactions.

Overview
--------

Zepto Clone replicates the core experience of Zepto's 10-minute grocery delivery service, featuring a sleek search bar, categorized product grids, dynamic cart management, and checkout flows. Users can browse fresh produce, essentials, and household items with real-time pricing, add-ons, and lightning-fast load times---perfect for building a modern quick-commerce frontend.

Getting Started
---------------

1.  Set up environment variables by creating a .env.local file in the root directory:

bash

```
# Required: API base URL for product data (mock or backend)
NEXT_PUBLIC_API_URL=http://localhost:3001/api
# Optional: Analytics tracking ID (e.g., Google Analytics)
NEXT_PUBLIC_GA_ID=your_ga_id
# Optional: Stripe publishable key for payments
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=pk_test_your_key
```

1.  Install the dependencies:

bash

```
npm install
# or
yarn install
# or
pnpm install
```

1.  Run the development server:

bash

```
npm run dev
# or
yarn dev
# or
pnpm dev
```

1.  Open <http://localhost:3000> to see the demo app.

Integration Guide
-----------------

### 1\. Configure Product Data

Add or mock product catalogs in lib/products.ts:

typescript

```
// lib/products.ts
export const categories = [
  {
    id: "fruits",
    name: "Fresh Fruits",
    items: [
      { id: 1, name: "Apples", price: 99, image: "/apples.jpg", inStock: true },
      // Add more items
    ],
  },
  // More categories: veggies, dairy, etc.
];
```

### 2\. Embed the Cart Component

Integrate the cart into your layout for seamless shopping.

tsx

```
// In app/layout.tsx or page
import { CartProvider, useCart } from '@/components/cart/CartContext';
import { SearchBar, ProductGrid } from '@/components/grocery';

export default function GroceryPage() {
  return (
    <CartProvider>
      <div className="min-h-screen bg-gray-50">
        <SearchBar />
        <ProductGrid category="fruits" />
        <CartModal /> {/* Renders on demand */}
      </div>
    </CartProvider>
  );
}
```

### 3\. Customize the Look

The app uses Tailwind CSS and Framer Motion for animations. Override styles through:

-   Custom Tailwind config in tailwind.config.js
-   Component props for themes (e.g., dark mode toggle)
-   CSS variables for branding colors

Features
--------

-   🛒 Intuitive search with autocomplete and filters
-   🥦 Categorized product browsing with high-res images
-   🛍️ Real-time cart updates and quantity controls
-   💳 Quick checkout with address auto-fill
-   🚀 10-min delivery ETA simulator
-   📱 Fully responsive mobile-first design
-   ⚡ Smooth animations and loading states
-   🔍 Wishlist and order history mockups

Learn More
----------

-   [Project Demo](https://zepto-clone.vercel.app)
-   [Tailwind Docs](https://tailwindcss.com/docs)
-   [Framer Motion Guide](https://www.framer.com/motion/)

License
-------

This project is licensed under the MIT License - see the LICENSE file for details.
