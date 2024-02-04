# BackEnd_Task
# Price Alert Application

## Overview

This Django project implements a price alert application that triggers an email when the user's target price for a cryptocurrency is achieved. The application includes REST API endpoints for alert management, Binance WebSocket integration for real-time price updates, email notifications, and caching for improved performance.

## Setup

1. *Clone the repository:*

    bash
    git clone https://github.com/Anay-kamal-Singh/BackEnd_Task.git
    cd price-alert-project
    

2. *Install dependencies:*

    bash
    pip install -r requirements.txt
    

3. *Set up PostgreSQL:*

    - Install PostgreSQL if not already installed.
    - Create a database for the project.
    - Update the DATABASES configuration in price_alert_project/settings.py with your PostgreSQL credentials.

4. *Configure email settings:*

    - Open price_alert_project/settings.py.
    - Update the EMAIL_* settings with your email configuration. You can use Gmail SMTP, SendGrid, or another email service.

5. *Run migrations:*

    bash
    python manage.py makemigrations
    python manage.py migrate
    

6. *Start the Django development server:*

    bash
    python manage.py runserver
    

    The application will be accessible at http://127.0.0.1:8000/.

## API Endpoints

- *Create an alert:*
    - *Endpoint:* /api/alerts/create/
    - *Method:* POST
    - *Authentication:* JWT token required

- *Delete an alert:*
    - *Endpoint:* /api/alerts/delete/<alert_id>/
    - *Method:* DELETE
    - *Authentication:* JWT token required

- *Fetch all alerts:*
    - *Endpoint:* /api/alerts/
    - *Method:* GET
    - *Authentication:* JWT token required
    - *Pagination and filtering options available*

## Binance WebSocket Integration

The application uses Binance WebSocket to get real-time price updates for cryptocurrencies.

## Email Sending Logic

When the cryptocurrency price reaches the user's specified target, an email is sent using the configured email service.

## Caching

A caching layer is implemented using Redis to improve the performance of the "fetch all alerts" endpoint.

## Docker

I haven't included the docker file :(

```bash
docker-compose up
