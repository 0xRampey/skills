# EMV Specification Lookup

You are answering an EMV-related question or performing a spec-related task. Use the EMV specifications folder as your primary reference.

## Specs Location
`~/Documents/emv-specs/`

## Available Specs & When to Use

### Contact (Chip) Specs
| Spec | File Pattern | Use For |
|------|--------------|---------|
| Book 1 | `EMV*Book_1*` | ICC-Terminal interface, ATR, APDU commands |
| Book 2 | `EMV*Book_2*` | Security, keys, CDA/DDA/SDA/XDA, certificates, ARQC/TC/AAC, ECC |
| Book 3 | `EMV*Book_3*` | Application flow, tags, DOL, transaction processing |
| Book 4 | `EMV*Book_4*` | Cardholder interfaces, receipts, display |

### Contactless Specs
| Spec | File Pattern | Use For |
|------|--------------|---------|
| Book A | `*Book-A*` | Architecture, general requirements |
| Book B | `*Book-B*` | Entry Point, AID selection, kernel activation |
| Book D | `D_EMV*` | RF communication protocol, collision detection |
| Book E | `Book_E*` | ECC security, P-256, XDA, algorithm suites |
| C-2 | `C-2*` | Mastercard contactless (PayPass/MCL) |
| C-3 | `C-3*` | Visa contactless (payWave/VCPS) |
| C-4 | `*C-4*` | Amex contactless (ExpressPay) |
| C-5 | `C-5*` | JCB contactless (J/Speedy) |
| C-6 | `C-6*` | Discover/Diners contactless (D-PAS) |
| C-7 | `C-7*` | UnionPay contactless (QuickPass) |
| C-8 | `C-8*` | Common Kernel 8, ECC/XDA native |

### Other Specs
| Spec | File Pattern | Use For |
|------|--------------|---------|
| Tokenisation | `*Tokenisation*` | Payment tokens, token requestor, de-tokenisation |
| QR Code | `*QR*` | Consumer-presented QR payments |
| SRC | `*SRC*` | Secure Remote Commerce API |
| Issuer Security | `*Issuer-Security*` | Issuer security guidelines |

## Instructions

1. **Search ALL specs** for the keyword:
   ```bash
   for f in ~/Documents/emv-specs/*.pdf; do echo "=== $f ==="; pdftotext "$f" - | grep -i -A 5 -B 2 "keyword" | head -50; done
   ```

2. **Search specific spec** when you know which one:
   ```bash
   pdftotext ~/Documents/emv-specs/Book_2*.pdf - | grep -i -A 10 -B 2 "keyword"
   ```

3. **For tag lookups**, search Book 3 first (contact) or C-8 (contactless):
   ```bash
   pdftotext ~/Documents/emv-specs/EMV*Book_3*.pdf - | grep -i -A 15 "9F27\|tag name"
   ```

4. **For ECC/XDA lookups**, search Book E (contactless security) and Book 2 (contact security):
   ```bash
   pdftotext ~/Documents/emv-specs/Book_E*.pdf - | grep -i -A 10 "XDA\|P-256\|EC-SDSA"
   ```

5. **When answering**:
   - Cite the specific spec document, section, and page when possible
   - Quote relevant passages directly
   - Note differences between contact vs contactless if applicable
   - Note scheme-specific differences (Visa vs MC vs Amex) if relevant

## User's Question
$ARGUMENTS
