# Personal AI Assistant with n8n

## Overview
This project is a **Personal AI Assistant** built using **n8n**, an open-source workflow automation tool. The assistant processes tasks sent via a **Telegram chat** and performs actions such as reading emails, sending emails, adding calendar events, and conducting web searches. The results are then sent to a **Discord server** for output.

## Features
- **Telegram Integration**: Receive tasks via Telegram messages.
- **Email Handling**: Read and send emails based on user commands.
- **Calendar Management**: Add events to a calendar.
- **Web Search**: Perform web searches and return relevant results.
- **Discord Output**: Send task outputs to a specified Discord server channel.
- **Customizable Workflow**: Easily extendable for additional tasks using n8n nodes.

## Prerequisites
To run this project, you need the following:
- **n8n**: Installed and running (self-hosted or cloud instance).
- **Telegram Bot**: A Telegram bot with API token for receiving messages.
- **Email Service**: Access to an email account (e.g., Gmail) with API credentials.
- **Google Calendar API**: API credentials for calendar integration.
- **Discord Webhook**: A Discord webhook URL for sending outputs.
- **Node.js**: For running n8n locally (if self-hosted).
- A working internet connection for web searches.

## Setup Instructions
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/personal-ai-assistant.git
   cd personal-ai-assistant
   ```

2. **Install n8n** (if self-hosted):
   Follow the [n8n installation guide](https://docs.n8n.io/getting-started/installation/) to set up n8n on your system.

3. **Import the Workflow**:
   - Copy the contents of `Cat AI Assistant workflow.json` (provided in the repository).
   - In the n8n interface, go to **Workflows > Import from File** and paste the JSON content.
   - Save the workflow.

4. **Configure Credentials**:
   - Set up credentials for:
     - **Telegram**: Add your bot token in n8n's Telegram node.
     - **Email**: Configure IMAP/SMTP or Gmail API credentials.
     - **Google Calendar**: Add OAuth2 credentials for Google Calendar API.
     - **Discord**: Add your Discord webhook URL in the Discord node.
   - Update the respective nodes in the workflow with these credentials.

5. **Activate the Workflow**:
   - In n8n, open the imported workflow and click **Activate**.
   - Test the workflow by sending a command via Telegram (e.g., "Read my emails" or "Search for n8n tutorials").

6. **Monitor Outputs**:
   - Check the specified Discord channel for task results.

## Workflow Details
The workflow (`Cat AI Assistant workflow.json`) includes the following nodes:
- **Telegram Trigger**: Listens for incoming messages from the Telegram bot.
- **Switch Node**: Routes tasks based on command keywords (e.g., "read email," "send email," "add event," "search").
- **Email Nodes**: IMAP/SMTP or Gmail nodes for email reading and sending.
- **Google Calendar Node**: Adds events to the user's calendar.
- **HTTP Request Node**: Performs web searches using an API (e.g., Google Search API or similar).
- **Discord Node**: Sends formatted results to the Discord webhook.

### Example Commands
- `read email`: Fetches the latest unread emails.
- `send email to [recipient] subject [subject] message [body]`: Sends an email.
- `add event [date] [time] [title]`: Adds a calendar event.
- `search [query]`: Performs a web search and returns results.

## File Structure
- `Cat AI Assistant workflow`: The n8n workflow configuration file.
- `README.md`: This file provides project documentation.

## Usage
1. Send a command via Telegram to your bot (e.g., `search n8n automation`).
2. The assistant processes the command using the n8n workflow.
3. Results are sent to the configured Discord channel.

## Customization
- Add new commands by modifying the **Switch Node** in the workflow.
- Integrate additional services (e.g., Slack, Trello) by adding relevant nodes.
- Update the Discord message format in the Discord node for custom output styles.

## Contributing
Contributions are welcome! Please:
1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature`).
3. Make your changes and commit (`git commit -m "Add your feature"`).
4. Push to the branch (`git push origin feature/your-feature`).
5. Open a pull request.


## Contact
For questions or support, reach out via [GitHub Issues](https://github.com/your-username/personal-ai-assistant/issues) or contact me on Discord/Telegram.

