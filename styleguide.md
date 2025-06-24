# 📱 iOS App Style Guide

*Version 1.0*

> A single source-of-truth for building **clean, professional, user-centric** iOS experiences. This guide defines iOS-native design patterns and best practices for creating high-quality applications.

---

## Table of Contents

1. [Core Design Principles](#1-core-design-principles)
2. [Design DNA & Visual Language](#2-design-dna--visual-language)
3. [Colour System](#3-colour-system)
4. [Typography — System Font](#4-typography--system-font)
5. [Spacing & Layout](#5-spacing--layout)
6. [Components](#6-components)
7. [Imagery & Media](#7-imagery--media)
8. [Interaction & Motion](#8-interaction--motion)
9. [Accessibility Checklist](#9-accessibility-checklist)
10. [Token Naming & Design Systems](#10-token-naming--design-systems)
11. [Beyond the Basics: Achieving a Modern & Stylish Look](#11-beyond-the-basics-achieving-a-modern--stylish-look)
12. [Common Screen Patterns](#12-common-screen-patterns)

---

## 1. Core Design Principles

| Principle                 | Do                                                                       | Why                                       |
| ------------------------- | ------------------------------------------------------------------------ | ----------------------------------------- |
| **iOS Native First**      | Follow Apple's Human Interface Guidelines and use system components.     | Ensures familiarity and reliability.     |
| **Content-First Approach**| Prioritize content visibility over UI chrome and decoration.             | The UI should support the content.       |
| **Efficient Task Flow**   | Design for the user's primary tasks with clear progress feedback.        | Helps users achieve goals quickly.       |
| **Professional & Clean**  | Optimize for speed and efficiency over unnecessary visual flair.         | A clean UI inspires trust and feels fast. |
| **Touch-First Interface** | Ensure 44pt minimum touch targets and consider one-handed use.           | iOS is a mobile-first platform.          |
| **Graceful Error Handling**| Surface errors clearly with actionable recovery options.                 | Builds user trust and prevents frustration.|

### 1.1 Decision-Making Framework

**When designing any interface, ask:**

1.  **Does this follow iOS patterns?** → Use system components when possible.
2.  **Does this enhance the content?** → Reduce UI chrome, increase content space.
3.  **Does this streamline the user's main goal?** → Design for primary workflows.
4.  **Is this the simplest, fastest solution?** → Optimize for efficiency over beauty.
5.  **What happens when this fails?** → Design error states with clear recovery paths.

### 1.2 Copy & Content Guidelines

| Content Type     | Guidelines                                      | Good Examples                                    | Poor Examples        |
| ---------------- | ----------------------------------------------- | ------------------------------------------------ | -------------------- |
| **Button Labels**  | Use action verbs, be specific about what happens. | "Save Changes", "Export as PDF", "Add to Cart"   | "Submit", "Go"       |
| **Progress Text**  | Show current state and remaining work.          | "Step 3 of 5", "Uploading 8 of 24 files..."      | "Please wait..."     |
| **Error Messages** | Explain the problem and provide a solution.     | "No Internet Connection. Check your settings."   | "Something went wrong" |
| **Settings Labels**| Explain technical terms with context.           | "Video Quality: 1080p (recommended)"             | "High Quality"       |

### 1.3 Accessibility Requirements

- **Dynamic Type:** All text must scale with system font size settings.
- **VoiceOver:** All interactive elements need descriptive labels.
- **Color Independence:** Use icons or text alongside color to convey information.
- **Motion Sensitivity:** Reduce non-essential animations when "Reduce Motion" is enabled.
- **Touch Targets:** A minimum of 44pt × 44pt for all tappable areas is required.

---

## 2. Design DNA & Visual Language

| Attribute           | Guidance                                                                                                             | Visual Cue                   |
| ------------------- | -------------------------------------------------------------------------------------------------------------------- | ---------------------------- |
| **Tone**            | Professional, efficient, trustworthy, and intuitive.                                                                 | Clean interface, minimal distractions. |
| **Content**         | The user's content is the hero; UI should be secondary and supportive.                                                | Ample content padding, high contrast. |
| **Geometry**        | Use the iOS-native corner radius: 8-12pt for cards, 6pt for buttons.                                                 | System-consistent rounding.           |
| **Accent Strategy** | **Blue** for system actions & navigation • **Green** for success • **Orange** for warnings • **Red** for errors/destructive actions. | Follows iOS semantic color usage. |

> **Palette Heuristic:** *Follow iOS semantic colors for predictable user interactions.*

---

## 3. Colour System

### 3.1 Premium Dark Theme Color Palette

Tyniy uses a premium dark theme that matches the app icon's visual identity, creating a cohesive, professional experience for photography workflows.

#### Core Colors

| Token                    | Hex Code   | Usage                                                      |
| ------------------------ | ---------- | ---------------------------------------------------------- |
| `premium/background`     | `#1A1C20`  | Primary background - Very dark, near-black                |
| `premium/cardBackground` | `#2A2D33`  | Card backgrounds - Dark gray, slightly lighter than main  |
| `premium/primaryText`    | `#FFFFFF`  | Primary text - Clean, bright white for high contrast      |
| `premium/secondaryText`  | `#A0A0A0`  | Secondary text - Light gray for de-emphasized content     |

#### Accent Colors

| Token                    | Hex Code   | Usage                                                      |
| ------------------------ | ---------- | ---------------------------------------------------------- |
| `premium/accentBlue`     | `#00AEEF`  | Primary accent - Vibrant blue from icon's "T"             |
| `premium/accentOrange`   | `#FF8C42`  | Secondary accent - Warm orange for highlights & actions   |

#### Premium Gradients

| Token                    | Colors                          | Usage                                    |
| ------------------------ | ------------------------------- | ---------------------------------------- |
| `premium/blueGradient`   | `#00AEEF` → `#0088CC`          | Primary blue elements, progress bars     |
| `premium/orangeGradient` | `#FF8C42` → `#E67332`          | Orange buttons, warning states           |
| `premium/dynamicGradient`| `#00AEEF` → `#FF8C42`          | Hero elements, upgrade prompts, special effects |

#### Effect Colors

| Token                    | Hex Code   | Usage                                                      |
| ------------------------ | ---------- | ---------------------------------------------------------- |
| `premium/blueGlow`       | `#00AEEF`@15% | Card glow effects, primary element shadows            |
| `premium/orangeGlow`     | `#FF8C42`@15% | Orange element shadows, accent highlights             |
| `premium/gridOverlay`    | `#FFFFFF`@2%  | Subtle grid pattern overlay (matching app icon)      |

### 3.2 Color Usage Guidelines

#### Blue Accent (`#00AEEF`)
- **Primary actions** (main import buttons)
- **Progress indicators** and status rings
- **Interactive elements** and links
- **Card borders** and subtle glows
- **Navigation** and system elements

#### Orange Accent (`#FF8C42`)
- **Secondary actions** (upgrade prompts)
- **Warning states** and attention-grabbing elements
- **Statistics** and metric highlights
- **Call-to-action** buttons for conversions
- **Warm accents** to balance cool blue tones

#### Dynamic Blue-to-Orange Gradient
- **Hero elements** (animated rings, app icon highlights)
- **Premium features** (upgrade screens, purchase buttons)
- **Progress indicators** showing completion
- **Special effects** and engaging animations

### 3.3 Accessibility & Contrast

All color combinations meet WCAG AA standards:
- **White text on dark backgrounds**: 15.3:1 contrast ratio
- **Blue accent on dark background**: 4.8:1 contrast ratio  
- **Orange accent on dark background**: 5.2:1 contrast ratio

### 3.4 Legacy iOS Semantic Support

For non-premium screens or system integrations, fall back to iOS semantic colors:

| Token                 | Light Mode   | Dark Mode    | Usage                                    |
| --------------------- | ------------ | ------------ | ---------------------------------------- |
| `accent/green`        | `#34C759`    | `#30D158`    | Success states, completion indicators    |
| `accent/red`          | `#FF3B30`    | `#FF453A`    | Error states, destructive actions        |
| `separator/default`   | `#3C3C43`    | `#38383A`    | Hairline borders, dividers               |

### 3.3 Elevation & Shadow

| Level | Shadow                    | Example         |
| ----- | ------------------------- | --------------- |
| 1     | `0 2 8 rgba(0,0,0,0.08)`  | Cards, list items |
| 2     | `0 4 16 rgba(0,0,0,0.10)` | Floating sheets, toolbars |
| 3     | `0 8 24 rgba(0,0,0,0.16)` | Modals, context menus |

---

## 4. Typography — System Font

Using the iOS system font (San Francisco) is highly recommended for its legibility and automatic support for Dynamic Type.

| Style               | iOS Text Style    | Size (pt) | Weight    | Purpose                           |
| ------------------- | ----------------- | --------- | --------- | --------------------------------- |
| `largeTitle`        | largeTitle        | 34        | Regular   | Main screen titles                |
| `title1`            | title1            | 28        | Regular   | Section headers                   |
| `title2`            | title2            | 22        | Regular   | Card titles, modal headers        |
| `headline`          | headline          | 17        | Semibold  | Emphasized content, list item titles |
| `body`              | body              | 17        | Regular   | Primary body text                 |
| `subheadline`       | subheadline       | 15        | Regular   | List item subtitles, secondary info |
| `footnote`          | footnote          | 13        | Regular   | Helper text, metadata             |
| `caption1`          | caption1          | 12        | Regular   | Image captions, fine print        |

---

## 5. Spacing & Layout (iOS 8pt Grid)

| Token       | Value | Usage                           |
| ----------- | ----- | ------------------------------- |
| `space/xs`  | 4pt   | Icon padding, micro adjustments |
| `space/s`   | 8pt   | Element spacing, text gaps      |
| `space/m`   | 16pt  | Card padding, button insets     |
| `space/l`   | 20pt  | Standard screen margins         |
| `space/xl`  | 32pt  | Section separators              |
| `space/xxl` | 44pt  | Large section breaks            |

**Layout Guidelines:**
- **Safe Areas:** Always respect iOS safe area insets.
- **List Margins:** Use standard 20pt leading/trailing margins for full-width lists.
- **Touch Targets:** Minimum 44pt × 44pt for all interactive elements.
- **Readable Content Width:** For text-heavy views, constrain line width for readability.

---

## 6. Components

### 6.1 Buttons (iOS Native Styles)

| Variant     | Style            | Fill/Text Color               | Radius | Use Case                                  |
| ----------- | ---------------- | ----------------------------- | ------ | ----------------------------------------- |
| **Filled**  | Prominent        | `accent/blue` fill, white text| 8-12pt | Primary call-to-action (CTA).           |
| **Tinted**  | Secondary        | `accent/blue` (light), blue text | 8-12pt | Important, but not the primary action.      |
| **Gray**    | Subtle           | Gray fill, primary text       | 8-12pt | Standard, non-urgent actions.             |
| **Plain**   | Tertiary         | `accent/blue` text, no fill   | 0pt    | Less important actions, often in toolbars.  |
| **Destructive**| Filled or Plain| `accent/red`, white/red text| 8-12pt | Actions that delete data (e.g., "Delete"). |

*Icon buttons:* Must have a 44 × 44 pt touch area with a centered 24-28pt icon.

### 6.2 Lists & Grids

**Lists (`UITableView` / `UICollectionViewListConfiguration`):**
- Use for vertically scrolling content.
- Employ standard cell styles (e.g., `value1`, `subtitle`) for consistency.
- Use section headers to group related items.

**Grids (`UICollectionView`):**
- Use for visually rich, multi-column content.
- Ensure consistent spacing (e.g., 2-8pt) between items.
- Provide clear selection states (e.g., border, checkmark, or overlay).

### 6.3 Progress & Status Indicators

**Progress:**
- **Determinate:** Use a linear progress bar (`UIProgressView`) for tasks with a known duration. Show percentage text.
- **Indeterminate:** Use a spinning activity indicator (`UIActivityIndicatorView`) for tasks of unknown length.

**Status Pills/Badges:**
- Use colored, capsule-shaped labels to denote an item's state.
- **Success:** Green background, white text.
- **Error:** Red background, white text.
- **Warning/In-Progress:** Orange/Yellow background, dark text.

---

## 7. Imagery & Media

| Guideline       | Specification                                                     |
| --------------- | ----------------------------------------------------------------- |
| **Hero/Banners**| 16:9 or similar wide aspect ratio, full-bleed.                    |
| **Thumbnails**  | 1:1 or 4:3 aspect ratio, with corner radius matching the container.|
| **Placeholders**| Use a subtle gray background or blurred hash while loading.       |
| **Overlays**    | Use a 0-60% black gradient to ensure text legibility over images. |

---

## 8. Interaction & Motion

| Trigger → Response | Duration    | Easing                      |
| ------------------ | ----------- | --------------------------- |
| Tap → Screen push  | 240 ms      | iOS default cubic-out       |
| FAB → Sheet rise   | 300 ms      | cubic-out (with overshoot)  |
| Button tap         | 80 ms       | ease-out (scale 0.95 → 1.0) |
| List item select   | 180 ms      | spring-based animation      |

> Use motion to reinforce meaning, guide focus, and provide feedback—not for decoration. Disable non-essential animation when *Reduce Motion* is enabled.

---

## 9. Accessibility Checklist

1.  **Contrast:** AA ≥ 4.5:1 for body text. Use Xcode's color contrast checker.
2.  **Tap targets:** ≥ 44 × 44 pt for all interactive elements.
3.  **Dynamic Type:** Ensure all text styles are configured to scale. Test in simulator.
4.  **VoiceOver:** Add descriptive `.accessibilityLabel` for all controls and images.
5.  **Colour-blind support:** Never convey state or information by colour alone.
6.  **Motion:** Wrap animations in `if !UIAccessibility.isReduceMotionEnabled`.

---

## 10. Token Naming & Design Systems

For projects with a design system, use a structured naming convention for design tokens. This allows for easier export and consumption in code.

A common format is `category/subcategory/variant` in kebab-case.

**Example Token Structure:**
```json
{
  "color": {
    "background": {
      "primary": "#FFFFFF",
      "secondary": "#F2F2F7"
    },
    "text": {
      "primary": "#000000"
    },
    "accent": {
      "brand": "#FF8A00",
      "success": "#34C759"
    }
  },
  "space": {
    "s": 8,
    "m": 16,
    "l": 20
  }
}
```
This structure can be easily parsed into Swift code (e.g., `UIColor.backgroundPrimary`).

---

## 11. Beyond the Basics: Achieving a Modern & Stylish Look

A style guide ensures consistency and usability; it does not have to result in a "boring" app. The principles here are a foundation. A modern, stylish, and memorable app is created by thoughtfully applying a unique brand identity on top of this solid base.

| Customization Vector  | Strategy for a Modern Feel                                                                                                     | Example                                                                          |
| --------------------- | -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| **Brand Color Palette** | Go beyond the default `systemBlue`. Define a primary brand color for key actions and a set of secondary colors for states or themes. | Use a vibrant brand color for the main "Add to Cart" button.                       |
| **Expressive Typography**| While SF Pro is excellent for body text, use a custom display font for large headlines (`largeTitle`) to add character.           | A custom, slightly rounded font for screen titles to convey a friendly tone.     |
| **Custom Iconography**  | A unique, professionally designed icon set is a powerful brand identifier. Ensure icons are cohesive and instantly recognizable.   | Replacing the standard SF Symbols with a custom-designed set for the tab bar.    |
| **Delightful Motion**   | Use custom animations for state changes, loading indicators, or success screens to add personality and provide feedback.          | A fun animation plays when a user successfully completes a major task.           |
| **Component Styling**   | Adjust the corner radius of buttons and cards, apply subtle gradients to backgrounds, or use unique shadow styles.               | Giving all cards a slightly larger corner radius (e.g., 16pt) for a softer look.  |
| **Engaging Empty States** | Don't just show "No Data". Use this space for brand illustrations, helpful tips, and a clear call-to-action.                  | An illustration of a character looking through binoculars on a "No search results" screen. |

**Key Principle:** The goal is to create a *cohesive brand experience*, not to customize every single element. Apply these customizations consistently where they have the most impact.

---

## 12. Common Screen Patterns

### 12.1 Onboarding / Login Screen
- **Goal:** Introduce the app or authenticate the user.
- **Layout:** Centered content, prominent logo, clear text fields, and a single, primary call-to-action button.
- **Components:** `UILabel` for titles, `UITextField` for input, `UIButton` for actions. Often uses a `UIPageViewController` for multi-step onboarding.

### 12.2 List & Detail View
- **Goal:** Allow users to browse a collection of items and view details about a specific one.
- **Layout:** A `UITableView` or `UICollectionView` (the List) that, upon selection, pushes a new view controller (the Detail) onto the `UINavigationController` stack.
- **Components:** `UINavigationController`, `UITableViewController`, `UIViewController`.

### 12.3 Settings Screen
- **Goal:** Allow users to configure the app.
- **Layout:** A grouped `UITableView` is the standard pattern.
- **Components:** Use `UITableViewCell` with different controls: `UISwitch` for booleans, disclosure indicators (`>`) for sub-menus, and `UILabel` to show current values.

