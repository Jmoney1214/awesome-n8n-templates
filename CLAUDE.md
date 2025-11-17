# CLAUDE.md - AI Assistant Guide for awesome-n8n-templates

## Repository Overview

This is a **community-curated collection of n8n automation templates** focusing heavily on AI/LLM integrations. The repository contains **286+ workflow templates** organized into 18 thematic categories, serving as a resource library for n8n users worldwide.

**Key Characteristics:**
- **Content Source:** Templates sourced from the internet and n8n community (not original creations)
- **Primary Focus:** AI-powered automation workflows using OpenAI, Claude, Gemini, and other LLMs
- **Audience:** International (English and Chinese documentation)
- **Purpose:** Easy access and sharing of production-ready n8n workflow templates

**Important:** All templates are provided "as-is" from community sources. The repository maintainer assumes no responsibility for issues arising from template usage.

---

## Repository Structure

### Directory Organization

```
awesome-n8n-templates/
├── .github/
│   ├── workflows/
│   │   └── validate-workflows.yml    # CI/CD validation workflow
│   └── FUNDING.yml                    # GitHub Sponsors configuration
├── AI_Research_RAG_and_Data_Analysis/ # 40 workflows
├── Airtable/                          # 5 workflows
├── Database_and_Storage/              # 5 workflows
├── Discord/                           # 3 workflows
├── Forms_and_Surveys/                 # 3 workflows
├── Gmail_and_Email_Automation/        # 21 workflows
├── Google_Drive_and_Google_Sheets/    # 13 workflows
├── HR_and_Recruitment/                # 8 workflows
├── Instagram_Twitter_Social_Media/    # 10 workflows
├── Notion/                            # 10 workflows
├── OpenAI_and_LLMs/                   # 81 workflows (largest category)
├── Other/                             # Reference files
├── Other_Integrations_and_Use_Cases/  # 30 workflows
├── PDF_and_Document_Processing/       # 11 workflows
├── Slack/                             # 9 workflows
├── Telegram/                          # 20 workflows
├── WhatsApp/                          # 4 workflows
├── WordPress/                         # 6 workflows
├── img/                               # Images (n8n logo)
├── AI product imagines.json           # Root-level workflow
├── README.md                          # English documentation (66KB)
├── README-zh.md                       # Chinese documentation (59KB)
└── CLAUDE.md                          # This file
```

### Category Definitions

| Category | Purpose | Common Use Cases |
|----------|---------|------------------|
| **Gmail_and_Email_Automation** | Email processing and automation | Auto-labeling, draft generation, suspicious email analysis, support automation |
| **Telegram** | Telegram bot implementations | AI chatbots, voice/text/image processing, multi-modal agents |
| **OpenAI_and_LLMs** | General AI/LLM applications | AI agents, sentiment analysis, data extraction, chatbots |
| **AI_Research_RAG_and_Data_Analysis** | Advanced AI workflows | RAG systems, research automation, vector databases, semantic search |
| **Google_Drive_and_Google_Sheets** | Google Workspace automation | Document summarization, spreadsheet AI, file processing |
| **Notion** | Notion database integration | Knowledge base assistants, vector storage, content management |
| **Slack** | Slack bot and notification workflows | AI support bots, alert systems, integration hubs |
| **PDF_and_Document_Processing** | Document analysis and extraction | PDF parsing, OCR, resume screening, data extraction |
| **WordPress** | WordPress content automation | Auto-categorization, AI-powered content generation, chatbots |
| **Database_and_Storage** | Database integrations | SQL/NoSQL agents, vector databases, data queries |
| **Airtable** | Airtable automation | AI data analysis, project management, form processing |
| **Discord** | Discord bot workflows | Community management, content distribution, AI moderation |
| **Forms_and_Surveys** | n8n form integrations | Conversational forms, AI-enhanced data collection |
| **HR_and_Recruitment** | Human resources automation | CV screening, applicant tracking, interview automation |
| **Instagram_Twitter_Social_Media** | Social media automation | Content generation, posting automation, analytics |
| **WhatsApp** | WhatsApp business automation | AI chatbots, customer service, RAG implementations |
| **Other_Integrations_and_Use_Cases** | Miscellaneous integrations | Various specialized workflows |

---

## Workflow File Patterns

### Standard n8n Workflow JSON Structure

Every workflow template is a JSON file following the n8n workflow schema:

```json
{
  "name": "Workflow Display Name",
  "nodes": [
    {
      "id": "unique-uuid-v4",
      "name": "Node Display Name",
      "type": "n8n-nodes-base.nodeName",
      "position": [x, y],
      "parameters": { /* configuration */ },
      "credentials": { /* credential references */ },
      "typeVersion": 1.0
    }
  ],
  "connections": {
    "Node Name": {
      "main": [[{ "node": "Target Node", "type": "main", "index": 0 }]]
    }
  },
  "pinData": {},
  "active": false,
  "settings": {},
  "versionId": "optional-uuid",
  "meta": { /* metadata */ },
  "tags": []
}
```

### Common Node Types

**Triggers:**
- `gmailTrigger` - Monitor Gmail inbox
- `telegramTrigger` - Listen for Telegram messages
- `chatTrigger` - Chat interface trigger
- `manualTrigger` - Manual execution
- `webhookTrigger` - Webhook endpoints

**AI/LLM Nodes:**
- `lmChatOpenAi` - OpenAI language models
- `lmChatAnthropic` - Anthropic Claude models
- `lmChatGoogleGemini` - Google Gemini models
- `chainLlm` - LangChain LLM chains
- `agent` - LangChain AI agents
- `memoryBufferWindow` - Conversation memory

**Data Processing:**
- `set` - Set/transform data
- `code` - Custom JavaScript/Python code
- `merge` - Merge data streams
- `splitOut` - Split arrays into items
- `aggregate` - Aggregate items

**Integrations:**
- `gmail`, `telegram`, `notion`, `googleDrive`, `airtable`, `slack`, `discord`, `wordpress`
- Platform-specific nodes for various services

**Utilities:**
- `stickyNote` - Documentation within workflows
- `httpRequest` - HTTP API calls
- `switch` - Conditional routing
- `if` - Boolean conditions

### Connection Types

Workflows use multiple connection types:
- **main**: Standard data flow connections
- **ai_languageModel**: LLM model connections to AI nodes
- **ai_outputParser**: Structured output parsers
- **ai_tool**: Tool connections for AI agents
- **ai_memory**: Memory connections for stateful conversations

---

## Naming Conventions

### Workflow Filenames

**Format:** `Descriptive Title with Spaces and Punctuation.json`

**Rules:**
- Use natural language descriptions matching README entries
- Spaces are allowed and preferred
- Punctuation marks included (`:`, `&`, `-`, `_`, `!`, `?`)
- Emojis are acceptable (e.g., `🤖`, `📈`, `⚡`)
- Special emphasis using underscores (e.g., `_Human in the Loop_`)
- No strict character limits (some filenames are 80+ characters)

**Examples:**
```
✓ Auto-label incoming Gmail messages with AI nodes.json
✓ AI-Powered Email Automation for Business_ Summarize & Respond with RAG.json
✓ 🤖 Telegram Messaging Agent for Text_Audio_Images.json
✓ Chat with PDF docs using AI (quoting sources).json
```

### Internal Node Naming

**Best Practices:**
- Use descriptive display names (e.g., "Gmail trigger", "AI Classification (OpenAI)")
- Include service/tool name in parentheses when helpful
- Use sticky notes for documentation blocks
- Credential references should be descriptive

---

## Development Workflows

### Adding New Templates

When adding new workflow templates:

1. **Categorization:**
   - Place workflow in the most appropriate category folder
   - If no category fits, use `Other_Integrations_and_Use_Cases/`
   - Consider creating new category if adding 3+ related workflows

2. **File Naming:**
   - Use descriptive, natural language filename
   - Match the title you'll use in README
   - Include key technologies/platforms in name

3. **README Updates:**
   - Add entry to appropriate category table in both `README.md` and `README-zh.md`
   - Include: Title, Description, Department, Link (relative path)
   - Maintain alphabetical or logical ordering within category

4. **Workflow Preparation:**
   - Remove sensitive credentials
   - Clear any pinned test data (`pinData` should be `{}`)
   - Set `active: false`
   - Add sticky notes for complex logic explanations
   - Test workflow imports correctly

5. **Documentation (Optional but Recommended):**
   - For complex workflows, consider adding a dedicated setup guide
   - Follow pattern from `LEGACY_WINE_LIQUOR_SETUP_GUIDE.md`
   - Include: Prerequisites, Installation Steps, Configuration, Troubleshooting

### README Table Format

```markdown
| Title | Description | Department | Link |
|-------|-------------|------------|------|
| Workflow Name | Brief description of what it does and key technologies used. | Primary Department | [Link to Template](Category_Folder/Workflow%20Name.json) |
```

**Department Options:**
Support, Marketing, Sales, Engineering, Operations, HR, Security, Finance, IT, Development, Content, Executive, QA, Analytics, etc.

### CI/CD Validation

The repository uses GitHub Actions for validation:

**Workflow:** `.github/workflows/validate-workflows.yml`

**Validation Steps:**
1. All JSON files are validated for syntax
2. Workflow structure verified
3. Visualization PNGs generated (artifacts)
4. Results commented on PRs

**Note:** Current CI/CD references `./lib/requirements.txt` which doesn't exist. This may need fixing if CI/CD is actively used.

---

## Git Workflow & Branching

### Branch Naming Convention

**For Claude/AI-assisted development:**
```
claude/<description>-<session-id>
```

**Current working branch:**
```
claude/claude-md-mi2xu3q4xrymuv71-01CpaKRPvef6kGjKDZqRtvk8
```

### Git Operations Best Practices

**Push Operations:**
- Always use: `git push -u origin <branch-name>`
- Branch must start with `claude/` and include session ID
- Retry up to 4 times with exponential backoff on network errors (2s, 4s, 8s, 16s)

**Fetch/Pull Operations:**
- Prefer specific branches: `git fetch origin <branch-name>`
- Use: `git pull origin <branch-name>`
- Apply same retry logic for network failures

**Commit Messages:**
- Use descriptive, action-oriented messages
- Format: `Add <workflow-name> workflow` or `Update README with <changes>`
- Examples:
  - `Add Legacy Wine & Liquor AI-Powered Support Email Automation workflow`
  - `Update README with new Gmail automation templates`

### Pull Request Process

When creating PRs:
1. Ensure all workflows validate successfully
2. Verify README updates are complete and correct
3. Check both English and Chinese READMEs are updated
4. Review relative file paths work correctly
5. Wait for CI/CD validation results

---

## Common AI Assistant Tasks

### Task 1: Adding a New Workflow Template

**Steps:**
1. Save workflow JSON file to appropriate category folder
2. Update `README.md` with new table entry
3. Update `README-zh.md` with Chinese translation
4. Verify file path in README matches actual location
5. Commit with message: `Add <workflow-name> workflow`
6. Push to claude/* branch

**Example:**
```bash
# After adding workflow file
git add "Gmail_and_Email_Automation/New Workflow.json"
git add README.md README-zh.md
git commit -m "Add New Workflow for Gmail automation"
git push -u origin claude/add-gmail-workflow-<session-id>
```

### Task 2: Creating a New Category

**When to create:**
- Adding 3+ workflows in a new domain/platform
- Existing categories don't fit the use case
- Clear thematic grouping exists

**Steps:**
1. Create new directory: `New_Category_Name/`
2. Add workflows to directory
3. Update README with new category section and table
4. Update README-zh.md with Chinese version
5. Update this CLAUDE.md with category definition

### Task 3: Updating Existing Workflows

**Best Practices:**
- Don't modify workflows unless fixing clear errors
- Document changes in commit message
- Update README description if functionality changes
- Consider versioning (e.g., "V2" suffix) for major updates

### Task 4: Documentation Improvements

**README Updates:**
- Keep tables well-formatted and aligned
- Ensure relative links work (test locally if possible)
- Maintain consistency between English and Chinese versions
- Update category counts if adding many workflows

**Setup Guides:**
- Create for complex workflows with multiple prerequisites
- Include: Overview, Prerequisites, Installation, Configuration, Testing, Troubleshooting
- Use markdown formatting for readability

---

## Key Technical Patterns

### Common Workflow Architectures

**1. Email Automation Pattern:**
```
Email Trigger → Extract Content → AI Classification →
  ├─ Apply Label/Category
  ├─ Generate Response Draft
  └─ Send Notification
```

**2. Chat Bot Pattern:**
```
Message Trigger → Load Context/Memory →
  AI Agent (with tools) → Format Response →
  Send Reply + Update Memory
```

**3. RAG (Retrieval-Augmented Generation) Pattern:**
```
Query Input → Embed Query →
  Vector Search (Pinecone/Qdrant/Supabase) →
  Retrieve Context → LLM with Context →
  Formatted Response
```

**4. Document Processing Pattern:**
```
Document Trigger → Extract Text →
  Chunk/Split → Embed →
  Store in Vector DB
```

**5. Content Generation Pattern:**
```
Schedule/Trigger → Gather Context →
  AI Generation (with brand voice/rules) →
  Format → Post/Publish
```

### LangChain Integration Patterns

Most AI workflows use LangChain nodes:
- **Agents:** Use `@n8n/n8n-nodes-langchain.agent` with tools
- **Memory:** `@n8n/n8n-nodes-langchain.memoryBufferWindow` for conversations
- **Output Parsers:** `@n8n/n8n-nodes-langchain.outputParserStructured` for JSON
- **Tools:** `@n8n/n8n-nodes-langchain.toolHttpRequest`, custom tools

### Credential Management

**Important:**
- All workflows reference credentials, not actual keys
- Users must configure their own credentials in n8n
- Credential names are descriptive (e.g., "OpenAI API", "Gmail OAuth2")
- Never commit actual API keys or secrets

---

## Quality Standards

### Workflow Quality Checklist

Before adding a workflow template:
- [ ] Valid JSON syntax
- [ ] Imports successfully into n8n
- [ ] No pinned test data (pinData is empty)
- [ ] Workflow is set to inactive (active: false)
- [ ] Credentials removed/referenced only
- [ ] Sticky notes explain complex logic
- [ ] Descriptive node names
- [ ] README entry added (English + Chinese)
- [ ] Category is appropriate
- [ ] Filename follows conventions

### Documentation Quality

README entries should include:
- Clear, concise description
- Key technologies/services mentioned
- Primary use case
- Appropriate department tag
- Working relative file path

---

## Troubleshooting

### Common Issues

**1. Workflow doesn't import:**
- Check JSON syntax validity
- Verify all required node types exist in target n8n version
- Check for custom nodes that need installation

**2. Missing credentials errors:**
- Expected behavior - users must configure their own
- Document required credentials in workflow description or setup guide

**3. CI/CD validation fails:**
- Check JSON syntax
- Verify file is in correct directory
- Ensure README links match file paths

**4. README tables broken:**
- Verify pipe (`|`) alignment
- Check for unescaped special characters
- Ensure URLs are properly encoded

### File Path Encoding

When referencing workflows with special characters:
- Spaces → `%20`
- `&` → `%26`
- Chinese characters → URL encoded

Example:
```markdown
[Link](Gmail_and_Email_Automation/Auto-label%20incoming%20Gmail%20messages%20with%20AI%20nodes.json)
```

---

## Multilingual Support

### Language Files

- **English:** `README.md` (primary)
- **Chinese:** `README-zh.md` (translation)

### Translation Guidelines

When updating documentation:
1. Make changes to English version first
2. Update Chinese version with equivalent content
3. Maintain table structure and formatting
4. Translate descriptions, keep technical terms in English
5. Keep workflow filenames in English (no translation)

---

## External References

### Important Links

- **n8n Official:** https://n8n.io
- **n8n Workflows:** https://n8n.io/workflows/
- **Repository Sponsor:** https://buymeacoffee.com/enescingoz
- **GitHub Sponsor:** https://github.com/sponsors/enescingoz

### Related Documentation

- **n8n Documentation:** https://docs.n8n.io
- **LangChain Nodes:** https://docs.n8n.io/integrations/builtin/cluster-nodes/root-nodes/n8n-nodes-langchain/
- **Community Forum:** https://community.n8n.io

---

## Best Practices for AI Assistants

### When Adding Workflows

1. **Always verify category fit** - Don't create new categories unnecessarily
2. **Maintain both READMEs** - English and Chinese must stay in sync
3. **Test file paths** - Ensure relative links work correctly
4. **Use descriptive names** - Filenames should clearly indicate purpose
5. **Include department tags** - Helps users find relevant workflows
6. **Document complex workflows** - Add setup guides for multi-step configurations

### When Modifying Repository

1. **Preserve existing structure** - Don't reorganize without discussion
2. **Update all references** - README, file paths, documentation
3. **Commit atomically** - One logical change per commit
4. **Write clear commit messages** - Describe what and why
5. **Respect attribution** - Templates are from community sources

### When Assisting Users

1. **Understand context** - Is this for personal use or contribution?
2. **Explain credential requirements** - Users must provide their own API keys
3. **Suggest appropriate categories** - Help organize contributions
4. **Encourage documentation** - Setup guides help the community
5. **Test before committing** - Validate JSON and README changes

---

## Version Information

**Last Updated:** 2025-11-17
**Total Workflows:** 286+
**Categories:** 18
**Languages:** English, Chinese

---

## Maintainer Notes

**Repository Owner:** enescingoz
**Content Source:** Community-sourced templates from internet
**License:** Not specified (review individual workflows for licensing)
**Disclaimer:** Templates provided as-is without warranty

For questions, issues, or contributions, refer to the repository's GitHub Issues and Pull Requests.

---

*This CLAUDE.md file is designed to help AI assistants understand and work effectively with the awesome-n8n-templates repository. It should be updated as the repository structure or conventions evolve.*
