# Humanizer: Complete AI Writing Pattern Detection and Removal Guide

This reference document compiles the comprehensive catalog of 24 AI writing patterns, anti-patterns, rhetorical tropes, and voice restoration principles from the Humanizer skill and Wikipedia's WikiProject AI Cleanup.

---

## 1. Personality, Soul, and Authentic Developer Voice

Avoiding AI patterns is only half the objective. Sterile, robotic prose is just as artificial as synthetic text. Technical communication between engineers should sound like a human with expertise, judgment, and context.

### Signs of Soulless Writing (Even If Syntactically Clean)
- Monotonous sentence lengths and identical subject-verb-object structures across every paragraph.
- Total absence of technical opinions or evaluations of trade-offs.
- Inability to acknowledge real-world engineering messiness, edge-case warts, or operational friction.
- Passive refusal to take a stance on competing implementations.
- Reads like an anonymous marketing press release rather than an engineer's assessment.

### Techniques for Authentic Voice
1. **Have concrete technical opinions**: React to trade-offs directly.
   - *Soulless*: "There are advantages and disadvantages to using microservices."
   - *Authentic*: "For our two-engineer team, splitting this service into three microservices adds distributed tracing headaches with almost no scaling benefit."
2. **Vary sentence cadence**: Alternate between short, punchy statements and detailed, explanatory sentences.
3. **Acknowledge engineering complexity**: Real systems are rarely elegant end-to-end. Highlight known compromises honestly.
4. **Use natural pronouns**: Use *you* for the developer and *I* or *we* when expressing the agent's judgment or the team's recommendations.

---

## 2. Content Patterns (Patterns 1–6)

### 1. Undue Emphasis on Significance, Legacy, and Broader Trends
- **Words to watch**: *stands/serves as*, *is a testament/reminder*, *pivotal moment*, *crucial role*, *underscores its significance*, *reflects broader*, *symbolizing its enduring*, *setting the stage for*, *marking a shift*, *evolving landscape*, *indelible mark*.
- **Problem**: Artificial inflation of routine technical updates into monumental historical milestones.
- **Before**: "The migration to Kubernetes in 2024 served as a testament to the team's commitment to scalability, marking a pivotal moment in the evolving infrastructure landscape."
- **After**: "The team migrated services to Kubernetes in 2024 to automate container scaling and simplify rollbacks."

### 2. Undue Emphasis on Notability and Media Coverage
- **Words to watch**: *independent coverage*, *leading industry outlets*, *renowned expert*, *widely celebrated*, *active social media presence*.
- **Problem**: Listing external praise or authority without specific technical relevance.
- **Before**: "The algorithm was celebrated across major tech publications and authored by a world-renowned distributed systems expert."
- **After**: "The Raft consensus algorithm was published by Ongaro and Ousterhout in 2014 as an understandable alternative to Paxos."

### 3. Superficial Analyses with -ing Endings
- **Words to watch**: *highlighting...*, *underscoring...*, *ensuring...*, *reflecting...*, *fostering...*, *symbolizing...*, *encompassing...*, *showcasing...*.
- **Problem**: Tacking on participial phrases to fabricate analytical depth.
- **Before**: "The backend implements Redis caching, ensuring seamless low-latency lookups, fostering a responsive user experience, and showcasing our dedication to performance."
- **After**: "The backend caches database queries in Redis, reducing mean endpoint latency from 240ms to 18ms."

### 4. Promotional and Advertisement-Like Language
- **Words to watch**: *boasts a*, *vibrant*, *rich*, *profound*, *groundbreaking*, *breathtaking*, *stunning*, *world-class*, *seamless*, *state-of-the-art*.
- **Problem**: Infusing technical descriptions with marketing hyperbole.
- **Before**: "Our state-of-the-art platform boasts a rich ecosystem of groundbreaking developer tools designed to deliver a breathtaking coding experience."
- **After**: "The platform includes a CLI, an automated test runner, and a local debugging proxy."

### 5. Vague Attributions and Weasel Words
- **Words to watch**: *industry experts agree*, *observers have noted*, *critics argue*, *widely considered*, *studies show* (when uncited).
- **Problem**: Attributing opinions to anonymous authorities instead of citing specific data or specs.
- **Before**: "Experts believe that GraphQL is a crucial technology for modern client-server architectures."
- **After**: "GraphQL allows client applications to request only the specific fields needed, reducing mobile network payload sizes."

### 6. Formulaic "Challenges and Future Prospects" Outlines
- **Words to watch**: *Despite its... faces several challenges*, *Challenges and Legacy*, *Future Outlook*, *Despite these hurdles*.
- **Problem**: Padding technical summaries with formulaic school-essay concluding sections.
- **Before**: "Despite its high performance, PostgreSQL faces challenges with connection pooling under heavy load. Despite these hurdles, with ongoing active development, PostgreSQL continues to thrive as an indispensable database."
- **After**: "PostgreSQL opens a dedicated process per connection. For workloads exceeding 500 concurrent connections, use PgBouncer for connection pooling."

---

## 3. Language and Grammar Patterns (Patterns 7–12)

### 7. Overused AI Vocabulary Words
- **High-frequency AI words**: *additionally*, *align with*, *crucial*, *delve*, *emphasizing*, *enduring*, *enhance*, *fostering*, *garner*, *highlight* (verb), *interplay*, *intricate / intricacies*, *key* (adj), *landscape* (abstract), *pivotal*, *showcase*, *tapestry*, *testament*, *underscore* (verb), *valuable*, *vibrant*.
- **Before**: "Additionally, a crucial aspect of this intricate architecture is the interplay between services, showcasing how modern tools foster resilience in the cloud landscape."
- **After**: "Services communicate over gRPC with automated retries on network timeout."

### 8. Avoidance of "is" / "are" (Copula Avoidance)
- **Words to watch**: *serves as*, *stands as*, *marks*, *represents*, *boasts*, *features*, *offers*.
- **Problem**: Replacing simple verbs with convoluted equivalents.
- **Before**: "The gateway serves as the primary entry point and features four rate-limiting tiers."
- **After**: "The gateway is the primary entry point and has four rate-limiting tiers."

### 9. Negative Parallelisms
- **Problem**: Overusing rhetorical tropes like "It's not just about X, it's about Y" or "Not only... but also...".
- **Before**: "This refactoring is not merely about cleaner code; it is a declaration of our architectural standards."
- **After**: "This refactoring replaces circular dependencies with an event-driven architecture."

### 10. Rule-of-Three Stuffing
- **Problem**: Forcing descriptions into arbitrary triads.
- **Before**: "The CLI is intuitive, robust, and lightning-fast, ensuring speed, security, and scalability for every developer."
- **After**: "The CLI validates syntax locally before submitting the build job."

### 11. Elegant Variation (Synonym Cycling)
- **Problem**: Cycling through awkward synonyms to avoid repeating a word within a paragraph.
- **Before**: "The service processes user tokens. The daemon authenticates the credentials. The system then stores the session ticket."
- **After**: "The service validates user tokens and saves valid sessions to Redis."

### 12. False Ranges
- **Problem**: Using "from X to Y" when X and Y do not represent a valid spectrum or continuum.
- **Before**: "The platform supports everything from simple REST endpoints to enterprise machine learning pipelines."
- **After**: "The platform supports HTTP microservices and scheduled batch data jobs."

---

## 4. Style and Formatting Patterns (Patterns 13–18)

### 13. Em Dash Overuse
- **Problem**: Overusing em dashes (`—`) to mimic conversational sales copy.
- **Before**: "The database is fast—yet simple to deploy—making it ideal for startups—and enterprise teams alike."
- **After**: "The database is fast and straightforward to deploy for both small teams and large organizations."

### 14. Overuse of Boldface
- **Problem**: Mechanically bolding multiple keywords per paragraph.
- **Before**: "Our **authentication service** utilizes **JSON Web Tokens** with **RSA-256 signatures** to ensure **maximum security**."
- **After**: "The authentication service uses JSON Web Tokens with RSA-256 signatures."

### 15. Inline-Header Vertical Lists
- **Problem**: Defaulting to vertical bullet lists where every bullet starts with a bold title and colon for simple prose thoughts.
- **Before**:
  - **Performance**: High throughput across all nodes.
  - **Security**: Encrypted at rest using AES-256.
  - **Reliability**: 99.99% uptime guarantee.
- **After**: "The system provides 99.99% uptime, encrypts data at rest using AES-256, and supports up to 50,000 queries per second."

### 16. Title Case in Headings
- **Problem**: Capitalizing every word in Markdown section headers.
- **Before**: `## Setting Up Your Development Environment And Running Tests`
- **After**: `## Set up your development environment and run tests`

### 17. Decorative Emojis
- **Problem**: Prepending emojis to technical headers or bullet lists (`🚀 Launch`, `💡 Tip`, `✅ Done`).
- **Before**: "🚀 **Deployment Complete:** The build succeeded."
- **After**: "Deployment complete: all services updated."

### 18. Curly Quotation Marks
- **Problem**: Using typographic curly quotes (`“`, `”`) in technical code documentation where ASCII straight quotes (`"`, `'`) are required for syntax.
- **Before**: `const query = “SELECT * FROM users”;`
- **After**: `const query = "SELECT * FROM users";`

---

## 5. Communication Artifacts and Filler (Patterns 19–24)

### 19. Collaborative Conversational Artifacts
- **Forbidden openers**: "Sure thing!", "I'd be happy to help with that!", "Great question!", "Certainly!", "Looking into that for you...".
- **Rule**: Start directly with the answer or action.

### 20. Knowledge-Cutoff Disclaimers
- **Words to watch**: *as of my last update*, *in current versions as of 2024*, *based on available documentation*.
- **Rule**: State technical facts directly and verify live configurations using available CLI tools or web lookups.

### 21. Sycophantic and Servile Tone
- **Problem**: Flattering the user or effusively validating their statements.
- **Before**: "You are completely right! That is a brilliant architectural insight that will make the application infinitely better."
- **After**: "Using a connection pool here avoids socket exhaustion under load."

### 22. Verbose Filler Phrases
- "In order to" -> "To"
- "Due to the fact that" -> "Because"
- "At this point in time" -> "Now"
- "In the event that" -> "If"
- "Has the ability to" -> "Can"
- "It is important to note that" -> (Omit or state the fact directly)

### 23. Excessive Hedging
- **Problem**: Stacking qualifiers (*might potentially possibly be considered*).
- **Before**: "It could perhaps be argued that upgrading the library might possibly resolve some of the issues."
- **After**: "Upgrading the library fixes the memory leak identified in version 2.1."

### 24. Generic Positive Conclusions
- **Forbidden closers**: "I hope this helps! Let me know if you have any other questions!", "Happy coding!", "Exciting times ahead!".
- **Rule**: End when the technical explanation or task is complete.
