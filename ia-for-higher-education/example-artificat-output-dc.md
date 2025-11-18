# Information Architecture Recommendations for UC San Diego Library Digital Collections

## Recommendation 1: Task-First Navigation with Collection Context

### Overview
Restructure the primary navigation to lead with user tasks rather than organizational categories, while providing clear context about collection scope and purpose through progressive disclosure.

### Structural Approach
The current navigation lacks clarity about the site's unique value proposition. This recommendation places user goals at the forefront while addressing the critical pain point of users not understanding when to use this platform versus the main library search.

### Information Architecture

```
Home
├── Search & Discover
│   ├── Advanced Search
│   ├── Browse by Subject
│   │   ├── Earth Sciences
│   │   ├── Biological Sciences
│   │   ├── Chemical Sciences
│   │   ├── Information & Computing Sciences
│   │   ├── Education
│   │   └── Archaeology
│   └── Browse by Format
│       ├── Research Datasets
│       ├── Historical Documents
│       ├── Photographs
│       ├── Audio & Video
│       └── Maps & Visual Materials
├── For Researchers
│   ├── Research Data Collections
│   ├── Data Access Requirements
│   ├── Citation Guidelines
│   └── Download & Use Policies
├── For Teaching
│   ├── Classroom-Ready Materials
│   ├── Assignment Ideas
│   ├── Instructor Resources
│   └── Request Teaching Support
├── Contribute Materials
│   ├── Submit Research Data
│   ├── Digitization Services
│   ├── Donation Guidelines
│   └── Contact Our Team
├── Collections Highlights
│   ├── Featured Collections
│   ├── Baja California
│   ├── Melanesia & Pacific
│   ├── UC San Diego History
│   ├── Border Art
│   └── East Asian Collections
└── About & Help
    ├── What's in Digital Collections?
    ├── How to Use This Site
    ├── Technical Support
    └── Contact Information
```

### Detailed Explanation
The restructured navigation prioritizes user mental models by organizing around tasks ("Search & Discover," "For Researchers," "For Teaching") rather than library organizational structure. The "What's in Digital Collections?" section directly addresses the core pain point by clearly explaining the platform's scope and differentiating it from general library search.

The "Browse by Subject" organization aligns with the site's research strengths, while "Browse by Format" accommodates different user preferences for material types. Task-based sections like "For Researchers" and "For Teaching" use progressive disclosure to reveal relevant tools and resources without overwhelming the main navigation.

### Research-Based Rationale
Task-oriented navigation structures significantly improve findability and user satisfaction in academic contexts (Battleson et al., 2001). The Nielsen Norman Group's research on university websites demonstrates that users perform better when navigation reflects their goals rather than institutional organization (Pernice & Nielsen, 2009). Progressive disclosure principles help manage cognitive load while maintaining access to comprehensive functionality (Miller, 1956).

---

## Recommendation 2: Audience-Aware Hub Structure with Smart Defaults

### Overview
Create audience-specific entry points that adapt the interface and content presentation based on user type, while maintaining a unified search experience across all user paths.

### Structural Approach
This approach acknowledges the diverse user base while providing personalized pathways that reduce cognitive overhead. Smart defaults and contextual help guide users toward relevant materials and workflows.

### Information Architecture

```
Home
├── I'm Looking For... (Prominent Section)
│   ├── Research Data & Publications
│   ├── Historical Materials & Archives
│   ├── Teaching & Learning Resources
│   └── Browse Everything
├── Quick Access Portals
│   ├── Researchers & Faculty
│   │   ├── Research Data Hub
│   │   ├── Publication Support
│   │   └── Collaboration Tools
│   ├── Students & Instructors
│   │   ├── Course Materials
│   │   ├── Assignment Resources
│   │   └── Study Collections
│   ├── Community & Public
│   │   ├── Local History
│   │   ├── Cultural Collections
│   │   └── General Interest
│   └── Depositors & Contributors
│       ├── Submit Materials
│       ├── Manage Collections
│       └── Support & Guidelines
├── Featured & New
│   ├── Recent Additions
│   ├── Popular Collections
│   └── Spotlight Items
├── Search Tools
│   ├── Simple Search
│   ├── Advanced Search
│   ├── Visual Browse
│   └── API Access
└── Support & Information
    ├── Getting Started Guide
    ├── Collection Scope
    ├── Technical Help
    └── Contact Specialists
```

### Detailed Explanation
The "I'm Looking For..." section serves as a clear disambiguation tool, directly addressing user confusion about the site's purpose. Each option leads to tailored search interfaces with appropriate filters and result displays. The Quick Access Portals provide audience-specific entry points without fragmenting the underlying content structure.

Smart defaults adjust search filters, result sorting, and featured content based on the chosen pathway. For example, the "Researchers & Faculty" portal emphasizes peer-reviewed data and research outputs, while "Community & Public" highlights accessible historical and cultural materials.

### Research-Based Rationale
Audience-based navigation structures improve task completion rates in complex digital libraries (Park, 2000). Card sorting studies consistently show that users prefer hybrid classification systems that combine topical and audience-based organization (Rosenfeld et al., 2015). The hub model reduces navigation depth while maintaining logical relationships between content areas (Kalbach, 2007).

---

## Recommendation 3: Discovery-Focused Architecture with Collection Storytelling

### Overview
Transform the navigation to emphasize discovery and exploration while embedding collection narratives that help users understand the unique value and context of materials.

### Structural Approach
This approach treats the digital collections as a discovery destination rather than just a search tool, incorporating storytelling elements and visual navigation that showcase the breadth and uniqueness of materials.

### Information Architecture

```
Home
├── Discover Collections
│   ├── Explore by Theme
│   │   ├── Ocean & Earth Sciences
│   │   ├── Regional Cultures
│   │   ├── University History
│   │   ├── Border & Migration
│   │   └── Arts & Literature
│   ├── Explore by Time Period
│   ├── Explore by Geography
│   └── Surprise Me (Random Discovery)
├── Research & Data
│   ├── UC San Diego Research
│   ├── Open Research Data
│   ├── Data Visualization Tools
│   └── Research Collaboration
├── Teaching Toolkit
│   ├── Primary Source Sets
│   ├── Assignment Templates
│   ├── Student Showcase
│   └── Educator Community
├── Search & Find
│   ├── Quick Search
│   ├── Advanced Search
│   ├── Browse A-Z
│   └── Search Tips & Tricks
├── Collection Stories
│   ├── Behind the Scenes
│   ├── Curator Insights
│   ├── Community Connections
│   └── Impact & Use Cases
└── Get Involved
    ├── Contribute Your Materials
    ├── Volunteer Opportunities
    ├── Community Partnerships
    └── Support the Collections
```

### Detailed Explanation
The "Discover Collections" section transforms browsing from a utilitarian task into an engaging exploration experience. Thematic organization helps users understand the interconnections between materials while geographic and temporal browsing accommodate different discovery preferences.

"Collection Stories" addresses the pain point about understanding the site's purpose by showcasing the human stories, research impact, and community connections behind the collections. This narrative approach helps users grasp the unique value proposition while building emotional connection to the materials.

The "Teaching Toolkit" goes beyond simple resource access to provide pedagogical support, positioning the platform as an active partner in education rather than just a content repository.

### Research-Based Rationale
Discovery-oriented interfaces increase user engagement and serendipitous learning in digital libraries (Bates, 1989). Narrative frameworks help users develop mental models of complex information spaces, improving both comprehension and retention (Davenport & Beck, 2001). The storytelling approach aligns with research showing that context and provenance information significantly impact user trust and material usage in academic settings (Yakel & Torres, 2003).

---

## Annotated Bibliography

**Bates, M. J. (1989).** The design of browsing and berrypicking techniques for the online search interface. *Online Review, 13*(5), 407-424.
This seminal work on information seeking behavior provides the theoretical foundation for discovery-oriented interface design, demonstrating how browsing and exploration differ from directed search tasks.

**Battleson, B., Booth, A., & Weintrop, J. (2001).** Usability testing of an academic library web site: A case study. *The Journal of Academic Librarianship, 27*(3), 188-198.
Presents empirical evidence for task-based navigation effectiveness in academic library contexts, directly supporting the recommendations for user-centered information architecture.

**Davenport, T. H., & Beck, J. C. (2001).** *The attention economy: Understanding the new currency of business*. Harvard Business Review Press.
Provides framework for understanding how narrative and storytelling can capture and maintain user attention in information-rich environments.

**Kalbach, J. (2007).** *Designing web navigation*. O'Reilly Media.
Comprehensive guide to navigation design principles, particularly valuable for the hub model and progressive disclosure recommendations.

**Miller, G. A. (1956).** The magical number seven, plus or minus two: Some limits on our capacity for processing information. *Psychological Review, 63*(2), 81-97.
Classic cognitive psychology research that informs progressive disclosure and information chunking strategies in interface design.

**Park, S. (2000).** Usability, user preferences, effectiveness, and user behaviors when searching individual and integrated full-text databases. *Journal of the American Society for Information Science, 51*(5), 456-468.
Demonstrates the effectiveness of audience-based navigation and customized search interfaces in academic contexts.

**Pernice, K., & Nielsen, J. (2009).** *How to conduct eyetracking studies*. Nielsen Norman Group.
Research methodology and findings that support task-oriented navigation design in higher education websites.

**Rosenfeld, L., Morville, P., & Arango, J. (2015).** *Information architecture: For the web and beyond* (4th ed.). O'Reilly Media.
Authoritative text on information architecture principles, particularly relevant for hybrid classification systems and scalability considerations.

**Yakel, E., & Torres, D. A. (2003).** AI: Archival intelligence and user expertise. *The American Archivist, 66*(1), 51-78.
Research on how users interact with archival and special collections materials, supporting the importance of context and storytelling in digital collections interfaces.