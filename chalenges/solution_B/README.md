## 💻 Section B: Problem Solving Task

**Challenge:**  
Write pseudocode or  code in Laravel (PHP) or JavaScript/TypeScript (Next.js programming language for the following challenge:
Given a list of services with ratings, return the top 3 in descending order.

### Example Input:
```json
[
  { "name": "Tutoring", "rating": 4.6 },
  { "name": "Food Delivery", "rating": 4.9 },
  { "name": "Tech Support", "rating": 4.3 },
  { "name": "Child Care", "rating": 4.8 }
]
```

### Expected Output:
```json
[
  { "name": "Food Delivery", "rating": 4.9 },
  { "name": "Child Care", "rating": 4.8 },
  { "name": "Tutoring", "rating": 4.6 }
]
```

## **PseudoCode**
Function: getTopServices(serviceList)

Input: serviceList (a list of service objects, each with a name and rating)

Sort: Create a new list called sortedServices. Sort serviceList in descending order based on the rating property of each service.

Slice: Take the first three elements from sortedServices.

Return: Return the new list containing the top three services.


## **Code**
'use client';

import { useEffect } from 'react';

// Define Typescript type for a service object
type Service = {
  name: string;
  rating: number;
};

function getTopServices(services: Service[]): Service[] {
  return services
    .sort((a, b) => b.rating - a.rating) // Sort in Descending order; from highest to lowest rating
    .slice(0, 3); // Return top 3 services
}

// Example usage:
export default function Home() {
  const services: Service[] = [
    { name: "Tutoring", rating: 4.6 },
    { name: "Food Delivery", rating: 4.9 },
    { name: "Tech Support", rating: 4.3 },
    { name: "Child Care", rating: 4.8 },
  ];

const topServices = getTopServices(services);

  // Log to browser console when component loads
  useEffect(() => {
    console.log("Top 3 Services:");
    console.log(topServices);
  }, [topServices]);

  return (
    <main>
      <h1>Top 3 Services</h1>
      <ul>
        {topServices.map((service, index) => (
          <li key={index}>
            {service.name} - {service.rating}
          </li>
        ))}
      </ul>
    </main>
  );
}


## **How to Run The Code in a Next.js Project with TypeScript**
Step 1: Create a Next.js App with TypeScript
- Open terminal and run:
npx create-next-app@latest app-name --typescript
cd app-name

Step 2: Add the Code
- Inside the project folder, go to:
/src/app/page.tsx
Paste the code

Step 3: Run the App
npm run dev

- Visit: http://localhost:3000 in your browser.
- You'll see the output in the page. To view the console output, Right click on the page, go to Inspect, then Console tab