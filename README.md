# 🛡️ Password Strength Analyzer

A free, client-side password strength analyzer that calculates real entropy and estimates crack times against modern hardware.

**[Try it live →](https://maxmini0214.github.io/password-strength-analyzer/)**

## Why?

Most password meters just check "has uppercase + special character = strong!" — that tells you nothing about actual security. This tool calculates **real entropy** based on the character classes you use, then estimates how long it would take to crack with different hardware setups.

## How It Works

### Entropy Calculation
- Detects character classes: lowercase, uppercase, digits, symbols, extended unicode
- `entropy = log2(charset_size ^ length)`
- Accounts for effective keyspace, not just length

### Crack Time Estimates
| Scenario | Speed |
|----------|-------|
| Single GPU | ~10B hashes/sec (SHA-256) |
| 8-GPU Rig | ~80B hashes/sec |
| Botnet (theoretical) | ~1T hashes/sec |
| Bcrypt (conservative) | ~10K hashes/sec |

### Pattern Detection
- Common substitutions (`@` → `a`, `3` → `e`, etc.)
- Sequential characters
- Repeated patterns

## Privacy

- **100% client-side** — zero network requests after page load
- No analytics, no tracking, no cookies
- Verify yourself: open DevTools → Network tab → type a password → zero requests

## Tech

Single HTML file. No build step. No dependencies. Just open `index.html`.

## License

MIT
