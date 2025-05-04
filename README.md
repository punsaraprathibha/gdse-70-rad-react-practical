# 🚀 Getting Started with Your React + TypeScript Project

Follow these simple steps to kick off your first React project with TypeScript:

## ✅ Step 1: Create a New React + TypeScript Project

You can either use the GUI or the command line:

### Using GUI (e.g., in IDE like WebStorm or IntelliJ):
- Navigate to: `File` → `New` → `Project` → `React`
- ✅ Make sure to **tick the "Create TypeScript Project"** option

### OR via CLI:
```bash
npx create-react-app react-practical --template typescript
```

## ✅ Step 2: Explore dependencies in package.json
Open the package.json file to view all the dependencies with their versions currently using by your React project, such as:
```json
{
  "dependencies": {
    "react": "^19.1.0",
    "react-dom": "^19.1.0",
    "react-scripts": "5.0.1",
    "typescript": "^4.9.5"
  }
}
```

## ✅ Step 3: Explore default scripts in package.json
Open the package.json file and visit to the scripts section to view the default scripts created for your React project, such as:

```json
{
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject"
  }
}
```

## ▶️ Step 4: Run Your React Project
You can start your React app using above-mentioned script defined in the package.json file:
```bash
npm run start
```
or simply
```bash
npm start
```