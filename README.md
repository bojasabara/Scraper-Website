# Web Scraper and Crawler

A powerful web scraping and crawling application built with Node.js, featuring real-time progress tracking and a modern user interface.

## Features

- Single page scraping and full website crawling
- Real-time progress tracking with WebSocket
- Memory usage monitoring
- Concurrent processing for improved performance
- Modern and responsive user interface
- Support for JavaScript-heavy websites
- Customizable crawling depth and batch processing
- Docker support for easy deployment

## Prerequisites

- Docker and Docker Compose (recommended)
OR
- Node.js (v14 or higher)
- npm (v6 or higher)

## Installation

### Using Docker (Recommended)

1. Clone the repository:
```bash
git clone https://github.com/bojasabara/Scraper-Website.git
cd Scraper-Website
```

2. Build and start the container:
```bash
docker-compose up --build
```

The application will be available at `http://localhost:3000`

### Manual Installation

1. Clone the repository:
```bash
git clone https://github.com/bojasabara/Scraper-Website.git
cd Scraper-Website
```

2. Install dependencies:
```bash
npm install
```

3. Create a `.env` file in the root directory:
```bash
cp .env.example .env
```

4. Start the server:
```bash
npm run dev  # for development
npm start    # for production
```

## Environment Variables

Create a `.env` file with the following variables:

```env
PORT=3000                    # Server port
MAX_DEPTH=3                  # Maximum crawling depth
RATE_LIMIT_MS=1000          # Delay between requests
MAX_CONCURRENT=5            # Maximum concurrent requests
BROWSER_POOL_SIZE=3         # Number of browser instances
```

## Usage

1. Open your browser and navigate to `http://localhost:3000`

2. Enter a URL in the input field

3. Configure scraping options:
   - Crawling depth (1-10)
   - Request delay (ms)
   - Maximum concurrent requests
   - Enable/disable JavaScript processing

4. Choose your operation:
   - "Scrape Single Page" for individual page scraping
   - "Crawl Website" for full website crawling

5. Monitor progress in real-time through the dashboard

6. Download results in JSON or CSV format

## Configuration

The following parameters can be adjusted in `extract.js`:

- `RATE_LIMIT_MS`: Delay between requests (default: 1000ms)
- `MAX_CONCURRENT`: Maximum concurrent requests (default: 5)
- `TIMEOUT`: Request timeout (default: 30000ms)
- `BROWSER_POOL_SIZE`: Number of browser instances (default: 3)
- `BATCH_SIZE`: URLs to process in each batch (default: 5)

## Docker Configuration

The Docker environment can be customized through the following files:

- `Dockerfile`: Contains the container build instructions
- `docker-compose.yml`: Defines the service configuration
- `chrome.json`: Security profile for running Chrome in Docker

You can adjust the following in `docker-compose.yml`:
- Port mapping (default: 3000:3000)
- Memory limits (default: 2GB max, 1GB reserved)
- CPU limits (default: 2 CPUs max, 1 CPU reserved)

## Project Structure

- `server.js`: Main server file with WebSocket and HTTP endpoints
- `extract.js`: Core scraping and crawling logic
- `public/`: Frontend assets
  - `index.html`: Main UI
  - `styles.css`: UI styling
  - `script.js`: Client-side JavaScript
- `Dockerfile`: Container build instructions
- `docker-compose.yml`: Container orchestration
- `chrome.json`: Chrome security profile

## API Endpoints

- `GET /api/status`: Get current scraping status
- `POST /api/scrape`: Start single page scraping
- `POST /api/crawl`: Start website crawling
- `GET /api/results`: Download scraped data
- `POST /api/stop`: Stop current operation

## Error Handling

The application includes comprehensive error handling for:
- Invalid URLs
- Network timeouts
- Rate limiting responses
- Memory limitations
- Malformed HTML

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- Built with Node.js and Puppeteer
- Uses WebSocket for real-time communication
- Implements modern web technologies and best practices
- Docker support for consistent deployment