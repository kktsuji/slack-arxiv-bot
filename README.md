# arxiv-bot

Notify to webhooks of new papers on arXiv.

## Local Execution

### Check Environment

Check your environment. Ubuntu 22.04.4 LTS is only supported.

```bash
lsb_release -a
# Ubuntu 22.04.4 LTS
```

Clone this project.

```bash
git clone git@github.com:kktsuji/arxiv-bot.git
cd arxiv-bot
```

Python version must be 3.12.3.

```python
python --version
# Python 3.12.3
```

Install python packages.

```python
pip install -U pip
pip install -r requirements.txt
```

Configure environment variables.

```bash
vim .env

WEBHOOK_URL=https://YOUR_WEBHOOK_URL
KEYWORDS=keyword1,keyword2,keyword3
CATEGORIES=cs.AI,cs.CV,cs.LG,eess.IV
```

| Key | Description |
|----------|----------|
| webhook_url | The webhook url such as Slack, Teams, and other service APIs. |
| keywords | Keywords used in queries for arXiv searches.<br>Each keyword is separated by a comma with no spaces.<br>Keywords are used to search titles and abstracts.<br>Keywords are searched for with "or".<br>For example, if the value "keyword1,keyword2" is specified, paper containing "keyword1" and papers containing "keyword2" will be displayed as search results. |
| categories | Categories used in queries for arXiv searches.<br>This follows the same rule of keywords (separated by comma without space, searched with "or").<br>For more details, see [arXiv Category Taxonomy](https://arxiv.org/category_taxonomy). |

Execute script.

```python
python main.py
```

## AWS Execution

See [my blog post](https://tsuji.tech/arxiv-bot-aws/) for AWS Configuration to Automatically Notify Webhooks of New Papers.
