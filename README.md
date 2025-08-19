# AI Nutrition Coach 🥗🤖

An intelligent Flask web application that analyzes food images and provides detailed nutritional information using AI-powered image recognition and nutritional analysis.

## 📋 Table of Contents
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [API Information](#api-information)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

## ✨ Features

- **Image Upload & Analysis**: Upload food images for instant nutritional analysis
- **AI-Powered Recognition**: Uses Meta's Llama 4 Maverick model via OpenRouter API
- **Comprehensive Nutritional Breakdown**: 
  - Food item identification
  - Portion size estimation
  - Calorie calculation
  - Nutrient breakdown (proteins, carbs, fats, vitamins, minerals)
  - Health evaluation
- **User-Friendly Interface**: Clean, responsive web interface with real-time image preview
- **Real-time Processing**: Live image preview and loading indicators

## 🔧 Prerequisites

Before you begin, ensure you have the following installed:

- **Python 3.7+** (recommended: Python 3.8 or higher)
- **pip** (Python package installer)
- **Git** (for cloning the repository)

## 🚀 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/AliAbdallah21/AI-Nutrition-Coach.git
cd AI-Nutrition-Coach
```

### 2. Create a Virtual Environment

**On Windows:**
```bash
python -m venv my_env
my_env\Scripts\activate
```

**On macOS/Linux:**
```bash
python3 -m venv my_env
source my_env/bin/activate
```

### 3. Install Dependencies

Create a `requirements.txt` file in your project root with the following content:

```txt
flask
requests
pillow
python-dotenv
openai
```

Then install the dependencies:

```bash
pip install -r requirements.txt
```

## ⚙️ Configuration

### 1. Get OpenRouter API Key

1. Visit [OpenRouter.ai](https://openrouter.ai/)
2. Sign up for an account
3. Navigate to your API keys section
4. Generate a new API key
5. Copy the API key for the next step

### 2. Environment Variables Setup

Create a `.env` file in your project root directory:

```bash
touch .env  # On Windows: type nul > .env
```

Add your OpenRouter API key to the `.env` file:

```env
OPENROUTER_API_KEY=your_openrouter_api_key_here
```

**Important:** 
- Replace `your_openrouter_api_key_here` with your actual API key
- Never commit your `.env` file to version control
- Add `.env` to your `.gitignore` file

### 3. Project Structure

Ensure your project structure looks like this:

```
AI-Nutrition-Coach/
├── app.py                 # Main Flask application
├── requirements.txt       # Python dependencies
├── .env                  # Environment variables (create this)
├── .gitignore           # Git ignore file
├── templates/
│   └── index.html       # HTML template
├── static/
│   └── style.css        # CSS styles
└── README.md            # This file
```

### 4. Create Required Directories

```bash
mkdir -p templates static
```

Move your HTML file to `templates/index.html` and CSS file to `static/style.css`.

## 🎯 Usage

### 1. Start the Application

```bash
python app.py
```

You should see output similar to:
```
 * Running on http://127.0.0.1:5000
 * Debug mode: on
```

### 2. Access the Web Interface

Open your web browser and navigate to:
```
http://localhost:5000
```

### 3. Using the Application

1. **Upload an Image**: Click "Choose an image" and select a food photo
2. **Add a Query** (optional): Modify the default question or ask something specific
3. **Submit**: Click "Tell me the total calories" to analyze the image
4. **View Results**: The AI will provide:
   - Identified food items
   - Portion sizes and calories
   - Total calorie count
   - Detailed nutrient breakdown
   - Health evaluation

## 📁 Project Structure

```
AI-Nutrition-Coach/
├── app.py                 # Main Flask application with routes and logic
├── requirements.txt       # Python package dependencies
├── .env                  # Environment variables (API keys)
├── .gitignore           # Files to ignore in version control
├── templates/
│   └── index.html       # HTML template for the web interface
├── static/
│   └── style.css        # CSS styling for the application
└── README.md            # Project documentation
```

## 🔌 API Information

### OpenRouter Integration

This application uses the OpenRouter API to access Meta's Llama 4 Maverick model:

- **Base URL**: `https://openrouter.ai/api/v1`
- **Model**: `meta-llama/llama-4-maverick`
- **Endpoint**: `/chat/completions`

### Supported Image Formats

- JPEG/JPG
- PNG
- GIF
- BMP
- WebP

## 🛠️ Troubleshooting

### Common Issues

**1. "No module named 'flask'" Error**
```bash
# Ensure virtual environment is activated
pip install -r requirements.txt
```

**2. "OpenRouter API Key not found" Error**
- Check that your `.env` file exists in the project root
- Verify the API key is correctly set in the `.env` file
- Ensure there are no extra spaces or quotes around the API key

**3. "File not found" or Template Error**
- Ensure `templates/` and `static/` directories exist
- Verify `index.html` is in the `templates/` folder
- Check that `style.css` is in the `static/` folder

**4. Image Upload Issues**
- Ensure the uploaded file is a valid image format
- Check that the file size is reasonable (under 10MB recommended)
- Verify your internet connection for API calls

**5. API Rate Limiting**
- OpenRouter has usage limits based on your plan
- Consider implementing request caching for repeated analyses
- Check your OpenRouter dashboard for usage statistics

### Debug Mode

The application runs in debug mode by default, which provides detailed error messages. To disable debug mode for production:

```python
if __name__ == "__main__":
    app.run(debug=False)
```

## 🔒 Security Considerations

- **API Key Security**: Never commit your `.env` file or expose API keys
- **File Upload Security**: The app accepts only image files, but consider additional validation for production
- **Input Sanitization**: User queries are passed to the AI model; consider implementing input validation

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🙏 Acknowledgments

- **OpenRouter**: For providing access to cutting-edge AI models
- **Meta**: For the Llama 4 Maverick model
- **Flask Community**: For the excellent web framework
- **Pillow**: For image processing capabilities

## 📞 Support

If you encounter any issues or have questions:

1. Check the [Troubleshooting](#troubleshooting) section
2. Open an issue on [GitHub](https://github.com/AliAbdallah21/AI-Nutrition-Coach/issues)
3. Review the OpenRouter [documentation](https://openrouter.ai/docs)

---

**Happy Analyzing!** 🍎📊
