# 🗺 Web Project Structure: CodeMap

This document outlines the project structure for the web implementation of AppFlowy.

🌟 Main Directory Structure

The project is structured into several key directories, each serving a distinct purpose within the overall architecture:

- **`index.html`**: The main HTML file for the application. 📄
- **`src`**: Contains all source code for the application.
  - **`components`**: Holds reusable UI components. 🔄
    - **`app`**: Contains the main application components. 📦
    - **`document`**: Contains components for the document page. 📄
    - **`database`**: Contains components for the database page. 📄
    - **`editor`**: Contains components for the editor. 📄
    - **`publish`**: Contains components for publishing. 📄
  - **`error`**: Contains error components. 🚨
  - **`pages`**: Contains different pages of the application. 🖥️
  - **`application`**: Contains the main application logic. 🧠
    - **`services`**: Get YDoc and deal with cache. 📦
    - **`slate-yjs`**: Adapter for Slate and Yjs. 🧠
    - **`database-yjs`**: Deals with the database data
  - **`utils`**: Stores utility functions and helpers. 🔧
  - **`assets`**: Contains static assets such as images and fonts. 🖼️
  - **`i18n`**: Configures internationalization for the application. 🌐
  - **`styles`**: Contains global styles for the application. 🎨
  - **`main.ts`**: The main entry point for the application. 🚀
- **`public`**: Includes static resources such as images and stylesheets. 🖼️

🚀 Deploy
- **`deploy`**: Contains deployment configurations. 🚀
  - **`Dockerfile`**: Configures the Docker image for the application. 🐳
  - **`nginx.conf`**: Configures the Nginx server for the application. 🌐
  - **`server.ts`**: Configures the server for the application. 🌐
  - **`start.sh`**: Script to start the application. 🚀
  - **`deploy.sh`**: Script to deploy the application. 🚀
  - **`supervisord.conf`**: Configures the Supervisor daemon. 🚀
- **`dist`**: Contains the production build of the application. 🚀

🧪 Test Configuration

- **`cypress`**: Contains end-to-end tests using Cypress. 🧪
- **`jest.config.cjs`**: Configures Jest testing framework. 🃏
- **`cypress.config.ts`**: Configures Cypress end-to-end testing framework. 🧪

🔧 Configuration Files

To ensure a consistent development environment and to facilitate various aspects of the application lifecycle, we use several configuration files:

- **`package.json`**: Contains metadata about the project and its dependencies. 📦
- **`tsconfig.json`**: Configures TypeScript compiler options. 🛠️
- **`vite.config.ts`**: Configures the Vite build tool. 🛠️
- **`tailwind.config.cjs`**: Configures Tailwind CSS. 🎨
- **`postcss.config.cjs`**: Configures PostCSS. 🎨
- **`.eslintrc.cjs`**: Configures ESLint. 🧹
- **`.eslintignore`**: Specifies files and directories to ignore during linting. 🧹
- **`.prettierrc.cjs`**: Configures Prettier. 🧹
- **`.gitignore`**: Specifies files and directories to ignore in Git. 🚫
- **`.nycrc`**: Configures Istanbul code coverage tool. 📊
- **`srcipts`**: Contains scripts for various tasks. 📜