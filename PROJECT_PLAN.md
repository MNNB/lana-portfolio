# Project Plan: Graphic Designer Portfolio Website

**Objective:** Develop a responsive, performant, and visually appealing portfolio website for a graphic designer using Astro and vanilla CSS, incorporating placeholder content and images initially, with Figma designs to guide the visual implementation.

**Phases & Deliverables:**

**Phase 1: Foundation & Core Structure (Astro Setup & Basic Layouts)**

1.  **Project Initialization & Configuration:**
    *   Review and confirm the existing Astro project setup in `lana-portfolio/`.
    *   Set up basic project structure:
        *   `src/components/` for reusable UI elements (Header, Footer, Navigation, ProjectCard, etc.).
        *   `src/layouts/` for page layouts (BaseLayout, ProjectLayout).
        *   `src/pages/` for main site pages (index.astro, about.astro).
        *   `src/content/projects/` for Markdown-based project pages.
        *   `src/styles/` for global CSS, variables, and component-specific styles.
        *   `public/placeholders/` for placeholder images.
2.  **Global Styles & Design Tokens:**
    *   Define CSS variables for colors, typography (font families, sizes, weights), spacing units, and breakpoints based on the provided Figma designs (once available) or the visual cues from the initial image.
    *   Create a `global.css` file for base styling (resets, body styles, typography defaults).
3.  **Core Layout Component (`Layout.astro`):**
    *   Develop the main layout component in `src/layouts/Layout.astro` that will wrap all pages.
    *   Include slots for page-specific content.
    *   Integrate placeholders for Header and Footer components.
4.  **Header Component:**
    *   Create `src/components/Header.astro`.
    *   Implement basic structure: logo, navigation links (Home, About).
    *   Plan for responsive behavior (desktop menu vs. mobile burger menu) – initial structure, JavaScript for interactivity will come later.
5.  **Footer Component:**
    *   Create `src/components/Footer.astro`.
    *   Implement basic structure: contact information, social media links (placeholders), copyright.
6.  **Basic Page Creation:**
    *   Create `src/pages/index.astro` (Home Page) using the `Layout.astro`.
    *   Create `src/pages/about.astro` (About Page) using the `Layout.astro`.
    *   Populate with placeholder text content.

**Phase 2: Home Page Development**

1.  **Hero Section:**
    *   Develop `src/components/HeroSection.astro`.
    *   Layout for showcasing the designer's best work (placeholder image/video).
    *   Call-to-action elements.
2.  **Project Grid & Filter:**
    *   Develop `src/components/ProjectGrid.astro`.
    *   Implement a 2-column responsive grid for project thumbnails.
    *   Create `src/components/ProjectCard.astro` for individual project representation (thumbnail, title, category placeholders).
    *   Develop `src/components/CategoryFilter.astro`.
        *   Static list of categories: branding, packaging, illustration, motion, photo retouching, art direction.
        *   Styling for the filter menu. (Interactivity will be a separate step).
3.  **Services Section:**
    *   Develop `src/components/ServicesSection.astro`.
    *   Layout to highlight expertise areas (placeholder text).
4.  **Contact Section:**
    *   Develop `src/components/ContactForm.astro`.
    *   Basic HTML structure for the form (name, email, message). (Form submission logic will be handled later or via a service like Netlify Forms).
    *   Display professional availability (placeholder text).
5.  **Testimonials Section (Placeholder):**
    *   Develop `src/components/TestimonialsSection.astro`.
    *   Structure for displaying client testimonials (placeholder content).

**Phase 3: About Page Development**

1.  **Professional Biography Section:**
    *   Structure for text content.
2.  **Skills & Expertise Visualization:**
    *   Plan for how skills will be displayed (e.g., list, simple bar chart with CSS – based on Figma).
    *   Placeholder content.
3.  **Education & Experience Timeline:**
    *   Structure for a timeline layout.
    *   Placeholder content.
4.  **Personal Philosophy Section:**
    *   Structure for text content.
5.  **Headshot Section:**
    *   Placeholder for a high-quality professional headshot.

**Phase 4: Project Pages (Markdown)**

1.  **Project Layout (`ProjectLayout.astro`):**
    *   Create `src/layouts/ProjectLayout.astro`.
    *   Define the structure for individual project pages: large imagery, project description, related projects, CTA.
2.  **Markdown Content Structure:**
    *   Define the frontmatter for project Markdown files (e.g., title, date, category, thumbnail, heroImage).
    *   Create example project Markdown files in `src/content/projects/` with placeholder content and frontmatter.
    *   Example: `src/content/projects/sample-project-1.md`
3.  **Dynamic Project Page Generation:**
    *   Create `src/pages/projects/[...slug].astro` to dynamically generate pages from Markdown files.
    *   Fetch and render Markdown content using the `ProjectLayout.astro`.
4.  **Related Projects Section:**
    *   Plan logic for displaying related projects (e.g., by category, or manually specified – placeholder for now).
5.  **Call-to-Action (CTA):**
    *   Consistent CTA on project pages.

**Phase 5: Interactivity & Refinements**

1.  **Responsive Navigation:**
    *   Implement JavaScript for the mobile burger menu functionality in the Header.
    *   Ensure smooth transitions and accessibility.
2.  **Interactive Category Filter:**
    *   Implement JavaScript to filter the `ProjectGrid.astro` based on selected categories.
    *   Update UI to reflect active filters.
3.  **Subtle Animations & Transitions:**
    *   Identify areas for subtle CSS animations/transitions (e.g., hover effects, page transitions if desired, scroll-based animations – keep it tasteful and performance-friendly).
4.  **Image Optimization Strategy:**
    *   Integrate with the MCP server for image optimization once its API/functionality is clear.
    *   If MCP server integration is complex or delayed, implement basic Astro image optimization features (`<Image />` component or similar).
    *   Ensure responsive images (`<picture>` element or `srcset` attribute).
5.  **Form Handling:**
    *   Implement contact form submission (e.g., using Netlify Forms, or a serverless function if the MCP server provides this).

**Phase 6: Content Integration & SEO**

1.  **Replace Placeholders:**
    *   Integrate actual text content provided by the designer.
    *   Integrate actual image assets.
2.  **SEO Basics:**
    *   Implement meta tags (title, description) for each page.
    *   Ensure semantic HTML.
    *   Add `robots.txt` and `sitemap.xml`.
    *   Open Graph tags for social sharing.

**Phase 7: Testing & Deployment**

1.  **Cross-Browser & Cross-Device Testing:**
    *   Test thoroughly on major browsers (Chrome, Firefox, Safari, Edge) and device viewports (desktop, tablet, mobile).
2.  **Performance Audit:**
    *   Use tools like Lighthouse to check performance, accessibility, and SEO.
    *   Optimize where necessary.
3.  **Deployment to Netlify:**
    *   Set up Netlify project.
    *   Configure build settings.
    *   Deploy the site.
4.  **Custom Domain Implementation:**
    *   Configure DNS records for the custom domain.

**Site Architecture (Mermaid Diagram):**

```mermaid
graph TD
    A[Client Browser] --> B{Astro Website};

    subgraph B [Astro Website on Netlify]
        C[/" (Home Page - index.astro)"]
        D["/about (About Page - about.astro)"]
        E["/projects/[slug] (Project Pages - pages/projects/[...slug].astro)"]

        C --> F[Header Component];
        C --> G[Hero Section];
        C --> H[Project Grid Component];
        H --> I[Project Card Component];
        H --> J[Category Filter Component];
        C --> K[Services Section];
        C --> L[Contact Section w/ Form];
        C --> M[Testimonials Section];
        C --> N[Footer Component];

        D --> F;
        D --> O[Bio Section];
        D --> P[Skills Section];
        D --> Q[Experience Timeline];
        D --> R[Philosophy Section];
        D --> S[Headshot];
        D --> N;

        E --> T[ProjectLayout.astro];
        T --> U[Markdown Content (Challenge, Process, Solution)];
        T --> V[Large Imagery];
        T --> W[Related Projects];
        T --> X[Project CTA];
        T --> F;
        T --> N;

        subgraph Content [src/content/projects/]
            Y[project-1.md]
            Z[project-2.md]
            AA[project-n.md]
        end

        E -.-> Y;
        E -.-> Z;
        E -.-> AA;

        subgraph Layouts [src/layouts/]
            AB[Layout.astro]
            AC[ProjectLayout.astro]
        end

        C -.-> AB;
        D -.-> AB;
        E -.-> AC;
        AC -.-> AB;


        subgraph Components [src/components/]
            F
            G
            H
            I
            J
            K
            L
            M
            N
            O
            P
            Q
            R
            S
            X
        end
    end

    AD[Figma Designs] -.-> B;
    AE[MCP Server (Image Opt.)] <--> B;
    AF[Content (Text/Images)] -.-> B;
```

**Assumptions & Notes:**

*   The Figma designs will provide clear guidance on visual styling, layout, typography, and color schemes.
*   The MCP server's image optimization functionality will be clearly defined and accessible.
*   Vanilla CSS will be used, potentially with a structured approach like BEM or utility classes for maintainability, but no CSS frameworks like Tailwind unless specified.
*   Focus on fluid layouts and responsive design principles from the start.