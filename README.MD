# Machine Coding (Frontend Reactjs) - Subscripton/Plan Management Task

## Task Objective

The goal of this task is to implement a frontend application that interacts with the provided APIs to manage subscriptions.

1. Account for potential API failures and provide appropriate feedback to the user.
2. Retrieve subscription details using the APIs `GET /api/subscriptions`.
3. Retrieve current subscription by calling the API `GET /api/subscriptions/current`
4. Present the fetched subscription information in a user-friendly interface.
5. Enable users to upgrade their subscriptions by calling the upgrade API `POST /api/subscriptions/upgrade`.
6. Enable users to downgrade their subscriptions by calling the downgrade API `POST /api/subscriptions/downgrade`.
7. Refetch or update the data in the state after successful `upgrades` or `downgrades`.

## APIs Overview

You are provided with the following APIs to interact with:

- **API failure type**

    ```typescript
    type ApiFailureType = {
      status: "failure";
      error: string;
    }
    ```

- **Subscription type**

    ```typescript
    type SubscriptionDataType = {
        price: number;
        code: string;
        tag: string;
        currency: string;
    };
    ```

- **Get All Subscriptions**  
    **Endpoint:** `GET /api/subscriptions`  
    **Description:** Fetches all available subscription plans.  
    **Success Response:**  

    ```typescript
    type GetSubscriptionsListApiResponse = {
      status: "success";
      data: SubscriptionDataType[];
    }
    ```

- **Get Current Subscription**  
    **Endpoint:** `GET /api/subscriptions/current`  
    **Description:** Fetches current subscription plan.  
    **Success Response:**  

    ```typescript
    type GetCurrentSubscriptionApiResponse = {
      status: "success";
      data: SubscriptionDataType;
    }
    ```

- **Upgrade Current Subscription**
    **Endpoint:** `POST /api/subscriptions/upgrade`  
    **Description:** Upgrade current subscription plans to plan that you want to upgrade to.

    **Api Body Type:**

    ```typescript
    type UpradeSubscriptionApiBody = {
      code: string // Subscription code that you want to upgrade to
    }
    ```

    **Success Response:**  

    ```typescript
    type UpradeSubscriptionApiResponse = {
      status: "success";
      data: SubscriptionDataType;
    }
    ```

- **Downgrade Current Subscription**
    **Endpoint:** `POST /api/subscriptions/downgrade`  
    **Description:** Downgrade current subscription plans to plan that you want to downgrade to.

    **Api Body Type:**

    ```typescript
    type UpradeSubscriptionApiBody = {
      code: string // Subscription code that you want to downgrade to
    }
    ```

    **Success Response:**  

    ```typescript
    type DowngradeSubscriptionApiResponse = {
      status: "success";
      data: SubscriptionDataType;
    }
    ```

## Development Commands

Run these command from root directory

- Install Dependencies

  ```sh
    npm install
  ```

- Start server

  ```sh
    npm run start:server
  ```

- Start React App

  ```sh
    npm run dev:app
  ```
  