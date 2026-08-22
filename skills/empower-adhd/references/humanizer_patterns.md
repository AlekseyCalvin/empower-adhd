# Reference: Humanizer AI Pattern Elimination

This guide catalogs common AI-generated writing artifacts and provides concrete techniques to ensure clear, grounded, and authentic prose.

---

## 1. High-Frequency AI Vocabulary

Avoid the predictable lexicon of synthetic text. Replace abstract, inflated terminology with precise, grounded verbs and nouns.

| AI Vocabulary Word | Problem | Concrete Alternative |
|---|---|---|
| **Pivotal / Key / Crucial** | Artificial inflation of significance | State the specific functional role directly |
| **Delve / Explore** | Formulaic exploration metaphor | "Analyze", "Examine", "Read", or state the action |
| **Testament / Reminder** | Metaphorical posturing | State verifiable historical or functional facts |
| **Tapestry / Landscape** | Vague spatial or artistic abstractions | "Architecture", "Domain", "Ecosystem", or name the system |
| **Underscore / Highlight** | Weak analytical filler | State the exact observation or conclusion |
| **Vibrant / Enduring / Rich** | Empty promotional adjectives | Provide concrete metrics, attributes, or details |
| **Fostering / Cultivating** | Vague constructive buzzwords | "Building", "Enabling", "Creating", "Developing" |
| **Seamless / Intuitive** | Unverified qualitative claims | Describe the specific mechanism or user flow |

---

## 2. Structural and Rhetorical Anti-Patterns

### 1. Superficial Participial Phrases (-ing Endings)
- **Problem**: Tacking on present participles (`ensuring...`, `highlighting...`, `reflecting...`) to fabricate analytical depth.
- **Before**: "We implemented caching, ensuring optimal performance and highlighting our commitment to reliability."
- **After**: "We implemented caching to reduce API response latency from 320ms to 45ms."

### 2. Copula Avoidance (Avoiding "is", "are", "has")
- **Problem**: Replacing simple verbs with inflated verbs (`serves as`, `stands as`, `marks a`, `boasts`).
- **Before**: "The module serves as the primary routing engine and boasts support for WebSocket connections."
- **After**: "The module routes traffic and supports WebSockets."

### 3. Negative Parallelisms
- **Problem**: Overusing rhetorical tropes like "Not only... but also..." or "It's not just about X, it's about Y."
- **Before**: "This library is not just a utility; it represents a new way of handling distributed transactions."
- **After**: "This library handles distributed transactions using two-phase commits."

### 4. Rule-of-Three Stuffing
- **Problem**: Forcing descriptions into arbitrary groups of three adjectives or nouns.
- **Before**: "The API is fast, flexible, and robust, providing clarity, speed, and precision."
- **After**: "The API provides sub-millisecond lookups and typed schema validation."

### 5. False Ranges
- **Problem**: Using "from X to Y" when X and Y do not share a meaningful continuum.
- **Before**: "We support everything from simple configuration files to enterprise-grade microservice clusters."
- **After**: "We support single-node deployments and Kubernetes clusters."

### 6. Inflated Symbolism and Promotional Hype
- **Problem**: Treating routine technical choices as monumental breakthroughs.
- **Before**: "The decision to migrate to TypeScript marks an enduring milestone in the project's evolution."
- **After**: "The project migrated to TypeScript to catch type errors at compile time."

---

## 3. Communication Artifacts and Filler

### 1. Conversational Preambles and Sycophancy
- **Cut immediately**:
  - "Great question!" / "Certainly!" / "Of course!"
  - "You're absolutely right."
  - "Let's dive into..." / "I'd be happy to help you with..."

### 2. Vague Attributions (Weasel Words)
- **Problem**: Citing phantom authorities (`industry experts agree`, `widely recognized as best practice`).
- **Correction**: Name the specific source, standard, RFC, or benchmark.

### 3. Formulaic Closers and Recaps
- **Cut immediately**:
  - "I hope this helps! Let me know if you need anything else."
  - "Feel free to reach out if you have further questions."
  - "In conclusion, by following these steps, you will achieve..."

---

## 4. Summary Transformation Table

| Category | AI-Flavored Draft | Humanized Technical Prose |
|---|---|---|
| **Architecture** | "The microservices architecture serves as a testament to scalable design, fostering seamless communication across disparate nodes." | "The microservices communicate over gRPC with protobuf serialization." |
| **Error Reporting** | "Unfortunately, an unexpected error occurred during execution, highlighting potential intricacies in the authentication flow." | "Auth failed: missing `Bearer` token in `Authorization` header at `client.go:88`." |
| **Performance** | "This optimization marks a crucial turning point, significantly enhancing processing throughput and revolutionizing data flow." | "Batching database writes increased throughput from 1,200 to 8,500 records/sec." |
