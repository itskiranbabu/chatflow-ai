# 🎯 ChatFlow AI - Master Development Prompt

**Version**: 1.0.0  
**Last Updated**: January 2026  
**Purpose**: Complete specification for AI code generation platforms (Lovable, Bolt, Cursor, v0)

---

## 📋 Project Overview

**Project Name**: ChatFlow AI  
**Type**: WhatsApp & Marketing Automation SaaS Platform  
**Target**: Open-source alternative to Wati, Interakt, AiSensy  
**Tech Stack**: Next.js 14, NestJS, PostgreSQL, MongoDB, Redis, Evolution API

---

## 🎨 Design System & Branding

### Color Palette
```css
/* Primary Colors */
--primary-green: #25D366;      /* WhatsApp Green */
--primary-blue: #00D9FF;       /* Brand Blue */
--primary-dark: #075E54;       /* Dark Green */

/* Secondary Colors */
--secondary-purple: #7C3AED;   /* AI Features */
--secondary-orange: #F97316;   /* Alerts */
--secondary-yellow: #FBBF24;   /* Warnings */

/* Neutral Colors */
--gray-50: #F9FAFB;
--gray-100: #F3F4F6;
--gray-200: #E5E7EB;
--gray-300: #D1D5DB;
--gray-400: #9CA3AF;
--gray-500: #6B7280;
--gray-600: #4B5563;
--gray-700: #374151;
--gray-800: #1F2937;
--gray-900: #111827;

/* Semantic Colors */
--success: #10B981;
--error: #EF4444;
--warning: #F59E0B;
--info: #3B82F6;
```

### Typography
```css
/* Font Family */
--font-sans: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
--font-mono: 'JetBrains Mono', 'Fira Code', monospace;

/* Font Sizes */
--text-xs: 0.75rem;    /* 12px */
--text-sm: 0.875rem;   /* 14px */
--text-base: 1rem;     /* 16px */
--text-lg: 1.125rem;   /* 18px */
--text-xl: 1.25rem;    /* 20px */
--text-2xl: 1.5rem;    /* 24px */
--text-3xl: 1.875rem;  /* 30px */
--text-4xl: 2.25rem;   /* 36px */
```

### Spacing System
```css
/* Use 4px base unit */
--space-1: 0.25rem;   /* 4px */
--space-2: 0.5rem;    /* 8px */
--space-3: 0.75rem;   /* 12px */
--space-4: 1rem;      /* 16px */
--space-6: 1.5rem;    /* 24px */
--space-8: 2rem;      /* 32px */
--space-12: 3rem;     /* 48px */
--space-16: 4rem;     /* 64px */
```

---

## 🏗️ Application Architecture

### Frontend Structure (Next.js 14 App Router)
```
app/
├── (auth)/
│   ├── login/
│   │   └── page.tsx
│   ├── register/
│   │   └── page.tsx
│   └── layout.tsx
├── (dashboard)/
│   ├── dashboard/
│   │   └── page.tsx          # Main dashboard
│   ├── contacts/
│   │   ├── page.tsx          # Contact list
│   │   └── [id]/
│   │       └── page.tsx      # Contact details
│   ├── conversations/
│   │   ├── page.tsx          # Inbox
│   │   └── [id]/
│   │       └── page.tsx      # Conversation view
│   ├── chatbots/
│   │   ├── page.tsx          # Chatbot list
│   │   ├── new/
│   │   │   └── page.tsx      # Create chatbot
│   │   └── [id]/
│   │       ├── page.tsx      # Chatbot builder
│   │       └── analytics/
│   │           └── page.tsx  # Chatbot analytics
│   ├── campaigns/
│   │   ├── page.tsx          # Campaign list
│   │   ├── new/
│   │   │   └── page.tsx      # Create campaign
│   │   └── [id]/
│   │       ├── page.tsx      # Campaign details
│   │       └── analytics/
│   │           └── page.tsx  # Campaign analytics
│   ├── broadcasts/
│   │   ├── page.tsx          # Broadcast list
│   │   └── new/
│   │       └── page.tsx      # Create broadcast
│   ├── templates/
│   │   ├── page.tsx          # Template library
│   │   └── [id]/
│   │       └── page.tsx      # Template editor
│   ├── analytics/
│   │   └── page.tsx          # Analytics dashboard
│   ├── integrations/
│   │   └── page.tsx          # Integrations
│   ├── settings/
│   │   ├── page.tsx          # General settings
│   │   ├── team/
│   │   │   └── page.tsx      # Team management
│   │   ├── billing/
│   │   │   └── page.tsx      # Billing
│   │   └── api/
│   │       └── page.tsx      # API keys
│   └── layout.tsx
├── api/
│   ├── auth/
│   │   └── [...nextauth]/
│   │       └── route.ts
│   ├── webhooks/
│   │   └── whatsapp/
│   │       └── route.ts
│   └── trpc/
│       └── [trpc]/
│           └── route.ts
└── layout.tsx
```

### Component Structure
```
components/
├── ui/                        # Shadcn/ui components
│   ├── button.tsx
│   ├── input.tsx
│   ├── card.tsx
│   ├── dialog.tsx
│   ├── dropdown-menu.tsx
│   ├── table.tsx
│   ├── tabs.tsx
│   └── ...
├── layout/
│   ├── Sidebar.tsx
│   ├── Header.tsx
│   ├── Footer.tsx
│   └── DashboardLayout.tsx
├── chatbot/
│   ├── ChatbotBuilder.tsx    # Main builder component
│   ├── FlowCanvas.tsx         # React Flow canvas
│   ├── NodePalette.tsx        # Drag-and-drop nodes
│   ├── NodeEditor.tsx         # Edit node properties
│   └── nodes/
│       ├── MessageNode.tsx
│       ├── QuestionNode.tsx
│       ├── ConditionNode.tsx
│       ├── AINode.tsx
│       └── ActionNode.tsx
├── inbox/
│   ├── ConversationList.tsx
│   ├── ConversationView.tsx
│   ├── MessageBubble.tsx
│   ├── MessageInput.tsx
│   └── ContactInfo.tsx
├── campaign/
│   ├── CampaignBuilder.tsx
│   ├── AudienceSelector.tsx
│   ├── MessageComposer.tsx
│   ├── ScheduleSelector.tsx
│   └── CampaignPreview.tsx
├── analytics/
│   ├── MetricCard.tsx
│   ├── LineChart.tsx
│   ├── BarChart.tsx
│   ├── PieChart.tsx
│   └── DataTable.tsx
└── shared/
    ├── LoadingSpinner.tsx
    ├── EmptyState.tsx
    ├── ErrorBoundary.tsx
    └── ConfirmDialog.tsx
```

---

## 🗄️ Database Schema

### PostgreSQL Schema (Relational Data)

```sql
-- Users Table
CREATE TABLE users (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  email VARCHAR(255) UNIQUE NOT NULL,
  password_hash VARCHAR(255) NOT NULL,
  full_name VARCHAR(255),
  avatar_url TEXT,
  role VARCHAR(50) DEFAULT 'user',
  status VARCHAR(50) DEFAULT 'active',
  created_at TIMESTAMP DEFAULT NOW(),
  updated_at TIMESTAMP DEFAULT NOW()
);

-- Organizations Table (Multi-tenancy)
CREATE TABLE organizations (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  name VARCHAR(255) NOT NULL,
  slug VARCHAR(255) UNIQUE NOT NULL,
  logo_url TEXT,
  plan VARCHAR(50) DEFAULT 'free',
  settings JSONB DEFAULT '{}',
  created_at TIMESTAMP DEFAULT NOW(),
  updated_at TIMESTAMP DEFAULT NOW()
);

-- Organization Members
CREATE TABLE organization_members (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id UUID REFERENCES organizations(id) ON DELETE CASCADE,
  user_id UUID REFERENCES users(id) ON DELETE CASCADE,
  role VARCHAR(50) DEFAULT 'member',
  created_at TIMESTAMP DEFAULT NOW(),
  UNIQUE(organization_id, user_id)
);

-- WhatsApp Connections
CREATE TABLE whatsapp_connections (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id UUID REFERENCES organizations(id) ON DELETE CASCADE,
  instance_name VARCHAR(255) NOT NULL,
  phone_number VARCHAR(50),
  status VARCHAR(50) DEFAULT 'disconnected',
  qr_code TEXT,
  webhook_url TEXT,
  settings JSONB DEFAULT '{}',
  created_at TIMESTAMP DEFAULT NOW(),
  updated_at TIMESTAMP DEFAULT NOW()
);

-- Contacts
CREATE TABLE contacts (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id UUID REFERENCES organizations(id) ON DELETE CASCADE,
  whatsapp_id VARCHAR(255) NOT NULL,
  phone_number VARCHAR(50) NOT NULL,
  name VARCHAR(255),
  email VARCHAR(255),
  avatar_url TEXT,
  tags TEXT[],
  custom_fields JSONB DEFAULT '{}',
  created_at TIMESTAMP DEFAULT NOW(),
  updated_at TIMESTAMP DEFAULT NOW(),
  UNIQUE(organization_id, whatsapp_id)
);

-- Conversations
CREATE TABLE conversations (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id UUID REFERENCES organizations(id) ON DELETE CASCADE,
  contact_id UUID REFERENCES contacts(id) ON DELETE CASCADE,
  whatsapp_connection_id UUID REFERENCES whatsapp_connections(id),
  status VARCHAR(50) DEFAULT 'open',
  assigned_to UUID REFERENCES users(id),
  last_message_at TIMESTAMP,
  created_at TIMESTAMP DEFAULT NOW(),
  updated_at TIMESTAMP DEFAULT NOW()
);

-- Messages
CREATE TABLE messages (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  conversation_id UUID REFERENCES conversations(id) ON DELETE CASCADE,
  whatsapp_message_id VARCHAR(255),
  direction VARCHAR(50) NOT NULL, -- 'inbound' or 'outbound'
  type VARCHAR(50) NOT NULL, -- 'text', 'image', 'video', 'document', etc.
  content TEXT,
  media_url TEXT,
  status VARCHAR(50) DEFAULT 'sent',
  sent_by UUID REFERENCES users(id),
  created_at TIMESTAMP DEFAULT NOW()
);

-- Chatbots
CREATE TABLE chatbots (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id UUID REFERENCES organizations(id) ON DELETE CASCADE,
  name VARCHAR(255) NOT NULL,
  description TEXT,
  status VARCHAR(50) DEFAULT 'draft',
  flow_data JSONB NOT NULL, -- React Flow data
  settings JSONB DEFAULT '{}',
  created_by UUID REFERENCES users(id),
  created_at TIMESTAMP DEFAULT NOW(),
  updated_at TIMESTAMP DEFAULT NOW()
);

-- Campaigns
CREATE TABLE campaigns (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id UUID REFERENCES organizations(id) ON DELETE CASCADE,
  name VARCHAR(255) NOT NULL,
  type VARCHAR(50) NOT NULL, -- 'broadcast', 'drip', 'trigger'
  status VARCHAR(50) DEFAULT 'draft',
  message_template JSONB NOT NULL,
  audience_filter JSONB,
  schedule JSONB,
  settings JSONB DEFAULT '{}',
  created_by UUID REFERENCES users(id),
  created_at TIMESTAMP DEFAULT NOW(),
  updated_at TIMESTAMP DEFAULT NOW()
);

-- Campaign Messages (Tracking)
CREATE TABLE campaign_messages (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  campaign_id UUID REFERENCES campaigns(id) ON DELETE CASCADE,
  contact_id UUID REFERENCES contacts(id) ON DELETE CASCADE,
  message_id UUID REFERENCES messages(id),
  status VARCHAR(50) DEFAULT 'pending',
  sent_at TIMESTAMP,
  delivered_at TIMESTAMP,
  read_at TIMESTAMP,
  clicked_at TIMESTAMP,
  created_at TIMESTAMP DEFAULT NOW()
);

-- Templates
CREATE TABLE templates (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id UUID REFERENCES organizations(id) ON DELETE CASCADE,
  name VARCHAR(255) NOT NULL,
  category VARCHAR(100),
  language VARCHAR(10) DEFAULT 'en',
  content TEXT NOT NULL,
  variables JSONB DEFAULT '[]',
  media_url TEXT,
  status VARCHAR(50) DEFAULT 'pending',
  created_at TIMESTAMP DEFAULT NOW(),
  updated_at TIMESTAMP DEFAULT NOW()
);

-- API Keys
CREATE TABLE api_keys (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id UUID REFERENCES organizations(id) ON DELETE CASCADE,
  name VARCHAR(255) NOT NULL,
  key_hash VARCHAR(255) NOT NULL,
  permissions JSONB DEFAULT '[]',
  last_used_at TIMESTAMP,
  expires_at TIMESTAMP,
  created_by UUID REFERENCES users(id),
  created_at TIMESTAMP DEFAULT NOW()
);

-- Webhooks
CREATE TABLE webhooks (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  organization_id UUID REFERENCES organizations(id) ON DELETE CASCADE,
  url TEXT NOT NULL,
  events TEXT[] NOT NULL,
  secret VARCHAR(255),
  status VARCHAR(50) DEFAULT 'active',
  created_at TIMESTAMP DEFAULT NOW(),
  updated_at TIMESTAMP DEFAULT NOW()
);

-- Create indexes
CREATE INDEX idx_contacts_org ON contacts(organization_id);
CREATE INDEX idx_contacts_phone ON contacts(phone_number);
CREATE INDEX idx_conversations_org ON conversations(organization_id);
CREATE INDEX idx_conversations_contact ON conversations(contact_id);
CREATE INDEX idx_messages_conversation ON messages(conversation_id);
CREATE INDEX idx_messages_created ON messages(created_at DESC);
CREATE INDEX idx_campaigns_org ON campaigns(organization_id);
CREATE INDEX idx_campaign_messages_campaign ON campaign_messages(campaign_id);
```

### MongoDB Schema (Analytics & Logs)

```javascript
// Analytics Events Collection
{
  _id: ObjectId,
  organizationId: UUID,
  eventType: String, // 'message_sent', 'message_delivered', 'message_read', 'button_clicked', etc.
  eventData: {
    contactId: UUID,
    conversationId: UUID,
    messageId: UUID,
    campaignId: UUID,
    chatbotId: UUID,
    // ... other event-specific data
  },
  metadata: {
    userAgent: String,
    ipAddress: String,
    deviceType: String
  },
  timestamp: ISODate
}

// Chatbot Sessions Collection
{
  _id: ObjectId,
  organizationId: UUID,
  chatbotId: UUID,
  contactId: UUID,
  conversationId: UUID,
  startedAt: ISODate,
  endedAt: ISODate,
  steps: [
    {
      nodeId: String,
      nodeType: String,
      input: String,
      output: String,
      timestamp: ISODate
    }
  ],
  outcome: String, // 'completed', 'abandoned', 'escalated'
}

// Message Logs Collection
{
  _id: ObjectId,
  organizationId: UUID,
  messageId: UUID,
  direction: String,
  status: String,
  statusHistory: [
    {
      status: String,
      timestamp: ISODate,
      error: String
    }
  ],
  metadata: Object,
  timestamp: ISODate
}
```

---

## 🔌 API Endpoints

### Authentication
```typescript
POST   /api/auth/register          // Register new user
POST   /api/auth/login             // Login
POST   /api/auth/logout            // Logout
POST   /api/auth/refresh           // Refresh token
POST   /api/auth/forgot-password   // Request password reset
POST   /api/auth/reset-password    // Reset password
```

### Organizations
```typescript
GET    /api/organizations          // List user's organizations
POST   /api/organizations          // Create organization
GET    /api/organizations/:id      // Get organization details
PATCH  /api/organizations/:id      // Update organization
DELETE /api/organizations/:id      // Delete organization
GET    /api/organizations/:id/members  // List members
POST   /api/organizations/:id/members  // Add member
DELETE /api/organizations/:id/members/:userId  // Remove member
```

### WhatsApp Connections
```typescript
GET    /api/whatsapp/connections   // List connections
POST   /api/whatsapp/connections   // Create connection
GET    /api/whatsapp/connections/:id  // Get connection
PATCH  /api/whatsapp/connections/:id  // Update connection
DELETE /api/whatsapp/connections/:id  // Delete connection
POST   /api/whatsapp/connections/:id/connect  // Initiate connection
POST   /api/whatsapp/connections/:id/disconnect  // Disconnect
GET    /api/whatsapp/connections/:id/qr  // Get QR code
```

### Contacts
```typescript
GET    /api/contacts               // List contacts (with pagination, filters)
POST   /api/contacts               // Create contact
GET    /api/contacts/:id           // Get contact
PATCH  /api/contacts/:id           // Update contact
DELETE /api/contacts/:id           // Delete contact
POST   /api/contacts/import        // Bulk import contacts
POST   /api/contacts/:id/tags      // Add tags
DELETE /api/contacts/:id/tags      // Remove tags
```

### Conversations
```typescript
GET    /api/conversations          // List conversations
GET    /api/conversations/:id      // Get conversation with messages
PATCH  /api/conversations/:id      // Update conversation (assign, status)
POST   /api/conversations/:id/messages  // Send message
GET    /api/conversations/:id/messages  // Get messages (paginated)
POST   /api/conversations/:id/assign    // Assign to team member
POST   /api/conversations/:id/close     // Close conversation
```

### Chatbots
```typescript
GET    /api/chatbots               // List chatbots
POST   /api/chatbots               // Create chatbot
GET    /api/chatbots/:id           // Get chatbot
PATCH  /api/chatbots/:id           // Update chatbot
DELETE /api/chatbots/:id           // Delete chatbot
POST   /api/chatbots/:id/publish   // Publish chatbot
POST   /api/chatbots/:id/test      // Test chatbot
GET    /api/chatbots/:id/analytics // Get chatbot analytics
```

### Campaigns
```typescript
GET    /api/campaigns              // List campaigns
POST   /api/campaigns              // Create campaign
GET    /api/campaigns/:id          // Get campaign
PATCH  /api/campaigns/:id          // Update campaign
DELETE /api/campaigns/:id          // Delete campaign
POST   /api/campaigns/:id/send     // Send campaign
POST   /api/campaigns/:id/schedule // Schedule campaign
GET    /api/campaigns/:id/analytics // Get campaign analytics
```

### Templates
```typescript
GET    /api/templates              // List templates
POST   /api/templates              // Create template
GET    /api/templates/:id          // Get template
PATCH  /api/templates/:id          // Update template
DELETE /api/templates/:id          // Delete template
POST   /api/templates/:id/submit   // Submit for WhatsApp approval
```

### Analytics
```typescript
GET    /api/analytics/overview     // Dashboard overview
GET    /api/analytics/messages     // Message analytics
GET    /api/analytics/conversations // Conversation analytics
GET    /api/analytics/campaigns    // Campaign analytics
GET    /api/analytics/chatbots     // Chatbot analytics
POST   /api/analytics/export       // Export analytics data
```

### Webhooks
```typescript
POST   /api/webhooks/whatsapp      // WhatsApp webhook endpoint
GET    /api/webhooks               // List webhooks
POST   /api/webhooks               // Create webhook
DELETE /api/webhooks/:id           // Delete webhook
POST   /api/webhooks/:id/test      // Test webhook
```

---

## 🎨 Key UI Components Specifications

### 1. Dashboard Overview
```typescript
// Dashboard metrics cards
interface MetricCard {
  title: string;
  value: number | string;
  change: number; // percentage change
  trend: 'up' | 'down' | 'neutral';
  icon: React.ReactNode;
}

// Example metrics:
- Total Conversations (last 30 days)
- Messages Sent (last 30 days)
- Active Chatbots
- Campaign Performance
- Response Rate
- Average Response Time
```

### 2. Chatbot Builder
```typescript
// Node types for React Flow
interface BaseNode {
  id: string;
  type: 'message' | 'question' | 'condition' | 'ai' | 'action';
  position: { x: number; y: number };
  data: NodeData;
}

interface MessageNode extends BaseNode {
  type: 'message';
  data: {
    message: string;
    media?: { type: string; url: string };
    buttons?: Array<{ id: string; text: string }>;
  };
}

interface QuestionNode extends BaseNode {
  type: 'question';
  data: {
    question: string;
    variableName: string;
    validationType?: 'email' | 'phone' | 'number' | 'text';
  };
}

interface ConditionNode extends BaseNode {
  type: 'condition';
  data: {
    variable: string;
    operator: 'equals' | 'contains' | 'greater' | 'less';
    value: string;
    trueOutput: string;
    falseOutput: string;
  };
}

interface AINode extends BaseNode {
  type: 'ai';
  data: {
    prompt: string;
    model: 'gpt-4' | 'gpt-3.5-turbo' | 'gemini-pro';
    temperature: number;
    maxTokens: number;
  };
}

interface ActionNode extends BaseNode {
  type: 'action';
  data: {
    actionType: 'webhook' | 'email' | 'tag' | 'assign';
    config: Record<string, any>;
  };
}
```

### 3. Conversation Inbox
```typescript
// Conversation list item
interface ConversationListItem {
  id: string;
  contact: {
    name: string;
    phone: string;
    avatar?: string;
  };
  lastMessage: {
    content: string;
    timestamp: Date;
    isRead: boolean;
  };
  unreadCount: number;
  status: 'open' | 'pending' | 'closed';
  assignedTo?: {
    name: string;
    avatar?: string;
  };
  tags: string[];
}

// Message bubble
interface Message {
  id: string;
  direction: 'inbound' | 'outbound';
  type: 'text' | 'image' | 'video' | 'document' | 'audio';
  content: string;
  mediaUrl?: string;
  status: 'sent' | 'delivered' | 'read' | 'failed';
  timestamp: Date;
  sentBy?: {
    name: string;
    avatar?: string;
  };
}
```

### 4. Campaign Builder
```typescript
interface Campaign {
  id: string;
  name: string;
  type: 'broadcast' | 'drip' | 'trigger';
  status: 'draft' | 'scheduled' | 'running' | 'completed' | 'paused';
  message: {
    template?: string;
    content: string;
    media?: { type: string; url: string };
    buttons?: Array<{ id: string; text: string; url?: string }>;
  };
  audience: {
    type: 'all' | 'segment' | 'custom';
    filters?: Array<{
      field: string;
      operator: string;
      value: any;
    }>;
    contactIds?: string[];
    estimatedReach: number;
  };
  schedule?: {
    type: 'immediate' | 'scheduled' | 'recurring';
    sendAt?: Date;
    timezone?: string;
    recurrence?: {
      frequency: 'daily' | 'weekly' | 'monthly';
      interval: number;
      endDate?: Date;
    };
  };
  analytics: {
    sent: number;
    delivered: number;
    read: number;
    clicked: number;
    failed: number;
  };
}
```

---

## 🔐 Authentication & Authorization

### JWT Token Structure
```typescript
interface JWTPayload {
  userId: string;
  email: string;
  organizationId: string;
  role: 'owner' | 'admin' | 'member';
  permissions: string[];
  iat: number;
  exp: number;
}
```

### Role-Based Access Control (RBAC)
```typescript
const permissions = {
  owner: ['*'], // All permissions
  admin: [
    'contacts:read',
    'contacts:write',
    'contacts:delete',
    'conversations:read',
    'conversations:write',
    'chatbots:read',
    'chatbots:write',
    'chatbots:delete',
    'campaigns:read',
    'campaigns:write',
    'campaigns:delete',
    'templates:read',
    'templates:write',
    'analytics:read',
    'settings:read',
    'settings:write',
    'team:read',
    'team:write',
  ],
  member: [
    'contacts:read',
    'conversations:read',
    'conversations:write',
    'chatbots:read',
    'campaigns:read',
    'templates:read',
    'analytics:read',
  ],
};
```

---

## 🚀 Key Features Implementation

### 1. Real-Time Messaging (WebSocket)
```typescript
// Socket.io events
const socketEvents = {
  // Client -> Server
  'conversation:join': (conversationId: string) => void,
  'conversation:leave': (conversationId: string) => void,
  'message:send': (message: Message) => void,
  'typing:start': (conversationId: string) => void,
  'typing:stop': (conversationId: string) => void,
  
  // Server -> Client
  'message:new': (message: Message) => void,
  'message:status': (messageId: string, status: string) => void,
  'conversation:updated': (conversation: Conversation) => void,
  'typing:indicator': (conversationId: string, isTyping: boolean) => void,
};
```

### 2. Chatbot Flow Execution
```typescript
// Chatbot execution engine
class ChatbotEngine {
  async executeFlow(
    chatbotId: string,
    contactId: string,
    userInput: string,
    context: Record<string, any>
  ): Promise<{
    response: string;
    nextNodeId?: string;
    variables: Record<string, any>;
    shouldEscalate: boolean;
  }> {
    // 1. Load chatbot flow
    // 2. Find current node
    // 3. Process user input
    // 4. Execute node logic
    // 5. Determine next node
    // 6. Return response
  }
}
```

### 3. Campaign Scheduler
```typescript
// Campaign scheduling with BullMQ
interface CampaignJob {
  campaignId: string;
  organizationId: string;
  contactIds: string[];
  messageTemplate: any;
  scheduledFor: Date;
}

// Queue processor
async function processCampaignJob(job: Job<CampaignJob>) {
  const { campaignId, contactIds, messageTemplate } = job.data;
  
  for (const contactId of contactIds) {
    // Send message to contact
    await sendWhatsAppMessage(contactId, messageTemplate);
    
    // Track in database
    await trackCampaignMessage(campaignId, contactId);
    
    // Rate limiting
    await delay(100); // 10 messages per second
  }
}
```

### 4. AI Integration
```typescript
// AI service wrapper
class AIService {
  async generateResponse(
    prompt: string,
    context: string[],
    model: 'gpt-4' | 'gemini-pro'
  ): Promise<string> {
    if (model === 'gpt-4') {
      return await this.openAI.chat.completions.create({
        model: 'gpt-4',
        messages: [
          { role: 'system', content: 'You are a helpful customer service assistant.' },
          ...context.map(c => ({ role: 'user', content: c })),
          { role: 'user', content: prompt }
        ],
        temperature: 0.7,
        max_tokens: 500,
      });
    } else {
      // Gemini implementation
    }
  }
  
  async analyzeSentiment(text: string): Promise<'positive' | 'negative' | 'neutral'> {
    // Sentiment analysis implementation
  }
  
  async extractIntent(text: string): Promise<string> {
    // Intent extraction implementation
  }
}
```

---

## 📱 Responsive Design Requirements

### Breakpoints
```css
/* Mobile First Approach */
--breakpoint-sm: 640px;   /* Small devices */
--breakpoint-md: 768px;   /* Tablets */
--breakpoint-lg: 1024px;  /* Laptops */
--breakpoint-xl: 1280px;  /* Desktops */
--breakpoint-2xl: 1536px; /* Large screens */
```

### Mobile Optimizations
- Collapsible sidebar on mobile
- Bottom navigation for key actions
- Swipe gestures for conversation management
- Touch-optimized buttons (min 44x44px)
- Optimized images and lazy loading

---

## 🧪 Testing Requirements

### Unit Tests
```typescript
// Example test structure
describe('ChatbotEngine', () => {
  it('should execute message node correctly', async () => {
    const engine = new ChatbotEngine();
    const result = await engine.executeNode({
      type: 'message',
      data: { message: 'Hello!' }
    });
    expect(result.response).toBe('Hello!');
  });
});
```

### Integration Tests
- API endpoint testing
- Database operations
- WebSocket connections
- External API integrations

### E2E Tests
- User registration and login
- Creating and publishing chatbot
- Sending campaign
- Conversation flow

---

## 🔒 Security Requirements

### Data Protection
- All passwords hashed with bcrypt (12 rounds)
- API keys encrypted at rest
- HTTPS only in production
- CORS properly configured
- Rate limiting on all endpoints
- Input validation and sanitization
- SQL injection prevention (parameterized queries)
- XSS prevention (content sanitization)

### Compliance
- GDPR compliant (data export, deletion)
- WhatsApp Business Policy compliant
- Data retention policies
- Audit logging for sensitive operations

---

## 🎯 Performance Requirements

### Response Times
- API endpoints: < 200ms (p95)
- Page load: < 2s (p95)
- Real-time message delivery: < 500ms
- Chatbot response: < 1s

### Scalability
- Support 10,000+ concurrent users
- Handle 1M+ messages per day
- Database query optimization
- Caching strategy (Redis)
- CDN for static assets

---

## 📦 Deployment Configuration

### Environment Variables
```bash
# Application
NODE_ENV=production
APP_URL=https://chatflow.ai
API_URL=https://api.chatflow.ai

# Database
DATABASE_URL=postgresql://user:pass@localhost:5432/chatflow
MONGODB_URL=mongodb://localhost:27017/chatflow
REDIS_URL=redis://localhost:6379

# Authentication
JWT_SECRET=your-secret-key
JWT_EXPIRES_IN=7d

# WhatsApp (Evolution API)
EVOLUTION_API_URL=https://evolution.chatflow.ai
EVOLUTION_API_KEY=your-api-key

# AI Services
OPENAI_API_KEY=your-openai-key
GOOGLE_AI_API_KEY=your-google-key

# Email
SENDGRID_API_KEY=your-sendgrid-key
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=your-email
SMTP_PASS=your-password

# Storage
AWS_ACCESS_KEY_ID=your-aws-key
AWS_SECRET_ACCESS_KEY=your-aws-secret
AWS_S3_BUCKET=chatflow-media
AWS_REGION=us-east-1

# Payments
STRIPE_SECRET_KEY=your-stripe-key
STRIPE_WEBHOOK_SECRET=your-webhook-secret

# Monitoring
SENTRY_DSN=your-sentry-dsn
```

### Docker Compose
```yaml
version: '3.8'

services:
  app:
    build: .
    ports:
      - "3000:3000"
    environment:
      - NODE_ENV=production
    depends_on:
      - postgres
      - mongodb
      - redis

  postgres:
    image: postgres:14
    environment:
      POSTGRES_DB: chatflow
      POSTGRES_USER: chatflow
      POSTGRES_PASSWORD: password
    volumes:
      - postgres_data:/var/lib/postgresql/data

  mongodb:
    image: mongo:6
    volumes:
      - mongo_data:/data/db

  redis:
    image: redis:7
    volumes:
      - redis_data:/data

  evolution-api:
    image: atendai/evolution-api:latest
    ports:
      - "8080:8080"
    environment:
      - DATABASE_URL=postgresql://user:pass@postgres:5432/evolution

volumes:
  postgres_data:
  mongo_data:
  redis_data:
```

---

## 🎨 UI/UX Guidelines

### Design Principles
1. **Simplicity**: Clean, uncluttered interfaces
2. **Consistency**: Uniform design patterns throughout
3. **Feedback**: Clear visual feedback for all actions
4. **Accessibility**: WCAG 2.1 AA compliant
5. **Performance**: Fast, responsive interactions

### Component Patterns
- Use Shadcn/ui components as base
- Consistent spacing (4px grid)
- Clear visual hierarchy
- Intuitive navigation
- Helpful empty states
- Informative error messages
- Loading states for async operations

### Accessibility
- Semantic HTML
- ARIA labels where needed
- Keyboard navigation support
- Screen reader friendly
- Sufficient color contrast (4.5:1 minimum)
- Focus indicators
- Alt text for images

---

## 🚨 Error Handling

### Error Response Format
```typescript
interface ErrorResponse {
  success: false;
  error: {
    code: string;
    message: string;
    details?: any;
    timestamp: string;
  };
}

// Example error codes
const errorCodes = {
  AUTH_INVALID_CREDENTIALS: 'Invalid email or password',
  AUTH_TOKEN_EXPIRED: 'Your session has expired',
  WHATSAPP_CONNECTION_FAILED: 'Failed to connect WhatsApp',
  CAMPAIGN_SEND_FAILED: 'Failed to send campaign',
  RATE_LIMIT_EXCEEDED: 'Too many requests',
  VALIDATION_ERROR: 'Invalid input data',
  INTERNAL_SERVER_ERROR: 'Something went wrong',
};
```

### User-Facing Error Messages
- Clear, non-technical language
- Actionable suggestions
- Support contact information
- Error tracking ID for support

---

## 📊 Analytics & Tracking

### Key Metrics to Track
```typescript
interface AnalyticsEvent {
  eventName: string;
  userId?: string;
  organizationId: string;
  properties: Record<string, any>;
  timestamp: Date;
}

// Example events
const events = {
  'user_registered': {},
  'whatsapp_connected': {},
  'chatbot_created': {},
  'chatbot_published': {},
  'campaign_sent': { campaignId, recipientCount },
  'message_sent': { direction, type },
  'conversation_assigned': {},
  'template_created': {},
};
```

---

## 🎯 Success Criteria

### MVP Success Metrics
- [ ] User can register and login
- [ ] User can connect WhatsApp account
- [ ] User can send/receive messages
- [ ] User can create simple chatbot
- [ ] User can send broadcast campaign
- [ ] User can view basic analytics
- [ ] 95% uptime
- [ ] < 2s page load time

---

## 📝 Additional Notes

### Code Quality Standards
- TypeScript strict mode enabled
- ESLint + Prettier configured
- Meaningful variable names
- Comprehensive comments for complex logic
- Error handling in all async operations
- Logging for debugging

### Git Workflow
- Feature branches from `main`
- Descriptive commit messages
- Pull request reviews required
- CI/CD runs on all PRs

---

## 🎬 Getting Started Instructions

When using this prompt with AI code generation platforms:

### For Lovable.dev:
1. Start with: "Create a Next.js 14 app with the following structure..."
2. Build incrementally: Auth → Dashboard → WhatsApp → Chatbot → Campaigns
3. Use the component specifications above
4. Reference the database schema for data models

### For Bolt.new:
1. Begin with: "Build a full-stack WhatsApp automation platform..."
2. Focus on one feature at a time
3. Use the API endpoint specifications
4. Implement real-time features with Socket.io

### For Cursor:
1. Clone the repository
2. Use this prompt as context for each feature
3. Reference specific sections as needed
4. Build with test-driven development

---

**This is a living document. Update as the project evolves.**

**Version**: 1.0.0  
**Last Updated**: January 2026  
**Maintained by**: ChatFlow AI Team
