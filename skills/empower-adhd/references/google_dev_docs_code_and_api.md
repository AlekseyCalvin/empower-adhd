# Google Developer Documentation Style Guide: Code, CLI, and API Reference

This reference document compiles the comprehensive standards from the Google Developer Documentation Style Guide for formatting code in text, code samples, CLI commands, placeholders, and API reference comments.

---

## 1. Code in Text

Use inline code font (`backticks`) for anything that represents code, configuration syntax, file system entities, or CLI commands.

### When to Use Code Font
- **File names and extensions**: `package.json`, `main.py`, `.env`, `.yaml`, `.proto`.
- **Directory paths**: `/usr/local/bin`, `src/components/`, `~/.config/app/`.
- **Function and method names**: `getUserById()`, `JSON.stringify()`, `calculateHash()`. Include empty parentheses `()` when referring to functions/methods unless referring strictly to a function pointer or identifier.
- **Variables, constants, and properties**: `userId`, `MAX_RETRIES`, `request.headers`, `payload.items`.
- **Classes, interfaces, and types**: `AuthService`, `UserRecord`, `string`, `boolean`, `int64`, `Map<String, Object>`.
- **CLI commands, utilities, and flags**: `git commit`, `npm install`, `--verbose`, `-rf`, `kubectl apply`.
- **HTTP methods and status codes**: `GET`, `POST`, `PUT`, `DELETE`, `200 OK`, `404 Not Found`, `500 Internal Server Error`.
- **Configuration parameters and keys**: `max_connections`, `timeout_ms`, `allow_origins`.
- **Database entities**: Tables, schemas, and columns (e.g., `users` table, `created_at` column, `SELECT` queries).
- **Placeholders in inline text**: `PROJECT_ID`, `USER_TOKEN`.

### When NOT to Use Code Font
- **Product and tool names**: Write standard software names in regular text (e.g., Docker, Kubernetes, PostgreSQL, Git, npm, Node.js). Code font is only for the literal CLI executable command (e.g., "Use Docker to build your container by running `docker build`.").
- **Protocol names**: HTTP, HTTPS, TCP, UDP, gRPC, WebSocket (use standard uppercase without backticks).
- **File format names**: JSON, YAML, XML, CSV, PDF (use uppercase standard text when referring to the format concept).

---

## 2. Code Samples and Code Blocks

### Syntax Highlighting and Language Identifiers
Always specify the language tag immediately after the opening triple backticks (e.g., ` ```typescript `, ` ```bash `, ` ```json `, ` ```python `).

### Guidelines for Writing Code Samples
1. **Provide runnable, realistic code**: Avoid placeholder nonsense (`foo`, `bar`, `baz`, `asdf`). Use domain-relevant names (`customerEmail`, `orderTotal`, `paymentGateway`).
2. **Include necessary imports and dependencies**: Ensure the code sample shows required import statements or specifies prerequisites so the developer can execute it directly.
3. **Use standard ellipses for omitted code**: When omitting non-essential lines in an example, use a comment with three dots (`// ...` or `# ...`).
4. **Annotate complex logic with concise comments**: Add comments above complex lines, not inline at the end of the line, to prevent horizontal scrollbars.
5. **Adhere to standard language conventions**:
   - TypeScript/JavaScript: Standard casing, explicit types where helpful, modern ES syntax (`const`/`let`, async/await).
   - Python: PEP 8 compliant, type annotations, descriptive docstrings.
   - Go: `gofmt` compliant, explicit error checking (`if err != nil`).
   - Rust: Idiomatic error handling with `Result` and `Option`.

### Example Code Sample

```typescript
import { DatabaseClient, UserRecord } from '@example/database';

/**
 * Retrieves an active user record by ID.
 * Throws an error if the user is suspended or not found.
 */
export async function getActiveUser(
  client: DatabaseClient,
  userId: string
): Promise<UserRecord> {
  const user = await client.users.findUnique({
    where: { id: userId },
  });

  if (!user) {
    throw new Error(`User not found: ${userId}`);
  }

  if (user.status !== 'ACTIVE') {
    throw new Error(`User account is inactive: ${userId}`);
  }

  return user;
}
```

---

## 3. Placeholders in Commands and Code

Placeholders represent variable data that the developer must replace with specific values (such as API keys, project names, or paths).

### Placeholder Formatting Conventions
- **Uppercase snake case**: Format placeholders in all uppercase letters, using underscores between words (e.g., `PROJECT_ID`, `YOUR_API_KEY`, `INSTANCE_NAME`).
- **Clear, descriptive tokens**: Use tokens that immediately identify the required input (`DATABASE_URL`, `REGION`, `TARGET_BRANCH`).
- **Immediate definition**: Always define all placeholders used in a code or command block immediately beneath the block using a structured bulleted list.

### Placeholder Example

```bash
gcloud compute instances create INSTANCE_NAME \
    --project=PROJECT_ID \
    --zone=ZONE \
    --machine-type=MACHINE_TYPE
```

Replace the following:
- `INSTANCE_NAME`: A unique name for your virtual machine instance.
- `PROJECT_ID`: Your Google Cloud project ID.
- `ZONE`: The deployment zone (for example, `us-central1-a`).
- `MACHINE_TYPE`: The machine type specification (for example, `e2-standard-4`).

---

## 4. CLI Commands and Console Output

### Structuring Terminal Interactions
1. **Separate input commands from output**: Do not mix user input commands and system output in a single code block unless explicitly showing an interactive REPL dialogue.
2. **Omit leading shell prompts (`$`)**: For single-line and copyable CLI commands, omit the leading `$` prompt so developers can copy and paste the command directly with one click.
3. **Multi-line commands**: Use backslashes (`\`) for line continuation in bash commands to keep long commands readable without horizontal scrolling. Indent continuation lines by 4 spaces.
4. **Command output blocks**: Format command outputs in a separate plain code block labeled with `console`, `output`, or `text`.

### Example Command and Output Separation

```bash
docker run -d \
    --name redis-cache \
    -p 6379:6379 \
    -v redis-data:/data \
    redis:7-alpine
```

The terminal output displays the running container ID:

```output
a1b2c3d4e5f67890abcdef1234567890abcdef1234567890abcdef1234567890
```

---

## 5. API Reference Comments and Documentation

### General Standards
- Write concise, complete sentences.
- Begin the summary sentence with an active, third-person singular verb (e.g., "Calculates the checksum...", "Initializes a new database pool...") or an imperative verb ("Calculate the checksum..."), maintaining consistency across the codebase.
- Document parameter types, required/optional status, default values, and valid ranges.
- Document all possible return values and explicitly describe error conditions and thrown exceptions.

### API Comment Templates

#### TypeScript / JSDoc / TSDoc
```typescript
/**
 * Verifies a JSON Web Token (JWT) against the configured public key.
 *
 * @param token - The raw bearer token string extracted from the authorization header.
 * @param options - Verification configuration parameters.
 * @param options.maxAgeSeconds - Maximum allowed token age in seconds. Defaults to 3600.
 * @returns The decoded token payload containing user claims.
 * @throws {TokenExpiredError} If the token timestamp exceeds the expiration threshold.
 * @throws {JsonWebTokenError} If the token signature is invalid or malformed.
 */
export function verifyToken(token: string, options?: VerifyOptions): TokenPayload {
  // ...
}
```

#### Python Docstrings (Google Style)
```python
def fetch_telemetry_batch(
    client: TelemetryClient,
    device_id: str,
    limit: int = 100
) -> list[TelemetryRecord]:
    """Fetches a batch of telemetry records for a specified device.

    Args:
        client: An authenticated TelemetryClient instance.
        device_id: The unique string identifier of the target edge device.
        limit: The maximum number of telemetry records to return. Defaults to 100.
            Must be an integer between 1 and 1000.

    Returns:
        A list of TelemetryRecord instances sorted chronologically ascending.

    Raises:
        DeviceNotFoundError: If the specified device_id does not exist.
        ConnectionTimeoutError: If the remote telemetry endpoint fails to respond
            within the configured deadline.
    """
```

---

## 6. Filenames, File Paths, and Artifact Naming

- **Lowercase and hyphens for repository documentation**: Use `kebab-case` for documentation filenames (e.g., `getting-started.md`, `api-overview.md`).
- **Code file naming conventions**:
  - TypeScript/JavaScript: `camelCase.ts` or `kebab-case.ts` for utilities; `PascalCase.tsx` for React components.
  - Python: `snake_case.py` for modules and packages.
  - Go: `snake_case.go` for all files.
- **Always specify file extensions**: Always include the file extension when mentioning files in text (e.g., `schema.prisma`, `docker-compose.yaml`, `Cargo.toml`).
