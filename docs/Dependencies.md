# App Dependencies

## Backend Dependencies (`udagram-api`)
The backend is built with **Node.js** and **TypeScript** using the following key libraries:

- **Express**: Web framework for handling API requests.
- **Sequelize**: ORM for interacting with the PostgreSQL database.
- **pg**: PostgreSQL client for Node.js.
- **AWS SDK**: For interacting with AWS services (S3).
- **Bcrypt / JSONWebToken**: For authentication and password hashing.
- **Cors**: Middleware to enable Cross-Origin Resource Sharing.

### Build Tools
- **TypeScript**: Compiles `.ts` files to `.js`.
- **Eslint**: For code linting.

## Frontend Dependencies (`udagram-frontend`)
The frontend is a Single Page Application (SPA) built with:

- **Angular (v8)**: Main framework.
- **Ionic**: UI components and mobile-ready styles.
- **RxJS**: Reactive programming library.

### Key Configuration
- **package.json**: Defines the dependency tree.
- **package-lock.json**: Locks exact versions to ensure consistency across environments (CI vs Local).
