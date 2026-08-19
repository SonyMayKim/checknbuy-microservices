
#CheckNBuy – Microservices Deployment Project

A cloud deployment project for CheckNBuy, a product comparison application built using multiple microservices and deployed with IBM Cloud Code Engine.

The project demonstrates how independent backend services can be deployed and integrated with a frontend application through REST APIs.
Project Overview

The CheckNBuy application consists of three microservices:

    Product Details – provides product and dealer information.
    Dealer Pricing – provides pricing information for products and dealers.
    Dealer Evaluation – frontend application that allows users to search for products, view available dealers, and compare prices.

For this project, the backend microservices were deployed first. The deployed API endpoints were then configured in the Dealer Evaluation frontend before deploying the frontend application.
Architecture

                    CheckNBuy
                        │
                        ▼
             Dealer Evaluation
                  Frontend
                        │
             ┌──────────┴──────────┐
             │                     │
             ▼                     ▼
      Product Details       Dealer Pricing
           API                    API
             │                     │
             ▼                     ▼
        Products &             Product
          Dealers               Prices

The frontend communicates with the backend services through HTTP API requests.
Technologies Used

    Python
    Flask
    HTML
    CSS
    JavaScript
    Axios
    REST APIs
    Docker
    IBM Cloud Code Engine
    Git
    GitHub

Project Tasks Completed
1. Product Details Microservice

The Product Details microservice was deployed using IBM Cloud Code Engine.

The service provides API endpoints used by the frontend to retrieve:

    Available products
    Dealers supplying a selected product

Example endpoints:

/products
/getdealers/<product>

2. Dealer Pricing Microservice

The Dealer Pricing microservice was deployed using IBM Cloud Code Engine.

The service provides pricing information for selected products and dealers.

Example endpoints:

/price/<dealer>/<product>
/allprice/<product>

3. Dealer Evaluation Frontend

The Dealer Evaluation frontend repository was cloned and configured to communicate with the deployed backend services.

The frontend is served using a Flask application.
4. API Endpoint Configuration

The API endpoint placeholders in index.html were replaced with the URLs of the deployed Product Details and Dealer Pricing services.

The frontend uses Axios to make HTTP requests to these APIs.
5. Frontend Deployment

The Dealer Evaluation frontend was deployed using IBM Cloud Code Engine.

After deployment, the application was accessed through its Code Engine deployment URL.
Application Functionality
Product Selection

When the application loads, available products are retrieved from the Product Details API and displayed in a dropdown.
Dealer Selection

After a product is selected, the application retrieves the dealers supplying that product and displays them in a dealer dropdown.
Individual Dealer Pricing

When a dealer is selected, the application retrieves the price offered by that dealer for the selected product.
All Dealer Pricing

The All Dealers option retrieves pricing information for all dealers offering the selected product and displays the results in a comparison table.
Frontend API Integration

The frontend uses Axios to communicate with the deployed backend services.

The main API operations are:

GET /products
GET /getdealers/<product>
GET /price/<dealer>/<product>
GET /allprice/<product>

These requests allow the frontend to dynamically retrieve product, dealer, and pricing information.
Project Structure

.
├── html/
│   └── index.html
├── app.py
├── Dockerfile
├── products.json
├── requirements.txt
├── README.md
├── LICENSE
└── .gitignore

Flask Application

The app.py file contains the Flask application used to serve the Dealer Evaluation frontend.

The application serves index.html from the html directory and uses Flask-CORS to enable cross-origin requests.
Deployment Platform

The microservices were deployed using:

IBM Cloud Code Engine

Code Engine was used to deploy the services and make their API endpoints accessible to the frontend application.
Testing

The completed application was tested after deployment to verify the integration between the frontend and backend services.

The following scenarios were successfully tested:

    Products are preloaded in the product dropdown.
    Selecting a product displays the dealers supplying it.
    Selecting a dealer displays the price offered by that dealer.
    Selecting All Dealers displays the prices offered by all dealers.

Screenshots

Screenshots demonstrating the project can be added to this repository.

Recommended screenshots include:

    Product Details successful deployment
    Dealer Pricing successful deployment
    Cloned Dealer Evaluation repository
    Updated API endpoints in index.html
    Successful Dealer Evaluation frontend deployment
    Product dropdown populated
    Dealers displayed for a selected product
    Individual dealer price displayed
    All dealer prices displayed

Learning Outcomes

This project provided hands-on experience with:

    Microservices deployment
    IBM Cloud Code Engine
    REST API integration
    Flask applications
    Frontend-to-backend communication
    Axios HTTP requests
    Docker-based application deployment
    Git and GitHub
    Testing cloud-deployed applications

Author
Madina Kuyumdzhieva
