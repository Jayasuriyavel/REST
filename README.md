# Bold Agent - Automated Testing Framework

A Playwright‑based automated testing suite for the **BoldAgent AI application**, used to validate core UI workflows, authentication, and critical user journeys.

## 📋 Prerequisites

- **Node.js**: v22.12.0 or higher
- **Git**: For version control
- **IDE**: VS Code (recommended) or any preferred IDE

## 🚀 Quick Start

### 1. Clone the Repository

```bash
git clone <repository-url>
cd BOLDAGENT-PLAYWRIGHT-TESTS
```

### 2. Install Dependencies

```bash
npm install
npx playwright install --with-deps
npm install -D monocart-reporter
```
### 3. Install Playwright Extension (Optional)

To enhance your development experience, you can install the Playwright extension in VS Code.

#### Steps:

1. Open **Visual Studio Code**
2. Go to the **Extensions** panel  
   - Shortcut: `Ctrl + Shift + X`
3. Search for: `Playwright Test for VS Code`
4. Click **Install**

#### Benefits:
- Run tests directly from the editor
- Debug tests easily
- View test results inside VS Code


### 4. 📁 Project Structure

```
BOLDAGENT-PLAYWRIGHT-TESTS
├── .github/                 # CI workflows (optional)
├── Images/                  # Visual snapshot baselines
├── test-results/            # Reports, traces, screenshots
├── tests/
│   ├── Login/               # Login & authentication tests
│   │   ├── login.spec.ts
│   │   ├── selectors.ts
│   │   ├── Helper.ts
│   ├── data/                # Centralized test data
│   │   ├── users.ts         # ✅ User credentials ONLY
│   │   ├── urls.ts
│   │   ├── messages.ts
│   └── LoginPage.ts         # ✅ Base URL configured here
├── playwright.config.ts
├── package.json
└── README.md
```

### 5. Setup Environment

Update the base URL in `LoginPage.ts` if required:

```ts
private readonly BASE_URL =
  process.env.BASE_URL || 'https://staging.boldagent.ai';

```
Update test users in:

```
`tests/data/users.ts`
export const USERS = {
  builder: {
    email: 'builder@example.com',
    password: 'Password@123'
  }
};
```
### 6. Run Tests

```bash
# Run all tests
npx playwright test

# Run tests in headed mode (see browser)
npx playwright test --headed

```

## 📊 Test Reports

After running tests, view the HTML report:

```bash
npx playwright show-report
