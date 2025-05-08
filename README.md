# TripAdvisor Explorer App

A Flask web application that displays TripAdvisor data for restaurants, hotels, and attractions in different cities with a delicious fried chicken theme.

## Features

- View TripAdvisor data for Tacoma, Seattle, and Olympia
- Browse restaurants, hotels, and attractions using Bootstrap carousels
- Responsive design with Bootstrap 5 (Cosmo theme)
- Aesthetically pleasing fried chicken background
- Docker containerization for easy deployment

## Technologies Used

- Python 3.9
- Flask
- Bootstrap 5
- Docker
- AWS EC2

## Installation and Setup

### Prerequisites

- Python 3.9 or higher
- Docker (optional for containerized deployment)

### Local Development

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/tripadvisor-explorer.git
   cd tripadvisor-explorer
   ```

2. **Set up a virtual environment**:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the application**:
   ```bash
   python app.py
   ```

5. **Access the application**:
   Open your browser and navigate to `http://localhost:5000`

### Docker Deployment

1. **Build the Docker image**:
   ```bash
   docker build -t tripadvisor-explorer .
   ```

2. **Run the container**:
   ```bash
   docker run -p 80:5000 tripadvisor-explorer
   ```

3. **Access the application**:
   Open your browser and navigate to `http://localhost`

## AWS EC2 Deployment

1. **Push Docker image to Docker Hub**:
   ```bash
   docker tag tripadvisor-explorer yourusername/tripadvisor-explorer:latest
   docker push yourusername/tripadvisor-explorer:latest
   ```

2. **On EC2 instance**:
   ```bash
   docker pull yourusername/tripadvisor-explorer:latest
   docker run -d -p 80:5000 yourusername/tripadvisor-explorer:latest
   ```

## Project Structure

```
tripadvisor-explorer/
├── app.py                # Main Flask application
├── api/
│   └── fetch_data.py     # Data fetching utilities
├── templates/
│   ├── base.html         # Base template with layout and navigation
│   ├── index.html        # Home page with carousels
│   └── about.html        # About page
├── data/                 # Cached TripAdvisor data
├── Dockerfile            # Docker configuration
└── requirements.txt      # Python dependencies
```

## Key Features

- **City Selection**: Choose between Tacoma, Seattle, and Olympia
- **Category Carousels**: Browse through restaurants, hotels, and attractions
- **Responsive Design**: Works on desktop and mobile devices
- **Cached Data**: Uses pre-cached TripAdvisor data for demonstration purposes

## Development Notes

- The application uses cached TripAdvisor data, so no API key is required
- All carousel indicators have been removed as requested
- Cards within carousels are center-aligned using Bootstrap utility classes
- The background features a high-quality fried chicken image for aesthetic appeal

## Project Requirements Completed

- [x] Configure server to fetch data with `use_cache_only=True`
- [x] Implement Bootstrap carousels for each category
- [x] Remove carousel indicators
- [x] Center-align card content
- [x] Add "Olympia" to City menu
- [x] Replace Categories with About link
- [x] Create About page
- [x] Update footer with current year and name
- [x] Add background image
- [x] Dockerize application
- [x] Deploy to EC2

## Author

Richard Le
Professor Ling-Hong Hung

## License

This project is licensed under the MIT License - see the LICENSE file for details.
