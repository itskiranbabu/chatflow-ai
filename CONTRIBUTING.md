# Contributing to ChatFlow AI

First off, thank you for considering contributing to ChatFlow AI! It's people like you that make ChatFlow AI such a great tool.

## 🌟 Ways to Contribute

There are many ways to contribute to ChatFlow AI:

- 🐛 **Report bugs** - Help us identify and fix issues
- 💡 **Suggest features** - Share your ideas for improvements
- 📝 **Improve documentation** - Help others understand the project
- 🔧 **Submit code** - Fix bugs or implement new features
- 🎨 **Design improvements** - Enhance UI/UX
- 🌍 **Translations** - Help make ChatFlow AI multilingual
- 📣 **Spread the word** - Share ChatFlow AI with others

## 🚀 Getting Started

### Prerequisites

- Node.js 18+ and npm/yarn
- Docker & Docker Compose
- PostgreSQL 14+
- Redis 7+
- Git

### Setting Up Development Environment

1. **Fork the repository**
   ```bash
   # Click the "Fork" button on GitHub
   ```

2. **Clone your fork**
   ```bash
   git clone https://github.com/YOUR_USERNAME/chatflow-ai.git
   cd chatflow-ai
   ```

3. **Add upstream remote**
   ```bash
   git remote add upstream https://github.com/itskiranbabu/chatflow-ai.git
   ```

4. **Install dependencies**
   ```bash
   npm install
   ```

5. **Set up environment variables**
   ```bash
   cp .env.example .env
   # Edit .env with your configuration
   ```

6. **Start services**
   ```bash
   docker-compose up -d
   ```

7. **Run migrations**
   ```bash
   npm run migrate
   ```

8. **Start development server**
   ```bash
   npm run dev
   ```

9. **Open your browser**
   ```
   http://localhost:3000
   ```

## 📋 Development Workflow

### 1. Create a Branch

Always create a new branch for your work:

```bash
git checkout -b feature/your-feature-name
# or
git checkout -b fix/your-bug-fix
```

Branch naming conventions:
- `feature/` - New features
- `fix/` - Bug fixes
- `docs/` - Documentation changes
- `refactor/` - Code refactoring
- `test/` - Adding tests
- `chore/` - Maintenance tasks

### 2. Make Your Changes

- Write clean, readable code
- Follow the existing code style
- Add comments for complex logic
- Update documentation if needed
- Add tests for new features

### 3. Test Your Changes

```bash
# Run unit tests
npm run test

# Run integration tests
npm run test:integration

# Run e2e tests
npm run test:e2e

# Run linter
npm run lint

# Run type check
npm run type-check
```

### 4. Commit Your Changes

We follow [Conventional Commits](https://www.conventionalcommits.org/):

```bash
git add .
git commit -m "feat: add chatbot node type for API calls"
```

Commit message format:
```
<type>(<scope>): <subject>

<body>

<footer>
```

Types:
- `feat` - New feature
- `fix` - Bug fix
- `docs` - Documentation changes
- `style` - Code style changes (formatting, etc.)
- `refactor` - Code refactoring
- `test` - Adding tests
- `chore` - Maintenance tasks

Examples:
```bash
feat(chatbot): add API call node type
fix(inbox): resolve message ordering issue
docs(readme): update installation instructions
style(ui): improve button spacing
refactor(api): simplify authentication logic
test(campaign): add unit tests for scheduler
chore(deps): update dependencies
```

### 5. Push to Your Fork

```bash
git push origin feature/your-feature-name
```

### 6. Create a Pull Request

1. Go to your fork on GitHub
2. Click "New Pull Request"
3. Select your branch
4. Fill in the PR template
5. Submit the PR

## 📝 Pull Request Guidelines

### PR Title

Use the same format as commit messages:
```
feat(chatbot): add API call node type
```

### PR Description

Include:
- **What**: What changes did you make?
- **Why**: Why did you make these changes?
- **How**: How did you implement the changes?
- **Testing**: How did you test the changes?
- **Screenshots**: If UI changes, include before/after screenshots
- **Related Issues**: Link to related issues

Example:
```markdown
## What
Added a new node type for making API calls in the chatbot builder.

## Why
Users requested the ability to integrate external APIs in their chatbot flows.

## How
- Created new `APICallNode` component
- Added API configuration UI
- Implemented request/response handling
- Added error handling

## Testing
- Added unit tests for API call logic
- Tested with various API endpoints
- Verified error handling

## Screenshots
![API Node](screenshot.png)

## Related Issues
Closes #123
```

### PR Checklist

Before submitting, ensure:

- [ ] Code follows project style guidelines
- [ ] Tests pass locally
- [ ] New tests added for new features
- [ ] Documentation updated
- [ ] No console errors or warnings
- [ ] Commit messages follow conventions
- [ ] PR description is complete

## 🎨 Code Style Guidelines

### TypeScript

```typescript
// ✅ Good
interface User {
  id: string;
  email: string;
  name: string;
}

async function getUser(id: string): Promise<User> {
  const user = await db.user.findUnique({ where: { id } });
  if (!user) {
    throw new Error('User not found');
  }
  return user;
}

// ❌ Bad
async function getUser(id) {
  const user = await db.user.findUnique({ where: { id } });
  return user;
}
```

### React Components

```typescript
// ✅ Good
interface ButtonProps {
  children: React.ReactNode;
  onClick: () => void;
  variant?: 'primary' | 'secondary';
  disabled?: boolean;
}

export function Button({ 
  children, 
  onClick, 
  variant = 'primary',
  disabled = false 
}: ButtonProps) {
  return (
    <button
      onClick={onClick}
      disabled={disabled}
      className={cn(
        'px-4 py-2 rounded',
        variant === 'primary' && 'bg-blue-500 text-white',
        variant === 'secondary' && 'bg-gray-200 text-gray-800'
      )}
    >
      {children}
    </button>
  );
}

// ❌ Bad
export function Button(props) {
  return <button onClick={props.onClick}>{props.children}</button>;
}
```

### Naming Conventions

- **Components**: PascalCase (`UserProfile`, `ChatbotBuilder`)
- **Functions**: camelCase (`getUserById`, `sendMessage`)
- **Constants**: UPPER_SNAKE_CASE (`API_URL`, `MAX_RETRIES`)
- **Files**: kebab-case (`user-profile.tsx`, `chatbot-builder.tsx`)
- **Types/Interfaces**: PascalCase (`User`, `MessageData`)

### File Organization

```
components/
├── ui/                    # Reusable UI components
│   ├── button.tsx
│   └── input.tsx
├── chatbot/              # Feature-specific components
│   ├── ChatbotBuilder.tsx
│   └── NodeEditor.tsx
└── shared/               # Shared utilities
    └── LoadingSpinner.tsx
```

## 🧪 Testing Guidelines

### Unit Tests

```typescript
import { describe, it, expect } from 'vitest';
import { calculateMessageCost } from './billing';

describe('calculateMessageCost', () => {
  it('should calculate cost for marketing messages', () => {
    const cost = calculateMessageCost('marketing', 'US', 100);
    expect(cost).toBe(1.47);
  });

  it('should return 0 for service messages', () => {
    const cost = calculateMessageCost('service', 'US', 100);
    expect(cost).toBe(0);
  });
});
```

### Integration Tests

```typescript
import { describe, it, expect } from 'vitest';
import { createTestContext } from './test-utils';

describe('Chatbot API', () => {
  it('should create a new chatbot', async () => {
    const ctx = await createTestContext();
    const response = await ctx.client.post('/api/chatbots', {
      name: 'Test Bot',
      flowData: { nodes: [], edges: [] }
    });
    expect(response.status).toBe(201);
    expect(response.data.name).toBe('Test Bot');
  });
});
```

### E2E Tests

```typescript
import { test, expect } from '@playwright/test';

test('user can create a chatbot', async ({ page }) => {
  await page.goto('/chatbots');
  await page.click('text=New Chatbot');
  await page.fill('input[name="name"]', 'My Bot');
  await page.click('text=Create');
  await expect(page.locator('text=My Bot')).toBeVisible();
});
```

## 📚 Documentation Guidelines

### Code Comments

```typescript
/**
 * Sends a WhatsApp message to a contact
 * 
 * @param contactId - The ID of the contact to send to
 * @param message - The message content
 * @param options - Optional message options (media, buttons, etc.)
 * @returns The sent message object
 * @throws {Error} If the message fails to send
 */
async function sendMessage(
  contactId: string,
  message: string,
  options?: MessageOptions
): Promise<Message> {
  // Implementation
}
```

### README Updates

When adding new features, update relevant documentation:
- README.md - High-level overview
- INSTALLATION.md - Setup instructions
- API.md - API documentation
- CONFIGURATION.md - Configuration options

## 🐛 Bug Reports

### Before Reporting

1. Check if the bug has already been reported
2. Try to reproduce the bug
3. Gather relevant information

### Bug Report Template

```markdown
**Describe the bug**
A clear description of what the bug is.

**To Reproduce**
Steps to reproduce:
1. Go to '...'
2. Click on '...'
3. See error

**Expected behavior**
What you expected to happen.

**Screenshots**
If applicable, add screenshots.

**Environment**
- OS: [e.g., macOS 13.0]
- Browser: [e.g., Chrome 120]
- Version: [e.g., 1.0.0]

**Additional context**
Any other relevant information.
```

## 💡 Feature Requests

### Feature Request Template

```markdown
**Is your feature request related to a problem?**
A clear description of the problem.

**Describe the solution you'd like**
A clear description of what you want to happen.

**Describe alternatives you've considered**
Other solutions you've thought about.

**Additional context**
Any other relevant information, mockups, etc.
```

## 🏷️ Issue Labels

- `bug` - Something isn't working
- `feature` - New feature request
- `documentation` - Documentation improvements
- `good-first-issue` - Good for newcomers
- `help-wanted` - Extra attention needed
- `question` - Further information requested
- `wontfix` - This will not be worked on
- `duplicate` - This issue already exists
- `invalid` - This doesn't seem right

## 🎯 Priority Labels

- `priority: critical` - Needs immediate attention
- `priority: high` - Important issue
- `priority: medium` - Normal priority
- `priority: low` - Nice to have

## 📞 Communication

### Discord

Join our Discord server for:
- Real-time discussions
- Getting help
- Sharing ideas
- Community events

### GitHub Discussions

Use GitHub Discussions for:
- Feature proposals
- General questions
- Show and tell
- Community feedback

### Email

For sensitive issues:
- security@chatflow.ai (security vulnerabilities)
- support@chatflow.ai (general support)

## 🎓 Resources

- [Next.js Documentation](https://nextjs.org/docs)
- [NestJS Documentation](https://docs.nestjs.com)
- [React Flow Documentation](https://reactflow.dev)
- [Shadcn/ui Documentation](https://ui.shadcn.com)
- [TypeScript Handbook](https://www.typescriptlang.org/docs)

## 📜 Code of Conduct

### Our Pledge

We pledge to make participation in our project a harassment-free experience for everyone, regardless of age, body size, disability, ethnicity, gender identity, level of experience, nationality, personal appearance, race, religion, or sexual identity and orientation.

### Our Standards

**Positive behavior includes:**
- Using welcoming and inclusive language
- Being respectful of differing viewpoints
- Gracefully accepting constructive criticism
- Focusing on what is best for the community
- Showing empathy towards others

**Unacceptable behavior includes:**
- Trolling, insulting/derogatory comments, and personal attacks
- Public or private harassment
- Publishing others' private information
- Other conduct which could reasonably be considered inappropriate

### Enforcement

Instances of abusive, harassing, or otherwise unacceptable behavior may be reported to the project team at conduct@chatflow.ai. All complaints will be reviewed and investigated promptly and fairly.

## 🙏 Recognition

Contributors will be recognized in:
- README.md contributors section
- Release notes
- Annual contributor spotlight
- Special badges on Discord

## ❓ Questions?

Don't hesitate to ask! We're here to help:
- Open a GitHub Discussion
- Join our Discord
- Email support@chatflow.ai

---

**Thank you for contributing to ChatFlow AI! 🎉**

Together, we're building the best open-source WhatsApp automation platform.
