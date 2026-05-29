# Architecture

Project Zeta is a Discord bot and web dashboard system for managing student Discord channels and generating monthly student summaries from Discord message history.

The main goal of the architecture is to keep the system organized, safe, and easy to expand.

## Architecture Diagram

<img width="1536" height="1024" alt="fcf789c0-d249-4a98-8670-238918c833f0" src="https://github.com/user-attachments/assets/4fdae72b-2862-4084-92a8-68e356c4072e" />

> The Web Dashboard should never talk directly to Discord.  
> All Discord actions should go through the Backend API and Discord Bot Service.
