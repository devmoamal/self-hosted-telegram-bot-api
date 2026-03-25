# Telegram Bot API Local Server

This repository contains a Docker Compose configuration to run a local instance of the Telegram Bot API server. Running the API locally allows for higher limits, such as sending larger files and bypassing the standard rate limits.

## Prerequisites

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)
- Telegram API ID and API Hash (Obtained from [my.telegram.org](https://my.telegram.org/))

## Getting Started

1.  **Clone the repository:**
    ```bash
    git clone <repository-url>
    cd telegram-bot-api
    ```

2.  **Environment Variables:**
    Create a `.env` file or set the following environment variables:
    - `TELEGRAM_API_ID`: Your Telegram API ID.
    - `TELEGRAM_API_HASH`: Your Telegram API Hash.
    - `TELEGRAM_LOCAL`: Set to `1` (default) to enable local mode.

3.  **Run the server:**
    ```bash
    docker compose up -d
    ```

## Usage

The server will be available at `http://localhost:8081`. You can point your bot to this local endpoint.

### Health Check

You can verify the server is running by accessing `http://localhost:8081` in your browser or using `curl`:
```bash
curl http://localhost:8081
```

## Configuration

- **Ports:** The API server is exposed on port `8081`.
- **Volumes:** Data is persisted in a local Docker volume named `telegram-bot-api-data`.
- **Networks:** Uses a custom `internal` network and an external `coolify` network if available.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
