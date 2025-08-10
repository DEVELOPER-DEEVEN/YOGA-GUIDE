# Pose Generator with GenAI

A powerful application for generating and manipulating human poses using Google's Imagen on Google Cloud Platform with Spring Boot integration.

## 🚀 Features

- Generate human poses using Google's Imagen AI
- Real-time pose visualization
- Spring Boot backend for API services
- Google Cloud Platform integration
- Support for multiple input formats
- Scalable cloud-based architecture

## 🛠️ Tech Stack

### Backend
- **Java 17+** - Primary programming language
- **Spring Boot 3.x** - Application framework
- **Spring Web** - RESTful web services
- **Spring Cloud GCP** - Google Cloud Platform integration
- **Imagen** - Google's text-to-image generation model

### Frontend (Optional)
- **React.js** - Frontend library
- **Three.js** - 3D pose visualization
- **Material-UI** - UI components

### Infrastructure
- **Google Cloud Platform** - Cloud services
- **Docker** - Containerization
- **Kubernetes** - Container orchestration (optional)

### Development Tools
- **Maven** - Dependency management
- **Lombok** - Boilerplate reduction
- **JUnit 5** - Testing framework
- **Git** - Version control
- **GitHub Actions** - CI/CD pipeline

## 📦 Prerequisites

- Java 17 or higher
- Maven 3.6+
- Google Cloud SDK
- Docker (for containerization)
- Node.js 16+ (for frontend development)

## 🛠️ Installation

### Prerequisites
- Java 17 or higher
- Maven 3.6+
- Google Cloud SDK
- Docker (optional, for containerization)
- Node.js 16+ (for frontend development, if applicable)

### Step 1: Clone the Repository
```bash
git clone https://github.com/yourusername/genai-posegen.git
cd genai-posegen
```

### Step 2: Set Up Google Cloud
1. Install Google Cloud SDK:
   ```bash
   # For macOS using Homebrew
   brew install --cask google-cloud-sdk
   ```
   
   For other operating systems, follow the [official installation guide](https://cloud.google.com/sdk/docs/install).

2. Initialize and authenticate:
   ```bash
   gcloud init
   gcloud auth application-default login
   ```

3. Enable required APIs:
   ```bash
   gcloud services enable aiplatform.googleapis.com
   gcloud services enable storage-component.googleapis.com
   ```

### Step 3: Configure Application
1. Create a service account and download the JSON key:
   ```bash
   gcloud iam service-accounts create posegen-service-account \
     --display-name="Pose Generator Service Account"
   
   gcloud projects add-iam-policy-binding YOUR_PROJECT_ID \
     --member="serviceAccount:posegen-service-account@YOUR_PROJECT_ID.iam.gserviceaccount.com" \
     --role="roles/aiplatform.user"
   
   gcloud iam service-accounts keys create service-account.json \
     --iam-account=posegen-service-account@YOUR_PROJECT_ID.iam.gserviceaccount.com
   ```

2. Set the environment variable:
   ```bash
   export GOOGLE_APPLICATION_CREDENTIALS="$(pwd)/service-account.json"
   ```

### Step 4: Build the Application
```bash
# Install dependencies
mvn clean install

# Run the application
mvn spring-boot:run
```

### Step 5: Verify Installation
1. The application should start on `http://localhost:8080`
2. Check the health endpoint:
   ```bash
   curl http://localhost:8080/actuator/health
   ```

## 🚀 Quick Start

1. **Generate your first pose**
   ```bash
   curl -X POST http://localhost:8080/api/pose/generate \
     -H "Content-Type: application/json" \
     -d '{"prompt": "a person doing yoga"}'
   ```

2. **List generated poses**
   ```bash
   curl http://localhost:8080/api/pose
   ```

### Docker

```bash
docker build -t genai-posegen .
docker run -p 8080:8080 genai-posegen
```

## 🏗️ Project Structure

```
genai-posegen/
├── src/
│   ├── main/
│   │   ├── java/com/posegen/
│   │   │   ├── config/        # Configuration classes
│   │   │   ├── controller/    # REST controllers
│   │   │   ├── service/       # Business logic
│   │   │   ├── model/         # Data models
│   │   │   ├── repository/    # Data access
│   │   │   └── PoseGenApplication.java
│   │   └── resources/
│   │       ├── application.yml
│   │       └── application-dev.yml
│   └── test/                  # Test files
├── .github/workflows/         # GitHub Actions
├── .gitignore
├── Dockerfile
├── pom.xml
└── README.md
```

## 🌐 API Endpoints

- `POST /api/pose/generate` - Generate a new pose
- `GET /api/pose/{id}` - Get a generated pose by ID
- `GET /api/pose` - List all generated poses

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Google Cloud Platform for the infrastructure
- Google Research for the Imagen model
- Spring Boot team for the amazing framework

## 📧 Contact

Your Name - [@yourtwitter](https://twitter.com/yourtwitter) - your.email@example.com

Project Link: [https://github.com/yourusername/genai-posegen](https://github.com/yourusername/genai-posegen)
# YOGA-GUIDE
# YOGA-GUIDE
