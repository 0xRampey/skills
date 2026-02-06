# EMV Specification Lookup

You are answering an EMV-related question or performing a spec-related task. Use the EMV specifications folder as your primary reference.

## Specs Location
`~/Documents/emv-specs/`

## Available Specs & When to Use

| Spec | File Pattern | Use For |
|------|--------------|---------|
| Book 1 | `Book_1*` | ICC-Terminal interface, ATR, APDU commands |
| Book 2 | `Book_2*` | Security, keys, CDA/DDA/SDA, certificates, ARQC/TC/AAC |
| Book 3 | `Book_3*` | Application flow, tags, DOL, transaction processing |
| Book 4 | `Book_4*` | Cardholder interfaces, receipts, display |
| C-2 | `C-2*` | Mastercard contactless (PayPass) |
| C-3 | `C-3*` | Visa contactless (payWave) |
| C-4 | `C-4*` | Amex contactless (ExpressPay) |
| C-6 | `C-6*` | Discover/Diners contactless |
| C-7 | `C-7*` | UnionPay contactless (QuickPass) |
| C-8 | `C-8*` | Common kernel, general contactless |

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

4. **When answering**:
   - Cite the specific spec document, section, and page when possible
   - Quote relevant passages directly
   - Note differences between contact vs contactless if applicable
   - Note scheme-specific differences (Visa vs MC vs Amex) if relevant

## User's Question
$ARGUMENTS
