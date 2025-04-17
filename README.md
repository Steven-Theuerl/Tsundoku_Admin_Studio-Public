# Tsundoku Admin Studio - Headless CMS

Tsundoku Admin Studio is a custom-built headless CMS powered by Sanity.io.
It serves as the content engine behind my Tsundoku Blog, allowing me—and any future collaborators—to create, manage, and structure long-form articles, media content, and editorial metadata, all delivered to the frontend via GROQ-powered API.

Built for scale and usability, the Studio supports modern media formats (like WebP and MP4), intuitive editing flows, and custom schema definitions tailored for performance and collaboration.
Whether editing on a team or solo publishing, Tsundoku Admin Studio prioritizes flexibility, validation, and real-time previewing.

![image](https://github.com/user-attachments/assets/7e884c8a-1aa4-403f-9c7a-bfc295d8de85)

---

## 🔒 Code Access
This repository is intended for portfolio and informational purposes only.  
The source code is private and not included here.

If you are an employer, collaborator, or researcher interested in viewing the implementation details,  
please reach out directly to discuss access or licensing.

---

## 🖠 Tech Stack

- **CMS:** Sanity.io  
- **Language:** TypeScript  
- **Query Language:** GROQ  
- **UI Customization:** Sanity Studio v3 with Structure Builder + custom iframe preview integration
- **Data Delivery:** Sanity Content Lake (proprietary CDN) via REST and GROQ-powered APIs
- **Form Enhancements:** Custom components, validation rules, conditional fieldsets, and grouped inputs

---

## 🧬 Schema Architecture Overview

- **Document Types**:  
  `Post` (for article creation), with future support for other content-driven document types  
- **Field Types**:  
  `string` (for titles, authors, categories, descriptions, in-page links, and alt text)  
  `slug` (auto-generated from title with validation)  
  `date` (for both publication and update tracking)  
  `array` of block content (Portable Text for rich text, quotes, and embedded media)  
  `file` (for WebP/MP4 assets), `image` (for fallback static image support)  
- **Custom Inputs**:  
  Conditional sections, grouped fieldsets, schema validation, live preview pane  
- **Relationships**:  
  Tag and Category references enable GROQ filtering for related content and scoped queries  


---

## ✨ Core Features

- Custom schema type and layout purpose-built for long-form articles  
- Multiple `BodyText`, `BodyImage`, and `BodyQuote` blocks per article, with optional in-page anchor support  
- Image hotspot support for precise focal point control on Main Visual assets  
- Custom slug fields with real-time validation and fallback logic  
- GROQ-powered queries for dynamic related content filtering
  ![image](https://github.com/user-attachments/assets/9a597995-4a56-471a-85ab-ca91c62b338b)
- UI grouping with `Fieldsets` and `Groups` for improved editor experience  
- Integrated **Preview Pane** using `sanity-plugin-iframe-pane`, enabling real-time draft previews inside the Studio
- Cookie-based **draft mode** logic to prevent unpublished content from leaking into production  
- Body media schema uses `type: 'file'` instead of `type: 'image'` to support both **WebP** and **MP4** formats—cutting media size by up to 98% and improving load times significantly
- Built-in flexibility to support future content types—timelines, video posts, project showcases—through scalable schema design  

---

## 🧠 What I Learned

- Built a deep understanding of Sanity’s schema architecture, preview workflows, and Structure Builder API  
- Learned how to query and index deeply nested Portable Text blocks using GROQ for article-level search functionality  
- Used the Sanity Studio inspect tool to infer schema relationships and build dynamic GROQ filters via projections and joins  
- Improved editor UX through grouped fieldsets, conditional inputs, custom validation rules, and live previews  
- Integrated custom components into the Studio tailored to workflow, accessibility, and content-type needs  

---

## 🤔 Challenges

- Customized GROQ queries to power related content scoring and timeline view logic
- **Preview content isolation:** Initially encountered issues with draft content leaking into live views. Solved this by gating preview access behind a custom API and securing access via session-based cookies—ensuring draft mode is never unintentionally exposed outside the studio  
- **Live preview pane integration:** Embedded a side-by-side preview panel in the Studio UI to support faster iteration and real-time feedback for non-technical collaborators  
- **Schema-level performance upgrade:** Migrated article body media from `type: 'image'` to `type: 'file'` to support optimized formats (WebP, MP4), cutting load times by up to 95%  


---

## 📈 Future Improvements

- Add document-level change history or version diffs via custom plugin
- Expand role-based access control for multi-user teams (if ever needed)
- Integrate image CDN transformation presets for social sharing

---

## ⚠️ Legal Notice

This is a public-facing portfolio repository intended for informational and showcase purposes only.  
All content, schema files, structure builder logic, and GROQ queries are original works by **Steven Theuerl**.

You may not copy, modify, reuse, or repurpose any part of this project in your own work.

Unauthorized use, in whole or in part, will be treated as intellectual property theft and may result in legal action.

If you're interested in collaboration or licensing, please contact me directly.

**© 2025 Steven Theuerl. All rights reserved.**
