# FoodDistributionPro (Visual Studio-ready)

This is a professional demo solution that opens cleanly in **Visual Studio 2022**.

## Tech
- .NET 8 ASP.NET Core Web (Web API + SPA Proxy)
- React (Vite) inside `ClientApp`
- SQL Server database script with **25+ tables** and **8 stored procedures**

## 1) Open the solution
Open `FoodDistributionPro.sln` in Visual Studio 2022.

## 2) Create the database
Run:
- `database/FoodDistributionProDb.sql` in SSMS (or Azure Data Studio)

It creates:
- DB `FoodDistributionProDb`
- Tables, relationships, constraints, indexes
- Seed data
- Types (TVPs) and Stored Procedures

## 3) Run the app
In Visual Studio:
- Set **FoodDistribution.Web** as Startup Project
- Press **F5**
- Swagger opens at `/swagger`
- SPA launches via proxy: React dev server on `http://localhost:5173`

### Notes
If npm doesn't start automatically:
```bash
cd src/FoodDistribution.Web/ClientApp
npm install
npm run dev
```
Then run the .NET project.

## API endpoints
- GET `/api/locations`
- GET `/api/products`
- GET `/api/customers`
- GET `/api/orders`
- POST `/api/orders/sp` (uses stored proc `sp_CreateOrder` with TVP)
- GET `/api/shipments`
- POST `/api/shipments/sp` (uses stored proc `sp_CreateShipment` with TVP)
- GET `/api/dashboard` (stored proc metrics)
