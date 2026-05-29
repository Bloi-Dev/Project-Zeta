# Project Zeta

Project Zeta is a Discord bot and WebUI system for managing student channels, organizing those channels into alphabetical categories, and generating monthly student summaries for center leadership.

## Overview

Project Zeta helps center leadership manage student-specific Discord channels in a structured and consistent way.

The system is designed to:

- Create and manage Discord server channels
- Organize student channels alphabetically by student name
- Create A-Z Discord categories
- Name student channels using the format `{Grade} - {Name} - {Student ID}`
- Automatically create missing student channels
- Archive or remove students when needed
- Generate monthly summaries of student channel messages
- Provide a WebUI for leadership to manage students, channels, and summaries

## Features

### Discord Bot

The Discord bot will be responsible for:

- Creating student channels
- Managing channel names
- Creating alphabetical categories from A to Z
- Sorting student channels into the correct category
- Keeping channels ordered alphabetically
- Detecting missing student channels
- Creating new student channels when needed
- Archiving inactive or removed students
- Reading messages for a selected month
- Generating student-specific monthly summaries

### WebUI

The WebUI will allow center leadership to:

- View all students
- Add new students
- Edit student information
- Remove students
- Archive students
- Trigger channel organization
- Select a month for summaries
- Generate student summaries
- View and export summary results

## Channel Naming Format

Student channels should follow this format:

```text
{Grade} - {Name} - {Student ID}
```

Example:

```text
5 - Alice Johnson - 12345
```

## Category Organization

Student channels are organized into alphabetical categories based on the student's name.

Example:

```text
A
├── 5 - Alice Adams - 10001
├── 6 - Alice Johnson - 10002
└── 4 - Ava Smith - 10003

B
├── 7 - Ben Carter - 10004
└── 5 - Bella Nguyen - 10005
```

## Project Structure

Recommended structure:

```text
Project-Zeta/
├── README.md
├── CONTRIBUTING.md
├── LICENSE
├── .gitignore
├── .env.example
├── src/
│   ├── bot/
│   ├── web/
│   ├── services/
│   ├── models/
│   └── utils/
├── tests/
└── docs/
```

## Getting Started

### Prerequisites

You will need:

- Python 3.11 or newer
- Git
- A Discord bot application
- Access to a Discord server where the bot can manage channels
- Required Discord permissions for the bot

Recommended bot permissions include:

- Manage Channels
- View Channels
- Read Message History
- Send Messages
- Manage Roles, if role-based permissions are added later

## Installation

Clone the repository:

```bash
git clone git@github.com:Bloi-Dev/Project-Zeta.git
cd Project-Zeta
```

Create and activate a virtual environment:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

## Environment Setup

Copy the example environment file:

```bash
cp .env.example .env
```

Then fill in your local values:

```env
DISCORD_BOT_TOKEN=
DISCORD_GUILD_ID=
DATABASE_URL=
SECRET_KEY=
```

Do not commit your real `.env` file.

## Running the Project

Bot startup command will be added once the bot entry point is implemented.

Possible future command:

```bash
python -m src.bot
```

WebUI startup command will be added once the WebUI entry point is implemented.

Possible future command:

```bash
python -m src.web
```

## Monthly Summaries

Project Zeta will generate summaries by reading messages from a selected student's channel during a selected month.

The intended summary flow is:

1. Leadership selects a month in the WebUI.
2. Project Zeta finds each student channel.
3. The bot reads messages from the start of the selected month to the end of the selected month.
4. The system generates a summary for each student.
5. Leadership reviews summaries in the WebUI.

## Privacy and Security

Project Zeta may handle student names, student IDs, Discord messages, and summary data.

Do not commit:

- Discord bot tokens
- API keys
- Passwords
- `.env` files
- Real student data
- Private server exports
- Generated message transcripts containing student information

Use fake or sample data for testing and documentation.

## Development Status

Project Zeta is currently in early development.

Planned Sprint 0 work includes:

- Repository setup
- Project documentation
- Environment configuration
- Basic folder structure
- Discord bot setup
- WebUI setup
- Initial student data model
- Initial issue tracking

## Contributing

Contributions should follow the guidelines in [`CONTRIBUTING.md`](CONTRIBUTING.md).

Before opening a pull request:

- Create a focused branch
- Keep changes small and clear
- Avoid committing secrets or real student data
- Update documentation when needed
- Test your changes when possible

## License

See [`LICENSE`](LICENSE) for license information.

## Maintainer

Project Zeta is maintained by Bloi-Dev.