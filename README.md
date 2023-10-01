
# Face Matching Flask API

This is a simple Flask API that matches a provided face (via an image URL) with a dataset of known criminals and returns the best match, if any.

## Features

1. GET request on root displays a welcome message.
2. POST request to `/api/matchface` with a JSON body containing an `imgUrl` field will download the image, extract the face embedding, and compare it against known criminals from a CSV database to find the best match.

## Setup & Installation

### Prerequisites

- Python 3.x
- pip

### Steps

1. Clone this repository:
   ```
   git clone https://github.com/Lokesh4152/facematch.git
   cd facematch
   ```

2. Install the required packages:
   ```
   pip install Flask requests DeepFace pandas numpy
   ```

> **Note**: Ensure that you have the necessary dependencies (e.g., DeepFace) set up correctly. Refer to the respective documentation for any setup details.

3. You'll need a `criminal.csv` file in the root directory of the project. This CSV file should contain embeddings of known criminals. The first column should be labels (names) of the criminals, followed by embedding values.

### Running the Application

Start the Flask server:

```
python application.py
```

This will run the server on `http://127.0.0.1:8000/`.

## Usage

1. **Test the API**:
   Open your browser or API testing tool like Postman, and visit `http://127.0.0.1:8000/`. This should return a welcome message.

2. **Face Matching**:
   Make a POST request to `http://127.0.0.1:8000/api/matchface` with a JSON body like:
   ```json
   {
       "imgUrl": "https://example.com/path/to/your/image.jpg"
   }
   ```

   The response will either show the best match from the criminal database or state that no match was found.

## Contributions

Contributions, issues, and feature requests are welcome!



---

