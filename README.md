# Cats & Dogs Classifier 🐱🐶

A web application that uses machine learning to classify images as cats or dogs. Built with Flask and TensorFlow Lite, deployed on Render for easy access.

## 🎯 Features

- **Image Classification**: Upload an image and get instant predictions (Cat or Dog)
- **AI-Powered**: Uses a pre-trained TensorFlow Lite model from Hugging Face
- **User-Friendly Web Interface**: Simple and intuitive UI built with HTML/CSS
- **Fast Inference**: Optimized TFLite model for quick predictions
- **Confidence Score**: Displays the prediction confidence level

## 🚀 Live Demo

Try the application online: https://iagorivadulla-flask-cats-dogs.onrender.com/

## 📁 Project Structure

```
.
├── src/
│   ├── app.py              # Flask application & routes
│   ├── utils.py            # Helper functions
│   ├── explore.ipynb       # Notebook for experimentation
│   └── templates/
│       └── index.html      # Web interface
├── data/
│   ├── raw/                # Raw datasets
│   ├── interim/            # Intermediate processed data
│   └── processed/          # Final processed data
├── models/                 # Model storage
├── requirements.txt        # Python dependencies
└── Procfile               # Deployment configuration
```

## 🛠️ Tech Stack

- **Flask** - Web framework
- **TensorFlow Lite** - Machine learning inference
- **Hugging Face Hub** - Model hosting
- **Pillow** - Image processing
- **NumPy** - Numerical computations
## ⚡ Quick Start

### Prerequisites
- Python 3.11 or higher
- pip (Python package manager)

### Local Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd flask-cats-dogs-classifier
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Flask application**
   ```bash
   python src/app.py
   ```

4. **Open your browser** and navigate to:
   ```
   http://localhost:5000
   ```

## 💻 Usage

1. **Access the web interface** - Open the application in your browser
2. **Upload an image** - Click to select or drag a cat or dog image
3. **Get prediction** - The model will classify the image and show:
   - The predicted class (Cat or Dog)
   - Confidence percentage

## 🔧 How It Works

1. **Image Upload** - User selects an image from their device
2. **Preprocessing** - Image is resized to 200x200 pixels and normalized
3. **Model Inference** - TensorFlow Lite model processes the image
4. **Prediction** - Returns the class with highest confidence score
5. **Display Result** - Shows prediction and confidence to the user

## 📦 Dependencies

See `requirements.txt` for the complete list:
- Flask 3.1.0
- TFLite Runtime 2.14.0
- Hugging Face Hub 0.24.6
- NumPy 1.26.4
- Pillow

## 🤖 Model Information

- **Framework**: TensorFlow Lite (optimized for inference)
- **Input Size**: 200x200 RGB images
- **Output**: Binary classification (Cat or Dog)
- **Model Source**: [Hugging Face - jamirc/cat_dog_classifier](https://huggingface.co/jamirc/cat_dog_classifier)
- **Advantages**: Fast inference, small file size, perfect for web deployment

## 🚀 Deployment

This project is configured for deployment on Render with the included `Procfile`. To deploy your own version:

1. Connect your GitHub repository to Render
2. Render will automatically install dependencies from `requirements.txt`
3. The application will start using the Procfile configuration
4. Your app will be live at a unique Render URL

## 📝 API Endpoints

### GET /
Returns the main web interface (HTML page)

### POST /predict
Accepts an image file and returns a JSON response with prediction

**Request**: 
- Method: POST
- Content-Type: multipart/form-data
- Parameter: `file` (image file)

**Response**:
```json
{
  "class": "Cat",
  "confidence": 0.95
}
```

```makefile
DATABASE_URL="postgresql://<USER>:<PASSWORD>@<HOST>:<PORT>/<DB_NAME>"

#example
DATABASE_URL="postgresql://my_user:my_password@localhost:5432/my_database"
```

## Running the Application

To run the application, execute the app.py script from the root directory of the project:

```bash
python src/app.py
```

## Adding Models

To add SQLAlchemy model classes, create new Python script files within the models/ directory. These classes should be defined according to your database schema.

Example model definition (`models/example_model.py`):

```py
from sqlalchemy.orm import declarative_base
from sqlalchemy import String
from sqlalchemy.orm import Mapped, mapped_column

Base = declarative_base()

class ExampleModel(Base):
    __tablename__ = 'example_table'
    id: Mapped[int] = mapped_column(primary_key=True)
    username: Mapped[str] = mapped_column(unique=True)
```

## Working with Data

You can place your raw datasets in the data/raw directory, intermediate datasets in data/interim, and processed datasets ready for analysis in data/processed.

To process data, you can modify the app.py script to include your data processing steps, using pandas for data manipulation and analysis.

## Contributors

This template was built as part of the [Data Science and Machine Learning Bootcamp](https://4geeksacademy.com/us/coding-bootcamps/datascience-machine-learning) by 4Geeks Academy by [Alejandro Sanchez](https://twitter.com/alesanchezr) and many other contributors. Learn more about [4Geeks Academy BootCamp programs](https://4geeksacademy.com/us/programs) here.

Other templates and resources like this can be found on the school's GitHub page.
