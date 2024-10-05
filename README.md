

# Contrates - Exchange Rate API

Contrates is a backend application built with NestJS that provides an API for fetching and managing exchange rates. It allows users to retrieve the latest exchange rates, convert currencies, and access historical exchange data.

## Table of Contents

- [Features](#features)
- [Technologies](#technologies)
- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Database Schema](#database-schema)
- [Testing](#testing)
- [Contributing](#contributing)
- [License](#license)

## Features

- Fetch real-time exchange rates from a third-party API
- Manage historical exchange rates in a PostgreSQL database
- Convert amounts between different currencies
- RESTful API with well-defined endpoints

## Technologies

- [NestJS](https://nestjs.com/) - A progressive Node.js framework
- [PostgreSQL](https://www.postgresql.org/) - A powerful relational database
- [TypeORM](https://typeorm.io/) - ORM for TypeScript and JavaScript
- [Axios](https://axios-http.com/) - Promise-based HTTP client for the browser and Node.js

## Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/your-username/contrates.git
   cd contrates
   ```

2. **Install dependencies:**

   ```bash
   npm install
   ```

3. **Set up the database:**
   - Create a PostgreSQL database for your application.
   - Update the database connection details in the `src/config/database.config.ts` file.

4. **Run migrations (if any):**

   ```bash
   npm run typeorm migration:run
   ```

## Usage

1. **Start the development server:**

   ```bash
   npm run start:dev
   ```

2. The API will be running at `http://localhost:3000`.

## API Endpoints

### Exchange Rates

- **Get the latest exchange rates**
  - **URL:** `/api/rates/latest`
  - **Method:** `GET`

- **Get exchange rates for a specific currency**
  - **URL:** `/api/rates/:currency`
  - **Method:** `GET`

- **Create a new exchange rate entry**
  - **URL:** `/api/rates`
  - **Method:** `POST`
  - **Body:** 
    ```json
    {
      "baseCurrency": "USD",
      "targetCurrency": "EUR",
      "rate": 0.85,
      "timestamp": "2023-10-01T00:00:00Z"
    }
    ```

- **Update an existing exchange rate entry**
  - **URL:** `/api/rates/:id`
  - **Method:** `PUT`
  - **Body:**
    ```json
    {
      "rate": 0.84
    }
    ```

- **Delete an exchange rate entry**
  - **URL:** `/api/rates/:id`
  - **Method:** `DELETE`

### Currencies

- **Get all currencies**
  - **URL:** `/api/currencies`
  - **Method:** `GET`

## Database Schema

### ExchangeRate Model

- `id`: string (primary key)
- `baseCurrency`: string
- `targetCurrency`: string
- `rate`: number
- `timestamp`: Date

### Currency Model

- `id`: string (primary key)
- `name`: string
- `code`: string
- `symbol`: string

## Testing

To run the tests, use the following command:

```bash
npm run test
```

## Contributing

Contributions are welcome! Please fork the repository and create a pull request for any enhancements or bug fixes.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.
```

### Instructions to Use
1. Replace `your-username` in the clone URL with your GitHub username.
2. Update any specific details related to your project, such as database configurations or additional endpoints.
3. Add any other sections as necessary, like error handling or security practices.

Feel free to ask if you need further modifications!