# Bitcoin Price Tracker

This project is a full-stack application for converting an amount in USD to Bitcoin (BTC), fetching real-time conversion offers from multiple providers. It uses React and TypeScript for the frontend, with Vite as the build tool, and `aircode` for a serverless backend that handles data fetching and caching.

## Features

- **Real-time Conversion**: Fetches current conversion rates for converting USD to BTC from multiple providers (Paybis, Guardarian, Moonpay, Transak).
- **Responsive UI**: A clean and responsive user interface built with React and Tailwind CSS.
- **Debounced Input**: Provides a smooth user experience with debounced input to reduce API calls while typing.
- **Cached Offers**: Utilizes a serverless backend to cache offers and reduce unnecessary external API requests.

## Technologies Used

### Frontend

- **React**: Library for building user interfaces.
- **TypeScript**: For static type checking and enhanced developer experience.
- **Vite**: A fast build tool for development and production.
- **Tailwind CSS**: Utility-first CSS framework for styling components.
- **Axios**: For handling HTTP requests to the backend and third-party APIs.
- **Lodash**: Utility library for handling tasks like sorting and data manipulation.
- **use-debounced-effect**: For debouncing side effects in React hooks.

### Backend

- **Aircode**: A serverless backend framework for handling cloud functions and database operations.
- **Axios**: For making HTTP requests to third-party services to retrieve conversion rates.
- **TypeScript**: Provides type safety and improved maintainability.

## Project Structure

```
.
├── backend                    # Contains serverless functions and data handling
│   ├── cache.ts               # Handles caching of offer data to database
│   ├── cachedValues.ts        # Retrieves cached offers for different providers
│   ├── offers.ts              # Main function to get conversion rates for a given amount
│   └── providers.ts           # Fetches offers from various external APIs (e.g., Paybis, Guardarian)
├── public                     # Public assets and HTML file for the React app
├── src                        # Main frontend application code
│   ├── AmountInput.tsx        # Input component for entering the USD amount
│   ├── App.tsx                # Main application component
│   ├── Input.tsx              # Reusable input field component
│   ├── LoadingSkeleton.tsx    # Skeleton loader for displaying loading state
│   ├── ResultRow.tsx          # Component to display provider offers in a tabular format
│   ├── assets                 # Contains images and logos for providers
│   ├── index.css              # Global styles for the application
│   └── main.tsx               # Entry point of the React application
├── package.json               # Project metadata, dependencies, and scripts
└── tailwind.config.js         # Tailwind CSS configuration
```

## Getting Started

### Prerequisites

- **Node.js**: Make sure you have Node.js installed to run the application.
- **Yarn or npm**: Use either package manager to install dependencies.

### Installation

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd coins-table
   ```

2. **Install frontend dependencies**:
   ```bash
   yarn install
   # or with npm
   npm install
   ```

3. **Install backend dependencies**:
   ```bash
   cd backend
   yarn install
   # or with npm
   npm install
   ```

### Running the Application

1. **Frontend**: 
   Start the development server for the React frontend.
   ```bash
   yarn dev
   # or with npm
   npm run dev
   ```
   This will run the frontend on `http://localhost:3000`.

2. **Backend**:
   Since the backend uses `aircode`, make sure you have an `aircode` environment set up. Deploy backend functions to `aircode` as per the framework’s documentation.

### Building for Production

To build the frontend for production:
```bash
yarn build
# or with npm
npm run build
```
The built files will be located in the `dist` directory.

## Project Workflow

1. **User Input**: The user enters an amount in USD using the `AmountInput` component.
2. **Debounced API Call**: The input is debounced to avoid frequent API calls, and the backend is queried for conversion offers.
3. **Fetching Offers**: The backend fetches conversion rates from third-party providers (Paybis, Guardarian, etc.), caches the results, and returns the best offers.
4. **Display Results**: The frontend displays the results in a tabular format with clickable links to provider sites.
5. **Caching**: Offers are cached on the backend to improve performance and reduce the load on external APIs.

## License

This project is licensed under the MIT License.

