# Repository Guidelines

## Project Structure & Module Organization
This repository contains the **PropertyFlowHQ Mobile App**, built with **React Native** and **Expo**. The source code is organized within the `.\propertyflowhq-app` directory:

- **`.\propertyflowhq-app\src\app`**: File-based routing using **Expo Router**. Routes are grouped by role: `(agent)`, `(auth)`, `(contractor)`, `(employee)`, `(homeowner)`, `(marketplace)`, `(pm)`, `(public)`, and `(tenant)`.
- **`.\propertyflowhq-app\src\components`**: Shared UI components, including specialized modules like `chat-widget` and `sheets`.
- **`.\propertyflowhq-app\src\lib`**: Core logic, including API clients (`api.ts`), biometric handling, and OCR utilities.
- **`.\propertyflowhq-app\src\ui`**: Atomic UI building blocks (Button, Card, Input, etc.) following the project's design system.
- **`.\propertyflowhq-app\src\hooks`**: Custom React hooks for data fetching (`queries.ts`) and platform features.

## Build, Test, and Development Commands
Commands should be executed within the `.\propertyflowhq-app` directory:

- **`npm start`**: Starts the Expo development server.
- **`npm run android`**: Runs the app on an Android emulator or device.
- **`npm run ios`**: Runs the app on an iOS simulator or device.
- **`npm run web`**: Starts the app in a web browser.
- **`npm run lint`**: Runs Expo's linting configuration.
- **`npm run reset-project`**: Moves starter code to `app-example` and creates a blank `app` directory.

## Coding Style & Naming Conventions
- **TypeScript**: Strict mode is enabled. Use `@/*` paths for imports from the `src` directory.
- **Styling**: Uses **NativeWind** (Tailwind CSS for React Native). Follow the theme tokens defined in `.\propertyflowhq-app\src\theme\tokens.ts`.
- **Design Benchmark**: Visuals must align with high-end consumer products (Uber, Upwork, Fiverr).
- **Navigation**: 
    - Use `animation: 'slide_from_right'` for stack transitions.
    - Prefer `navigation.goBack()` for back actions to preserve animations.
    - Use `lazy: true` for bottom tab navigators.
- **Components**: Every component must handle loading, empty, and error states. Use `FlatList` or `SectionList` for large datasets instead of `ScrollView`.

## Testing Guidelines
- **Linting**: Enforced via `expo lint`.
- **Unit Testing**: Project is prepared for **Jest**, though no specific test scripts are currently defined in `package.json`. Follow official Expo guides for adding unit tests.

## Monorepo Context & API
- This app consumes the same backend as the **PropertyFlowHQ Website** (located in a separate repository at `c:\Users\earth\Desktop\PropertyFlowHQ`).
- **MANDATORY**: Always verify API contracts and data shapes against the web app's Prisma schema and API routes before implementation. Do not invent data structures.
