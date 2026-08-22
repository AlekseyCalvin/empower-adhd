# Google Developer Documentation Style Guide: Word List and Jargon Replacements

This reference document compiles standard developer terminology, approved word usages, spelling and capitalization conventions, and jargon replacements from the Google Developer Documentation Style Guide.

---

## 1. Developer Terminology and Usage Guide

| Term | Recommended Usage | Rules, Context, and Notes |
|---|---|---|
| **abort / cancel / terminate** | Use precisely | Use *abort* to stop a process before completion due to an error. Use *cancel* when a user intentionally stops an ongoing operation. Use *terminate* when a process or connection is closed normally or forcefully. |
| **allow / enable / let** | Use precisely | Use *let* when software or features give the user the ability to do something (e.g., "The CLI lets you deploy..."). Use *allow* or *enable* for permissions, security policies, and flags (e.g., "IAM roles allow access to resources."). |
| **allowlist / denylist** | Use instead of whitelist / blacklist | Do not use *whitelist* or *blacklist*. Use *allowlist* and *denylist* for security access filters. |
| **app** | Acceptable for applications | *App* is acceptable for mobile applications, web applications, and Slack/GitHub apps. Use *application* when referring to formal enterprise software systems. |
| **backend / back end / back-end** | Noun: *back end*, Adjective: *back-end* | Use *back end* as a noun ("The service connects to the back end."). Use *back-end* as an adjective ("Configure the back-end service."). Avoid *backend* as a single word in formal documentation unless part of code syntax. |
| **can / may / might** | Use precisely | Use *can* to express capability or possibility ("You can export the data."). Use *may* for formal permission ("Administrators may grant access."). Use *might* for conditional possibility ("Latency might increase under heavy load."). |
| **cloud / Cloud** | Lowercase general, Capitalize product | Use lowercase *cloud* for general cloud computing ("deployed to the cloud"). Capitalize only when part of a proper product name (e.g., "Google Cloud", "Cloud Storage"). |
| **codebase** | One word | Write *codebase* as a single word without a space or hyphen. |
| **data center / datacenter** | Two words | Write *data center* as two separate words. |
| **data set / dataset** | Two words in text | Write *dataset* when referring to specific database entities (like BigQuery datasets); write *data set* when referring to generic collections of data. |
| **dataclass** | One word (Python) | Write *dataclass* when referring to Python dataclasses. |
| **deprecated / obsolete** | Use precisely | Use *deprecated* for features that are still functional but scheduled for removal in future versions. Use *obsolete* or *removed* for features that are no longer available or supported. |
| **e.g. / i.e. / such as** | Use plain English | Avoid Latin abbreviations in prose. Replace *e.g.,* with *for example,* or *such as*. Replace *i.e.,* with *that is,* or *specifically*. |
| **filesystem / file system** | Two words | Write *file system* as two words in running text, unless referring to a specific code identifier (e.g., `fs` module). |
| **frontend / front end / front-end** | Noun: *front end*, Adjective: *front-end* | Use *front end* as a noun ("deployed to the front end"). Use *front-end* as an adjective ("a front-end client"). |
| **hostname** | One word | Write *hostname* as one word. |
| **ID / id** | Uppercase in text, lowercase in code | Write *ID* (all uppercase) in prose documentation. Use `id` or `userId` in code font when referencing specific code properties. |
| **lifecycle** | One word | Write *lifecycle* as a single word. |
| **log in / login / logged-in** | Verb: *log in*, Noun: *login* | Use *log in* as a verb phrase ("To view your account, log in with your credentials."). Use *login* as a noun or adjective ("Enter your login credentials.", "Go to the login page."). |
| **look up / lookup** | Verb: *look up*, Noun: *lookup* | Use *look up* as a verb phrase ("Look up the DNS record."). Use *lookup* as a noun or adjective ("Perform a DNS lookup."). |
| **metadata** | One word | Write *metadata* as a single word. Plural is also *metadata*. |
| **microservice / microservices** | One word | Write *microservice* as a single word without a hyphen. |
| **nonblocking** | One word | Write *nonblocking* as a single word without a hyphen. |
| **offline / online** | One word | Write *offline* and *online* as single words without hyphens. |
| **open source / open-source** | Noun: *open source*, Adj: *open-source* | Use *open source* as a noun ("contribute to open source"). Use *open-source* as an adjective preceding a noun ("an open-source project"). |
| **passphrase / password** | One word | Write *passphrase* and *password* as single words. |
| **plug-in / plugin** | Use *plugin* | Write *plugin* as a single word without a hyphen for software extensions. |
| **primary / replica** | Use instead of master / slave | Do not use *master* and *slave*. Use *primary* and *replica*, *leader* and *follower*, or *main* and *worker*. |
| **read-only / write-only** | Hyphenated adjective | Always hyphenate *read-only* and *write-only* when describing permissions or file attributes. |
| **real time / real-time** | Noun: *real time*, Adj: *real-time* | Use *real time* as a noun phrase ("processes data in real time"). Use *real-time* as an adjective ("a real-time streaming pipeline"). |
| **repository / repo** | Formal: *repository*, Informal: *repo* | Use *repository* in formal technical guides; *repo* is acceptable in developer-to-developer conversational technical collaboration. |
| **runtime** | One word | Write *runtime* as a single word (e.g., "Node.js runtime", "runtime environment"). |
| **schema / schemas** | Plural: *schemas* | Use *schemas* as the plural form in developer documentation, not *schemata*. |
| **set up / setup** | Verb: *set up*, Noun: *setup* | Use *set up* as a verb phrase ("Set up your development environment."). Use *setup* as a noun or adjective ("The setup script configures dependencies."). |
| **shut down / shutdown** | Verb: *shut down*, Noun: *shutdown* | Use *shut down* as a verb phrase ("Shut down the virtual machine."). Use *shutdown* as a noun or adjective ("Execute a graceful shutdown."). |
| **sync / synchronize** | Both acceptable | Use *sync* in developer-facing instructions ("Sync the database changes."); *synchronize* is acceptable in formal architectural specs. |
| **that / which** | Use precisely | Use *that* for restrictive clauses essential to meaning ("The container that hosts the API restarted."). Use *which* preceded by a comma for non-restrictive parenthetical clauses ("The container, which was built yesterday, restarted."). |
| **third party / third-party** | Noun: *third party*, Adj: *third-party* | Use *third party* as a noun ("a library developed by a third party"). Use *third-party* as an adjective ("third-party integrations"). |
| **time frame** | Two words | Write *time frame* as two separate words. |
| **timeout** | Noun/Adj: *timeout*, Verb: *time out* | Use *timeout* as a noun ("Configure a 30-second timeout."). Use *time out* as a verb phrase ("The connection will time out."). |
| **timestamp** | One word | Write *timestamp* as a single word. |
| **user ID / username** | *user ID*, *username* | Write *user ID* as two words with uppercase *ID*. Write *username* as a single lowercase word. |
| **web page / website** | *web page*, *website* | Write *web page* as two words. Write *website* as one word. |
| **workaround** | One word | Write *workaround* as a single word for temporary solutions. |
| **zero-downtime** | Hyphenated adjective | Hyphenate when preceding a noun (e.g., "zero-downtime deployment"). |

---

## 2. Jargon and Buzzword Replacements

Replace vague, violent, exclusionary, or colloquial jargon with precise, universally understood technical terms.

| Jargon / Buzzword | Why Avoid | Recommended Precise Alternative |
|---|---|---|
| **Blast radius** | Violent metaphor, unclear meaning | *Spatial impact*, *affected area*, *scope of impact* |
| **Ingest / Ingestion** | Biological metaphor, overly corporate | *Import*, *load*, *process*, *collect*, *receive* |
| **Out-of-the-box** | Marketing cliché, idiom | *Built-in*, *pre-configured*, *default*, *standard* |
| **Spin up / Spin down** | Hardware-era metaphor (spinning disks) | *Create*, *launch*, *start*, *provision*, *terminate*, *delete* |
| **Kill / Nuke** | Violent jargon | *Terminate*, *stop*, *cancel*, *force-quit*, *delete* |
| **Triage** | Medical emergency metaphor | *Review*, *prioritize*, *categorize*, *assess* |
| **Sanity check / Smoke test** | Ableist language / colloquialism | *Preliminary check*, *basic validation*, *smoke test* |
| **White-box / Black-box** | Vague, racially loaded metaphor | *Internal-structure / opaque*, *transparent / behavioral* |
| **Dogfood / Dogfooding** | Colloquial corporate slang | *Internal testing*, *pre-release evaluation* |
| **Bake time** | Kitchen metaphor | *Soak period*, *monitoring window*, *evaluation duration* |
| **Off-the-shelf** | Retail idiom | *Commercial*, *standard*, *pre-built*, *packaged* |
| **Post-mortem** | Medical/coroner metaphor | *Retrospective*, *incident review*, *post-incident analysis* |
| **Shift left** | Abstract industry buzzword | *Test earlier in development*, *early automated validation* |
| **Dead letter queue** | Standard term (if used, define) | *Dead-letter queue* (define on first use as unprocessable message storage) |
| **Cold standby / Hot standby** | Define clearly | Define on first use (e.g., "a standby replica maintained in continuous sync") |
| **Easy / Simple / Just / Simply** | Condescending in technical guides | Omit completely. State the concrete step directly without editorializing on difficulty. |
