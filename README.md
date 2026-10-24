# e-plantShopping

**Paradise Nursery** is a React shopping cart application for browsing and buying houseplants. This repository, `e-plantShopping`, is the final project for the IBM React course. It uses Redux Toolkit for global cart state.

**Live demo:** https://borkoandy.github.io/e-plantShopping/

## Features

### Landing page
- Paradise Nursery name and a short company description
- Background image
- "Get Started" button that opens the product listing page

### Product listing page
- Five plant categories, each with six plants: Air Purifying, Aromatic Fragrant, Insect Repellent, Medicinal, and Low Maintenance
- Each plant card shows a thumbnail, name, description, and price
- "Add to Cart" button that adds the plant to the cart, then disables and changes to "Added to Cart"
- Navbar with Home (Paradise Nursery), Plants, and Cart links
- Cart icon that shows the total number of items in real time

### Shopping cart page
- Thumbnail, name, and unit price for each plant
- Increase and decrease quantity buttons, with subtotals and totals updating instantly
- Delete button to remove a plant from the cart
- Total cart amount for all plants
- "Continue Shopping" button back to the product listing
- "Checkout" button that shows a "Coming Soon" message

## Tech stack

- React 18
- Redux Toolkit and React Redux
- Vite
- gh-pages for deployment

## Project structure

```
e-plantShopping/
├── public/
├── src/
│   ├── App.jsx          # Landing page and page switching
│   ├── App.css          # Landing page styles and background image
│   ├── AboutUs.jsx      # Company information
│   ├── ProductList.jsx  # Product listing page and navbar
│   ├── CartItem.jsx     # Shopping cart page
│   ├── CartSlice.jsx    # Redux slice: addItem, removeItem, updateQuantity
│   ├── store.js         # Redux store configuration
│   └── main.jsx         # App entry point with Redux Provider
├── package.json
└── vite.config.js
```

## Redux state

The store has one slice, `cart`, with an `items` array. Each item holds `name`, `image`, `cost`, and `quantity`.

| Action | Payload | Effect |
| --- | --- | --- |
| `addItem` | plant object | Adds the plant, or increases its quantity if already in the cart |
| `removeItem` | plant name | Removes the plant from the cart |
| `updateQuantity` | `{ name, quantity }` | Sets the plant's quantity |

## Getting started

```bash
git clone https://github.com/BorkoAndy/e-plantShopping.git
cd e-plantShopping
npm install
npm run dev
```

Open the local address Vite prints. The app is served under the base path `/e-plantShopping`.

To test a production build:

```bash
npm run build
npm run preview
```

## Deployment

The app is deployed to GitHub Pages with `gh-pages`:

```bash
npm run deploy
```

`vite.config.js` sets `base: "/e-plantShopping"` so asset paths match the repository name. In the repository settings, GitHub Pages is set to serve the `gh-pages` branch.

## Author

Andy Borko

## License

The course material this project is based on is licensed under [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0).