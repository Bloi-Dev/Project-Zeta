# Contributing to Project Zeta

Thank you for your interest in contributing to Project Zeta.

Project Zeta is a Discord bot and WebUI system for managing student channels, organizing channels by category, and generating monthly student summaries for center leadership.

## Project Goals

Project Zeta is designed to:

- Create and manage Discord server channels
- Organize student channels into alphabetical categories
- Use student channel names in the format `{Grade} - {Name} - {Student ID}`
- Create missing student channels automatically
- Archive or remove student channels when needed
- Summarize student channel messages for a selected month
- Provide a WebUI for center leadership to manage students and summaries

## Getting Started

1. Fork or clone the repository.

```bash
git clone git@github.com:Bloi-Dev/Project-Zeta.git
cd Project-Zeta
````

2. Create a new branch for your work.

```bash
git checkout -b feature/your-feature-name
```

Use clear branch names, such as:

```text
feature/student-channel-creation
feature/monthly-summary
fix/channel-sorting
docs/update-readme
```

3. Make your changes.

4. Commit your work with a clear message.

```bash
git add .
git commit -m "Add student channel creation logic"
```

5. Push your branch.

```bash
git push -u origin feature/your-feature-name
```

6. Open a pull request into the main branch.

## Development Guidelines

### Code Style

* Write clear, readable Python code.
* Use meaningful variable and function names.
* Keep functions focused on one responsibility.
* Add comments when logic is not immediately obvious.
* Avoid hardcoding secrets, IDs, tokens, or server-specific values.

### Python Guidelines

* Use virtual environments when developing locally.
* Keep dependencies listed in the appropriate dependency file.
* Prefer type hints where helpful.
* Keep Discord bot logic, WebUI logic, and shared utilities separated when possible.

Example:

```text
src/
├── bot/
├── web/
├── services/
├── models/
└── utils/
```

### Discord Bot Guidelines

When working on Discord features:

* Do not hardcode Discord server IDs, category IDs, channel IDs, or role IDs.
* Use configuration files or environment variables.
* Be careful with destructive actions such as deleting channels.
* Prefer archiving channels over deleting them unless deletion is explicitly required.
* Add safeguards for bulk channel operations.
* Make sure channel organization is predictable and repeatable.

### WebUI Guidelines

When working on the WebUI:

* Keep leadership/admin workflows simple and clear.
* Validate user input before saving or applying changes.
* Avoid exposing private student information unnecessarily.
* Use clear confirmation steps for destructive actions.

### Privacy and Student Data

Project Zeta may handle student names, IDs, and Discord messages. Treat this information carefully.

Contributors should:

* Avoid committing real student data.
* Use fake or sample data in tests and examples.
* Never commit Discord bot tokens, API keys, database passwords, or private credentials.
* Avoid logging sensitive student information unless necessary for debugging.
* Remove sensitive debug logs before opening a pull request.

## Environment Variables

Secrets and configuration should be stored in environment variables, not committed to the repository.

Example `.env` values:

```env
DISCORD_BOT_TOKEN=
DISCORD_GUILD_ID=
DATABASE_URL=
SECRET_KEY=
```

Do not commit your `.env` file.

A safe example file may be provided as:

```text
.env.example
```

## Commit Message Guidelines

Use short, descriptive commit messages.

Good examples:

```text
Add student channel naming helper
Fix alphabetical category sorting
Create monthly summary service
Update setup instructions
```

Avoid vague messages like:

```text
fix stuff
changes
update
final
```

## Pull Request Guidelines

Before opening a pull request:

* Make sure your code runs locally.
* Make sure no secrets or private data are committed.
* Update documentation when behavior changes.
* Add or update tests when possible.
* Keep pull requests focused on one main change.

A good pull request should include:

* What changed
* Why it changed
* How it was tested
* Any known limitations or follow-up work

## Issues

Use GitHub Issues to track work.

Good issues should include:

* A clear title
* A description of the problem or feature
* Acceptance criteria
* Any relevant notes, screenshots, or examples

Example issue title:

```text
Create student channel naming utility
```

Example acceptance criteria:

```text
- Generates channel names using grade, student name, and student ID
- Handles extra spaces in student names
- Returns names in the format `{Grade} - {Name} - {Student ID}`
- Includes tests for valid and invalid inputs
```

## Testing

When tests are available, run them before submitting a pull request.

Example:

```bash
pytest
```

If no automated tests exist yet, manually test your change and describe what you tested in the pull request.

## Documentation

Update documentation when adding or changing:

* Setup steps
* Environment variables
* Bot commands
* WebUI workflows
* Database models
* Deployment steps
* Permissions requirements

## Security

Do not commit:

* Discord bot tokens
* API keys
* Passwords
* Private SSH keys
* `.env` files
* Real student records
* Private server exports

If you accidentally commit a secret, rotate the secret immediately and notify the project maintainer.

## Code of Conduct

Be respectful and constructive.

Contributors are expected to:

* Communicate clearly
* Give helpful feedback
* Avoid personal attacks
* Respect privacy and confidentiality
* Keep discussions focused on improving the project

## Maintainer Notes

Maintainers may request changes before merging a pull request. This is normal and helps keep the project stable, secure, and maintainable.

Thank you for helping build Project Zeta.
