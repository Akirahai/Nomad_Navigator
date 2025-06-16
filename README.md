# Nomad Navigator - A  Project

Welcome to Nomad Navigator, a Next.js application designed to help users discover and book accommodations worldwide. This project is built with Next.js (App Router), React, ShadCN UI components, Tailwind CSS, and Genkit for AI-powered features.

## Getting Started

### Prerequisites

Ensure you have Node.js (version 18 or later recommended) and npm installed on your system.

### Running the Application

1.  **Install Dependencies**:
    Open your terminal, navigate to the project's root directory, and run:
    ```bash
    npm install
    ```

2.  **Run the Next.js Development Server**:
    To start the main application (frontend and Next.js backend), run:
    ```bash
    npm run dev
    ```
    This will typically start the app on `http://localhost:9002`.

3.  **Run the Genkit Development Server (for AI features)**:
    If you are working on or testing AI features powered by Genkit, you'll need to run the Genkit development server in a separate terminal:
    ```bash
    npm run genkit:dev
    ```
    Or, if you want Genkit to automatically reload on file changes:
    ```bash
    npm run genkit:watch
    ```
    The Genkit server usually starts on `http://localhost:4000` (or another port if 4000 is busy), where you can inspect flows and traces.

### Environment Variables

Some features, particularly those involving external APIs like Google Maps, might require API keys. These should be stored in a `.env.local` file in the project root. For example:

```
NEXT_PUBLIC_GOOGLE_MAPS_API_KEY=YOUR_GOOGLE_MAPS_API_KEY
```

Refer to the specific documentation for each service to obtain the necessary API keys.

## Project Structure

Here's an overview of the key directories and files in the project:

-   **`/` (Root Directory)**
    -   `next.config.ts`: Configuration for Next.js.
    -   `tailwind.config.ts`: Configuration for Tailwind CSS.
    -   `tsconfig.json`: Configuration for TypeScript.
    -   `package.json`: Lists project dependencies and scripts.
    -   `apphosting.yaml`: Configuration for Firebase App Hosting.
    -   `components.json`: ShadCN UI configuration.
    -   `README.md`: This file.

-   **`src/`**: Contains the main source code for the application.

    -   **`src/app/`**: Core of the Next.js application, using the App Router.
        -   `(main)/`: Route group for main application pages (e.g., homepage, search).
            -   `layout.tsx`: Layout for the main application pages.
        -   `booking/`: Pages and logic related to the booking process.
            -   `actions.ts`: Server Actions for handling booking creation.
            -   `confirmation/page.tsx`: Booking confirmation page.
            -   `page.tsx`: Main booking page.
        -   `hotels/`: Pages related to hotel listings and details.
            -   `[hotelId]/page.tsx`: Dynamic page for individual hotel details.
            -   `search/page.tsx`: Hotel search results page.
        -   `login/page.tsx`: User login page.
        -   `profile/page.tsx`: User profile page.
        -   `signup/page.tsx`: User signup page.
        -   `globals.css`: Global styles and Tailwind CSS base/component/utility layers, including ShadCN theme variables.
        -   `layout.tsx`: The root layout for the entire application.
        -   `page.tsx`: The main homepage of the application.

    -   **`src/components/`**: Reusable React components.
        -   `features/`: Components specific to certain application features.
            -   `destination-search/`: Components for destination search functionality.
            -   `hotel-search/`: Components for hotel search and map view.
        -   `shared/`: General-purpose components used across multiple features or pages (e.g., `Header.tsx`, `Footer.tsx`, `PageContainer.tsx`, `Logo.tsx`, `AppProviders.tsx`).
        -   `ui/`: UI components from ShadCN (e.g., `Button.tsx`, `Card.tsx`, `Input.tsx`). These are generally not modified directly but are used to build other components.

    -   **`src/ai/`**: Files related to AI functionality using Genkit.
        -   `flows/`: Contains Genkit flow definitions (e.g., for processing user queries, generating content).
        -   `genkit.ts`: Global Genkit instance configuration and plugin setup.
        -   `dev.ts`: Entry point for the Genkit development server.

    -   **`src/hooks/`**: Custom React hooks (e.g., `useToast.ts`, `useMobile.ts`).

    -   **`src/lib/`**: Utility functions, constants, and type definitions.
        -   `constants.ts`: Application-wide constants (e.g., mock data, configuration values).
        -   `utils.ts`: General utility functions (e.g., `cn` for class names).

    -   **`src/types/`**: TypeScript type definitions and interfaces used throughout the application.
        -   `index.ts`: Main file exporting all types.

-   **`public/`**: Static assets that are served directly (e.g., images, fonts, favicon).

## Key Technologies

-   **Next.js**: React framework for server-side rendering, static site generation, and more.
-   **React**: JavaScript library for building user interfaces.
-   **TypeScript**: Superset of JavaScript that adds static typing.
-   **Tailwind CSS**: Utility-first CSS framework for rapid UI development.
-   **ShadCN UI**: Collection of beautifully designed, accessible UI components.
-   **Genkit**: Toolkit for building AI-powered features, integrated with models like Gemini.
-   **Zod**: TypeScript-first schema declaration and validation library.
-   **React Hook Form**: For managing forms with validation.
-   **Lucide React**: Library for beautiful and consistent icons.
-   **Date-fns**: Modern JavaScript date utility library.

## Contributing

This project is managed within Firebase Studio. For major changes or contributions, please coordinate with the project maintainers.

Happy Coding!
