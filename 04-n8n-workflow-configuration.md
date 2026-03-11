## n8n Workflow Configuration

### Webhook Node
| Setting | Value |
|---------|-------|
| **Method** | `POST` |
| **Path** | `/webhook/wazuh-alerts` |
| **Response Mode** | `Immediately` |
| **Authentication** | `None` |

### IF Filter Node
| Setting | Value |
|---------|-------|
| **Condition** | `{{ $json.body.rule.level }} >= 8` |
| **True Branch** | `Continue to AI analysis` |
| **False Branch** | `NoOps` |

### AI Investigation Node
| Setting | Value |
|---------|-------|
| **Type** | `Investigation Summarization` |
| **Individual Summary Prompt** | See below ↓ |
| **Final Prompt to Combine** | See below ↓ |

### Telegram Node
| Setting | Value |
|---------|-------|
| **Credential** | `SOC Alert Bot (Telegram API)` |
| **Resource** | `Message` |
| **Operation** | `Send Message` |
| **Chat ID** | `[My Telegram Chat ID]` |
| **Parse Mode** | `Markdown` |
