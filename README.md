# Expo App Setup Guide

New README file for Expo Setup

This guide outlines the process for setting up a new Expo application and explains the functionality of the `npm run reset-project` command.

## Creating an Expo App

To create a new Expo app, you typically use the `create-expo-app` command. This command sets up a new project with a basic structure and all the necessary dependencies.

1.  **Install Expo CLI (if you haven't already):**
    ```bash
    npm install -g expo-cli
    ```
    Or, if you prefer yarn:
    ```bash
    yarn global add expo-cli
    ```

2.  **Create a new project:**
    Navigate to the directory where you want to create your project and run:
    ```bash
    npx create-expo-app my-new-app
    ```
    Replace `my-new-app` with your desired project name. You will be prompted to choose a template (e.g., blank, tabs, etc.).

3.  **Navigate into your project directory:**
    ```bash
    cd my-new-app
    ```

4.  **Start the development server:**
    ```bash
    npm start
    ```
    This will open the Expo Developer Tools in your browser, and you can then open your app on a physical device using the Expo Go app or on an emulator/simulator.

## Understanding `npm run reset-project`

The `npm run reset-project` script is a utility often found in Expo projects (especially those generated from certain templates or modified for specific workflows). Its primary purpose is to clean up various cached files and re-install dependencies, bringing the project back to a fresh state, similar to how it was right after initial creation or cloning.

This command typically performs actions such as:

*   **Deleting `node_modules`:** Removes all installed Node.js packages.
*   **Deleting `package-lock.json` (or `yarn.lock`):** Removes the dependency lock file, ensuring fresh dependency resolution.
*   **Clearing Metro bundler cache:** Removes cached build artifacts that Metro (Expo's JavaScript bundler) generates.
*   **Clearing native build caches:** For bare workflow projects, it might also clear platform-specific build caches (e.g., `ios/build`, `android/build`).
*   **Re-installing dependencies:** Runs `npm install` (or `yarn install`) to fetch and install all dependencies specified in `package.json`.

**When to use `npm run reset-project`:**

*   **Solving dependency issues:** If you're encountering cryptic errors related to packages or installations.
*   **After pulling changes from a repository:** Especially if `package.json` or `package-lock.json` has changed significantly.
*   **To ensure a clean build:** Before deploying or when sharing your project with others, to guarantee a consistent environment.
*   **When switching branches:** If different branches have different dependency requirements.

Using this command helps in resolving many common development issues by ensuring your project's dependencies and caches are in a consistent and clean state.