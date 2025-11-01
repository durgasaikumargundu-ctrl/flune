# NEXAR Design Guidelines

## Design Approach

**Reference-Based Approach**: Drawing inspiration from Linear's clean modernism, Notion's workspace organization, and cutting-edge AI interfaces (ChatGPT, Midjourney, Vercel AI), creating a futuristic AI control center aesthetic with glassmorphism, neon accents, and living, breathing animations.

**Core Philosophy**: Create a "living AI ecosystem" where every element feels animated, intelligent, and responsive. The interface should feel like a sci-fi command center where users witness real AI teamwork in action.

## Typography System

**Font Families**:
- Primary: 'Inter' (UI elements, chat, body text) - clean, highly legible
- Accent: 'Space Grotesk' (headings, manager name, project titles) - futuristic, geometric
- Monospace: 'JetBrains Mono' (code snippets from Coder assistant)

**Hierarchy**:
- Hero/Manager Name: text-5xl md:text-6xl font-bold tracking-tight
- Section Headers: text-3xl md:text-4xl font-bold
- Chat Messages: text-base md:text-lg leading-relaxed
- Assistant Names: text-sm font-semibold uppercase tracking-wider
- Metadata/Timestamps: text-xs opacity-60
- Button Text: text-sm md:text-base font-medium

## Layout & Spacing System

**Spacing Primitives**: Tailwind units of 2, 4, 8, 12, and 16 for consistent rhythm
- Tight spacing: p-2, gap-2 (assistant bubbles, icons)
- Standard spacing: p-4, gap-4 (chat messages, cards)
- Section spacing: p-8, gap-8 (dashboard sections, sidebars)
- Large spacing: p-12, gap-12 (page sections, modal padding)
- Extra spacing: p-16 (full-page containers, hero areas)

**Container Strategy**:
- Main chat container: max-w-4xl mx-auto
- Dashboard grid: max-w-7xl mx-auto
- Sidebar: fixed w-64 md:w-80
- Mobile: Full width with px-4 padding

## Component Library

### Authentication & Onboarding
**Login/Signup Screen**:
- Full-screen centered card with glassmorphism backdrop-blur-xl
- Large animated logo/icon above form (floating animation)
- Input fields with subtle glow on focus
- Social auth buttons (Google) with provider icons
- Smooth fade-in transitions on mount

**Manager Naming Modal**:
- Centered modal overlay with particle effects background
- Large input field with glowing border animation
- Preview of manager avatar below input (animated)
- "Continue" button with pulse animation
- Animated greeting message after submission

### Main Chat Interface
**Layout Structure**:
- Fixed sidebar (left): User profile, manager info, conversation history list
- Main area (center): Chat messages, input field, assistant workspace
- Optional panel (right): Project dashboard or settings (collapsible)

**Chat Messages**:
- User messages: Right-aligned, rounded-2xl, subtle backdrop blur
- Manager replies: Left-aligned with avatar, larger rounded-3xl container
- Assistant badges: Small pill shapes showing which AI contributed
- Timestamp: Subtle, bottom-right of each message
- Typing indicator: Three animated dots with glow pulse effect

**Manager Avatar**:
- Floating Lottie animation or animated SVG (120x120px on desktop, 80x80px mobile)
- Positioned top-left of manager messages
- Glow effect ring around avatar (changes with emotion)
- Smooth scale animation on new message arrival

**Input Area**:
- Fixed bottom position with backdrop-blur
- Multi-line textarea with auto-expand (max 6 rows)
- Voice input button (left) with recording animation
- Send button (right) with loading spinner on submit
- Suggested prompts row above input (dismissible pills)

### Assistant Visualization System
**Work Mode Control Room**:
- Horizontal row of assistant cards below input during processing
- Each card: Icon, name, status text, circular progress ring
- States: "Idle" (dim), "Working..." (pulsing glow), "Done ✅" (green glow)
- Smooth fade-in when activated, fade-out when complete
- Connecting "energy lines" between manager and active assistants (animated SVG paths)

**Assistant Cards**:
- Compact design: 100x120px each
- Icon at top (32x32px)
- Name below in small caps
- Status text and progress indicator
- Glassmorphism background with neon border glow

### Project Dashboard
**Dashboard Grid**:
- Masonry or standard grid layout: grid-cols-1 md:grid-cols-2 lg:grid-cols-3
- Project cards with hover elevation effect
- Each card shows: Title, progress bar, recent AI activity, quick actions

**Project Card**:
- Rounded-xl with glassmorphism
- Header: Project name + emoji icon
- Progress bar with percentage
- Task list preview (3-5 items max)
- AI activity timeline (last 3 actions with assistant icons)
- "View Details" button

**Project Detail View**:
- Modal or full-page layout
- Header: Project name, overall progress, edit button
- Task sections with checkboxes and AI attribution
- Activity log sidebar showing which assistant did what
- Export/share options

### Emotion & Memory System
**Emotion Indicators**:
- Manager avatar animation changes (calm, excited, serious expressions)
- Background particle speed/density adjusts
- Message container border glow intensity varies
- Subtle ambient color shift in glassmorphism overlays

**Memory Recall**:
- Small "brain" icon in chat when Nexar references memory
- Tooltip on hover: "Recalled from conversation on [date]"
- Memory highlights in chat: subtle underline or italic style

### Voice Interaction
**Voice Input Button**:
- Microphone icon with pulsing ring during recording
- Waveform visualization while user speaks
- Transcription preview appears above input field
- Cancel and confirm controls

**Voice Output Indicator**:
- Small speaker icon with sound waves during TTS playback
- Pause/resume controls
- Animated lip-sync style pulses on avatar (optional)

### Settings & Customization
**Manager Customization Panel**:
- Avatar style selector (grid of preview images)
- Voice style dropdown (with audio preview buttons)
- Theme accent color picker (limited palette)
- Personality slider (serious ↔ casual)

## Animation Strategy

**Principle**: Animations should enhance the "living AI" feel without overwhelming usability.

**Key Animations**:
- Page transitions: Smooth fade + slight scale (200ms)
- Chat messages: Slide-in from appropriate side (300ms)
- Typing indicator: Bouncing dots with stagger (1s loop)
- Assistant activation: Fade-in + glow pulse (400ms)
- Manager avatar: Gentle floating motion (3s loop)
- Background particles: Slow drift, respond to emotion state
- Progress rings: Smooth stroke animation (500ms)
- Button hovers: Subtle glow increase (150ms)
- Modal overlays: Backdrop fade + content scale (250ms)

**Animation Timing**: Use ease-in-out for most, ease-out for entrances, ease-in for exits

## Images

**Manager Avatar Image**:
- Lottie JSON animation or animated 3D render
- Futuristic AI character design (holographic, geometric, abstract)
- Placement: Throughout chat interface next to manager messages
- Size: 120x120px desktop, 80x80px mobile
- Style: Glowing, semi-transparent with energy effects

**Assistant Icons**:
- Custom icon set for each assistant (brain, pen, code brackets, magnifying glass, palette)
- Placement: In assistant cards, message badges, project activity logs
- Size: 24x24px in messages, 32x32px in cards
- Style: Line icons with subtle glow effect

**Background Elements**:
- Abstract particle field using react-tsparticles (not static image)
- Animated gradient mesh as backdrop
- No hero image needed - app opens directly to dashboard/chat

**Onboarding Illustrations** (Optional):
- Welcome screen: Abstract AI brain network illustration
- Tutorial steps: Simple line art showing features
- Empty states: Friendly "no conversations yet" illustration

**Project Thumbnails**:
- User-uploaded or auto-generated based on project type
- Placement: Project dashboard cards
- Size: Full card width, aspect ratio 16:9
- Fallback: Gradient with project icon overlay