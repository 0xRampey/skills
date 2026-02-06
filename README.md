# Skills

A collection of custom Claude Code skills for domain-specific tasks.

## Skills

| Skill | Description |
|-------|-------------|
| `emv-lookup` | Look up EMV specifications (tags, cryptograms, CDA/DDA, terminal flows) |

---

## Setup

### 1. Copy skills to Claude commands folder

```bash
# Create commands folder if it doesn't exist
mkdir -p ~/.claude/commands

# Copy all skills
cp *.md ~/.claude/commands/
```

### 2. (Optional) Enable auto-activation

Add to your global Claude memory (`~/.claude/CLAUDE.md`):

```markdown
## EMV Knowledge Base
- When answering EMV-related questions (tags, cryptograms, CDA/DDA, AIDs, terminal flows, etc.), proactively use the `/emv-lookup` skill to reference specs at `~/Documents/emv-specs/`
- Cite specific spec documents and sections when possible
```

---

## Skill Requirements

### emv-lookup

**Requires EMV specs at:** `~/Documents/emv-specs/`

Download EMV specs from [EMVCo](https://www.emvco.com/emv-technologies/contact/) and place PDFs in the folder:

```
~/Documents/emv-specs/
├── EMV_v4.4_Book_1_ICC_to_Terminal_Interface.pdf
├── EMV_v4.4_Book_2_Security_and_Key_Management.pdf
├── EMV_v4.4_Book_3_Application_Specification.pdf
├── EMV_v4.4_Book_4_Other_Interfaces.pdf
├── C-2-Kernel-2-*.pdf   (Mastercard)
├── C-3-Kernel-3-*.pdf   (Visa)
├── C-4-Kernel-4-*.pdf   (Amex)
├── C-6-Kernel-6-*.pdf   (Discover)
├── C-7-Kernel-7-*.pdf   (UnionPay)
└── C-8-Kernel-8-*.pdf   (Common)
```

**Also requires:** `pdftotext` (from poppler)

```bash
# macOS
brew install poppler

# Ubuntu/Debian
sudo apt install poppler-utils
```

---

## Usage

```
/emv-lookup what is tag 9F27
/emv-lookup explain CDA flow
/emv-lookup difference between ARQC and TC
```
