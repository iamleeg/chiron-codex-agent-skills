# Zoternote - Zotero to Evernote Sync Tool

Zoternote is a command-line tool that synchronizes notes from Zotero items to Evernote. It helps researchers and academics keep their literature notes organized by automatically transferring Zotero item notes to Evernote notebooks.

## Installation

### Prerequisites

- Python 3.14+
- Zotero account with API access enabled
- Evernote developer account and API credentials
- `poetry` for dependency management (recommended)

### Install the package

```bash
# Clone the repository
git clone https://github.com/yourusername/zoternote.git
cd zoternote

# Install dependencies using poetry
poetry install

# Or install directly with pip
pip install .
```

## Setup and Configuration

### 1. Get Zotero API Credentials

1. Go to [Zotero Settings](https://www.zotero.org/settings/keys)
2. Click "Create new private key"
3. Give it a name (e.g., "Zoternote")
4. Note your **User ID** (shown at the top of the page)
5. Copy the generated API key

### 2. Get Evernote API Credentials

1. Go to [Evernote Developer](https://dev.evernote.com/)
2. Create a new application
3. Note your **Consumer Key** and **Consumer Secret**
4. Complete OAuth authentication to get an **OAuth Token**
5. Create or identify the target notebook and get its **Notebook GUID**

### 3. Configure Environment Variables

Create a `.env` file in the project root based on `.env.example`:

```bash
cp .env.example .env
```

Edit `.env` with your credentials:

```ini
# Zotero API configuration
ZOTERO_API_KEY="your_zotero_api_key"
ZOTERO_USER_ID="your_zotero_user_id"

# Evernote API configuration  
EVERNOTE_CONSUMER_KEY="your_evernote_consumer_key"
EVERNOTE_CONSUMER_SECRET="your_evernote_consumer_secret"
EVERNOTE_SANDBOX=False
EVERNOTE_TOKEN="your_evernote_oauth_token"
EVERNOTE_NOTEBOOK_GUID="your_target_notebook_guid"
```

**Important Notes:**
- Set `EVERNOTE_SANDBOX=True` if you're testing with the Evernote sandbox
- The `EVERNOTE_NOTEBOOK_GUID` determines which notebook notes will be synced to
- Keep this file secure as it contains sensitive credentials

## Usage

### Basic Sync Command

```bash
# Using poetry (recommended)
poetry run zoternote COLLECTION_KEY

# Or if installed globally
zoternote COLLECTION_KEY
```

Replace `COLLECTION_KEY` with the key of the Zotero collection you want to sync.

### Finding Your Zotero Collection Key

1. Log in to your Zotero account online
2. Navigate to the collection you want to sync
3. Look at the URL - it will contain something like `/collections/ABC123`
4. `ABC123` is your collection key

### How the Sync Works

1. **Collection Processing**: The tool fetches all items in the specified Zotero collection
2. **Note Extraction**: For each item, it extracts all associated notes
3. **Stable Identification**: Generates a unique identifier for each item to track sync state
4. **Note Creation/Update**: 
   - If no existing Evernote note is found (by tag), creates a new one
   - If an existing note is found, updates it with the latest content
5. **Metadata Preservation**: Creates Evernote note titles in format: `"Title (Author1, Author2, Year)"`

### Example Workflow

```bash
# Sync your "Research Papers" collection to Evernote
ezoternote D9F8K7L6

# Check the output for sync status
Starting sync for collection: D9F8K7L6
Found 15 items in collection
Processing item 'The Future of AI' (key: ABC123)
  Found 2 notes for item 'The Future of AI'
  Generated stable identifier: zotero-ABC123-doi-10.1234/ai5678
  Creating new Evernote note
Processing item 'Machine Learning Basics' (key: DEF456)
  Found 1 notes for item 'Machine Learning Basics'
  Generated stable identifier: zotero-DEF456-isbn-9781234567890
  Updating existing Evernote note
...
Sync completed successfully
```

## Advanced Configuration

### Multiple Notebooks

To sync different collections to different notebooks:

1. Create multiple `.env` files (e.g., `.env.research`, `.env.reading`)
2. Modify the `EVERNOTE_NOTEBOOK_GUID` in each file
3. Use the appropriate environment file when running:

```bash
# For research notebook
env $(cat .env.research) zoternote RESEARCH_COLLECTION_KEY

# For reading notebook  
env $(cat .env.reading) zoternote READING_COLLECTION_KEY
```

### Sandbox Testing

Set `EVERNOTE_SANDBOX=True` in your `.env` file to test with Evernote's sandbox environment without affecting your production data.

## Troubleshooting

### Common Issues

**"Failed to fetch items from collection"**: 
- Verify your Zotero API key and user ID are correct
- Check that the collection key exists and is accessible
- Ensure your Zotero account has API access enabled

**"Evernote API request failed"**:
- Verify all Evernote credentials are correct
- Check that the notebook GUID exists and is accessible
- Try setting `EVERNOTE_SANDBOX=True` if you're testing

**"No notes found for items"**:
- Make sure your Zotero items actually have notes attached
- Notes must be of type "note" in Zotero (not annotations or attachments)

### Debugging

Run with verbose output to see more details:

```bash
# Using poetry
poetry run python -m zoternote COLLECTION_KEY

# Or with pip installation
python -m zoternote COLLECTION_KEY
```

## Security Considerations

- Never commit your `.env` file to version control
- Keep API keys and tokens secure
- Use environment variables instead of hardcoding credentials
- Consider using a secrets manager for production deployments


## Support

For help with Zotero API issues, visit the [Zotero Forums](https://forums.zotero.org/)
For Evernote API questions, check the [Evernote Developer Documentation](https://dev.evernote.com/)
