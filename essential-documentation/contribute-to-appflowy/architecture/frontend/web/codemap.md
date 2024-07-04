# 🗺 Web Project Structure: CodeMap

This document outlines the project structure for the web implementation of AppFlowy.

🌟 Main Directory Structure

The project is structured into several key directories, each serving a distinct purpose within the overall architecture:

- **`index.html`**: The main HTML file for the application. 📄
- **`src`**: Contains all source code for the application.
  - **`components`**: Holds reusable UI components. 🔄
    - **`app`**: Contains the main application components. 📦
      - **`App.tsx`**: The router and main component of the application. 📦
      - **`AppTheme.tsx`**: The theme provider for the application. 🎨
      - **`AppConfig.tsx`**: The configuration provider for the application. ⚙️
    - **`document`**: Contains components for the document page. 📄
      - **`Document.tsx`**: The document component. 📄
    - **`database`**: Contains components for the database page. 📄
      - **`Database.tsx`**: The database component. 📄
      - **`DatabaseRow.tsx`**: The single row component for the database. 📄
      - **`grid`**: Contains the grid component for the database. 📄
      - **`board`**: Contains the board component for the database. 📄
      - **`calendar`**: Contains the calendar component for the database. 📄
      - **`components`**: Contains the components for the database. 📄
    - **`editor`**: Contains components for the editor. 📄
      - **`command`**: Custom commands for the editor. 📄
      - **`components`**: Components for the editor. 📄
        - **`blocks`**: Blocks for the editor. 📄
        - **`element`**: Elements for the editor. 📄
        - **`leaf`**: Leaves for the editor. 📄
      - **`plugins`**: Plugins for the editor. 📄
      - **`utils`**: Utility functions for the editor. 📄
      - **`Editor.tsx`**: The editor component. 📄
    - **`publish`**: Contains components for publishing. 📄
      - **`PublishView.tsx`**: The publish view component. 📄
      - **`header`**: Contains the header component for publishing. 📄
  - **`error`**: Contains error components. 🚨
    - **`ErrorBoundary.tsx`**: The error boundary component. 🚨
    - **`ErrorFallback.tsx`**: The error fallback component. 🚨
  - **`pages`**: Contains different pages of the application. 🖥️
    - **`PublishPage.tsx`**: The publish page. 🖥️
  - **`application`**: Contains the main application logic. 🧠
    - **`services`**: Contains services for the application. 🛠️
      - `js-services`: Contains JavaScript services for the application. 🛠️
        - `index.ts`: Exports all methods for the JavaScript services. 🛠️
        - `fetch.ts`: Contains methods for fetching data. 🛠️
        - `cache`: Contains methods for caching data. 🛠️
        - `wasm`: Contains methods for WebAssembly. 🛠️
          - `client-api.ts`: Contains methods for the WebAssembly client API. 🛠️
      - `tauri-services`: Contains Tauri services for the application. 🛠️
      - `index.ts`: Exports the service of current environment. 🛠️
      - `service.type.ts`: Defines the service type. 🛠️
    - **`slate-yjs`**: Adapter for Slate and Yjs. 🧠
      - `index.ts`: Exports the Slate Yjs adapter. 🧠
      - `plugins`: Contains plugins for Slate Yjs. 🧠
        - `withYjs.ts`: Contains the Yjs plugin for Slate. 🧠
      - `utils`: Contains utility functions for Slate Yjs. 🧠
    - **`database-yjs`**: Deals with the database data
      - **`fields`**: Contains the fields for the database. 🧠
      - **`index.ts`**: Exports the database Yjs adapter. 🧠
      - **`context.ts`**: Contains the database context. 🧠
      - **`selectors.ts`**: Contains the database selectors. 🧠
      - **`database.type.ts`**: Defines the database type. 🧠
      - **`filter.ts`**: Provides filtering for the database. 🧠
      - **`sort.ts`**: Provides sorting for the database. 🧠
      - **`group.ts`**: Provides grouping for the database. 🧠
      - **`cell.type.ts`**: Defines the cell type for the database. 🧠
      - **`cell.parse.ts`**: Parses the cell for the database. 🧠
  - **`utils`**: Stores utility functions and helpers. 🔧
  - **`assets`**: Contains static assets such as images and fonts. 🖼️
  - **`i18n`**: Configures internationalization for the application. 🌐
    - **`config.ts`**: Configures the i18n library. 🌐
  - **`styles`**: Contains global styles for the application. 🎨
    - **`variables`**: Defines global CSS variables. 🎨
      - **`light.variables.css`**: Defines light mode CSS variables. 🌞
      - **`dark.variables.css`**: Defines dark mode CSS variables. 🌚
    - **`mixin.scss`**: Contains global SCSS mixins. 🎨
    - **`tailwind.css`**: Configures Tailwind CSS. 🎨
    - **`template.css`**: Contains global CSS styles. 🎨
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
  - **`create-symlink.cjs`**: Creates a symlink for the project. 🔗
  - **`generateTailwindColors.cjs`**: Generates Tailwind CSS colors. 🎨
  - **`i18n.cjs`**: Generates i18n translations. 🌐