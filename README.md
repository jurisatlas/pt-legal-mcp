# Portugal Legal Research MCP Server (`pt-legal-mcp`)

**[Português](#lang-pt) | [English Documentation](#english-documentation)**

---

<a id="lang-pt"></a>
## Servidor MCP de Legislação e Jurisprudência (`pt-legal-mcp`) — Português

### Sobre este repositório

Este repositório disponibiliza um servidor Model Context Protocol (MCP) que liga o seu assistente de IA (Claude Desktop, Cursor, Windsurf, VS Code / Copilot ou Antigravity) ao Diário da República (`diariodarepublica.pt`) e às bases de dados da DGSI (`dgsi.pt`: Tribunais de Comarca, TAF, 5 Tribunais da Relação, TCA, Supremo Tribunal de Justiça, STA e Tribunal Constitucional).

### Instalação rápida (Seleção da aplicação de IA)

1. **Transferir:** Clique em **`<> Code` -> `Download ZIP`** e extraia a pasta no seu computador.
2. **Executar:** Faça duplo clique em **`Click_Here_To_Install_Windows.bat`** (Windows) ou **`Click_Here_To_Install_Mac.command`** (macOS).
3. **Selecionar cliente IA:** Escolha as aplicações de IA que utiliza, clique em instalar e reinicie a aplicação selecionada.

**Nota de segurança:** O instalador funciona exclusivamente em modo de leitura e não acede aos seus ficheiros pessoais.

### Hierarquia dos tribunais e fontes oficiais

| Instância | Tribunais abrangidos |
|:---|:---|
| **1.ª Instância (Tribunais de Comarca e TAF)** | 23 Tribunais Judiciais de Comarca & Tribunais Administrativos e Fiscais de Círculo (TAF) |
| **2.ª Instância (Tribunais da Relação e TCA)** | 5 Tribunais da Relação (Lisboa, Porto, Coimbra, Évora, Guimarães) & 2 Tribunais Centrais Administrativos (TCA Sul & TCA Norte) |
| **STJ, STA e Tribunal Constitucional** | Supremo Tribunal de Justiça (STJ), Supremo Tribunal Administrativo (STA) & Tribunal Constitucional (TC) |

- **Diário da República Eletrónico (diariodarepublica.pt):** [https://diariodarepublica.pt](https://diariodarepublica.pt) (`diariodarepublica.pt`, `pgdlisboa.pt`, `parlamento.pt`)
- **DGSI Bases Jurídico-Documentais (dgsi.pt — STJ, STA, 5 Tribunais da Relação & 2 TCA):** [http://www.dgsi.pt](http://www.dgsi.pt) (`dgsi.pt`, `stj.pt`, `tribunalconstitucional.pt`, `stadministrativo.pt`)

---

<a id="english-documentation"></a>
## English Documentation

Model Context Protocol (MCP) server providing live, read-only access to **Portugal (PT)** legislation, official gazettes, multi-tier judicial decisions (First Instance, Regional/Cantonal/Appellate, and Supreme/Constitutional courts, including HTML and PDF full-text extraction), and statutory citation verification across all major AI clients (**ChatGPT Desktop, OpenAI Codex CLI, Claude Desktop, Claude Code CLI, Cursor, Windsurf, VS Code / GitHub Copilot / Cline / Roo Code, Google Antigravity / Gemini CLI, Perplexity, and Continue.dev**).

---

### Interactive Desktop Setup (Select Your AI Assistant)

This package includes a graphical installer for legal practitioners and non-technical users that lets you select which AI application(s) you use:

1. **Download:** Click **`<> Code`** at the top right of this repository, select **`Download ZIP`**, and extract the folder to your computer.
2. **Run the Setup Utility:**
   - **Windows:** Double-click `Click_Here_To_Install_Windows.bat`
   - **macOS:** Double-click `Click_Here_To_Install_Mac.command`
3. **Select Your AI Client(s) & Connect:** Check the box(es) for the AI assistant(s) installed on your computer (**ChatGPT Desktop & OpenAI Codex CLI**, **Claude Desktop & Claude Code CLI**, **Cursor**, **Windsurf**, **VS Code / GitHub Copilot / Cline / Roo Code**, **Google Antigravity / Gemini CLI**, or **Perplexity / Continue.dev**), click **Install to Selected AI Clients**, and restart your selected AI application.

**System Integrity Note:** The setup utility operates strictly in read-only mode with respect to your personal files and documents. It installs an isolated Python runtime inside the extracted folder and registers the server entry only in the AI client configuration files you select.

---

### Multi-Tier Judicial Hierarchy & Live Indexed National Archives

This server performs live queries across the full judicial hierarchy and official legal archives of **Portugal**, extracting full text from both HTML pages and official court/gazette PDF judgments:

| Judicial Tier | Covered Courts & Tribunals |
|:---|:---|
| **Tier 1 — First Instance** | 23 Tribunais Judiciais de Comarca & Tribunais Administrativos e Fiscais de Círculo (TAF) |
| **Tier 2 — Regional / Cantonal / Appellate** | 5 Tribunais da Relação (Lisboa, Porto, Coimbra, Évora, Guimarães) & 2 Tribunais Centrais Administrativos (TCA Sul & TCA Norte) |
| **Tier 3 — Supreme & Constitutional** | Supremo Tribunal de Justiça (STJ), Supremo Tribunal Administrativo (STA) & Tribunal Constitucional (TC) |

#### Official Portals & Live Indexed Domains

- **National Legislation & Official Gazette:** Diário da República Eletrónico (diariodarepublica.pt) — [https://diariodarepublica.pt](https://diariodarepublica.pt)
  - *Indexed Legislation Domains:* `diariodarepublica.pt`, `pgdlisboa.pt`, `parlamento.pt`
- **Court Decisions & Jurisprudence Archives:** DGSI Bases Jurídico-Documentais (dgsi.pt — STJ, STA, 5 Tribunais da Relação & 2 TCA) — [http://www.dgsi.pt](http://www.dgsi.pt)
  - *Indexed Judicial & Open Case Law Domains:* `dgsi.pt`, `stj.pt`, `tribunalconstitucional.pt`, `stadministrativo.pt`

---

### Available MCP Tools

| Tool | Description |
|:---|:---|
| `search_legislation` | Searches enacted statutes, codes, decrees, and official gazette publications in Portugal. |
| `search_case_law` | Searches national jurisprudence and open judicial archives for Portugal. |
| `search_tiered_court_decisions` | Filters case law specifically by judicial instance (`first_instance`, `appellate_regional`, `supreme_constitutional`) or specific regional/cantonal/district court. |
| `list_court_hierarchy` | Returns the complete 3-tier court structure and supported regional court filters for Portugal. |
| `get_legal_document_markdown` | Retrieves full statutory or judicial texts (both HTML and official `.pdf` court judgments) and converts them into clean Markdown. |
| `verify_citation` | Validates statutory and case law citations against official registries. |

---

<details>
<summary><b>Manual Configuration for Developers (Optional)</b></summary>

```json
{
  "mcpServers": {
    "pt-legal-mcp": {
      "command": "uvx",
      "args": [
        "--from",
        "https://github.com/jurisatlas/pt-legal-mcp/archive/refs/heads/main.zip",
        "pt-legal-mcp"
      ]
    }
  }
}
```
</details>
