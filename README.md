# Pokémon Color Classifier 

This project demonstrates a complete computer vision pipeline for classifying Pokémon images by their primary color using deep learning. The workflow is implemented in the Jupyter notebook [`ACM_aiml.ipynb`](ACM_aiml.ipynb).

## Overview

- **Objective:**  
  Automatically predict the color of a Pokémon given its image, using a Convolutional Neural Network (CNN) trained on official Pokémon artwork and color labels obtained from the PokeAPI.

- **Data Used:**  
  A zip archive of Pokémon images (PNG format) organized in folders.  
  Color labels are retrieved programmatically for each Pokémon using their Pokédex ID and the [PokeAPI](https://pokeapi.co/).

- **Main Steps:**  
  1. **Data Upload & Extraction:**  
     - Upload a zip file (`archive (7).zip`) containing Pokémon images.
     - Extract images to a working directory.

  2. **Image Discovery:**  
     - Recursively list all PNG images within the extracted directories.

  3. **Label Generation:**  
     - For each image, parse the Pokémon ID from its filename.
     - Query the PokeAPI for the corresponding color label.
     - Save results as a CSV file for further processing.

  4. **Preprocessing:**  
     - Create a DataFrame linking image paths to color labels.
     - Encode labels numerically.
     - Split data into training and validation sets.

  5. **Data Augmentation:**  
     - Use Keras `ImageDataGenerator` for real-time image augmentation during training.

  6. **Model Building:**  
     - Construct a simple CNN in Keras/TensorFlow.
     - Train the model with early stopping based on validation loss.

  7. **Evaluation:**  
     - Monitor training/validation accuracy and loss.
     - The model can be further evaluated or deployed for inference.

## How to Run

1. **Open the Notebook:**  
   Launch the notebook in [Google Colab](https://colab.research.google.com/) for best compatibility.

2. **Upload Data:**  
   - Upload the Pokémon image archive when prompted (`archive (7).zip`).
   - The notebook will extract and process the images automatically.

3. **Run All Cells:**  
   - Execute each cell in order, or use "Runtime > Run all".
   - The notebook will fetch Pokémon color data, build the dataset, augment, train, and evaluate the model.

4. **Results:**  
   - The trained model will classify images into one of 10 color categories (e.g., pink, yellow, blue, etc.).
   - Intermediate CSVs and logs show labeling accuracy and model progress.

## Requirements

- **Python Libraries:**  
  - `tensorflow` (Keras)
  - `pandas`
  - `numpy`
  - `requests`
  - `scikit-learn`
  - `google.colab` (for file upload, if using Colab)

- **External Data:**  
  - Pokémon image zip archive
  - Internet connection (for PokeAPI queries and Colab execution)

## Example Output

- **CSV Preview:**

  | Pokemon         | Color  |
  |-----------------|--------|
  | 585-autumn.png  | pink   |
  | 40.png          | pink   |
  | 460.png         | white  |
  | ...             | ...    |

- **Model Summary:**  
  The CNN consists of two convolutional layers, pooling, dense, and dropout, finishing with a softmax for multi-class output.

- **Training Log:**  
  Loss and accuracy are printed per epoch, with early stopping if validation loss doesn't improve.

## Customization

- Model architecture and augmentation parameters can be adjusted in the notebook.
- The labeling function can be modified to use other attributes from PokeAPI.

## Credits

- **Data:**  
  Pokémon images & names © Nintendo, Game Freak, The Pokémon Company.  
  Color labels via [PokeAPI](https://pokeapi.co/).

- **Notebook Author:**  
  [Diptesh2006](https://github.com/Diptesh2006)

## License

This project is for educational use only. Pokémon and its images are intellectual property of their respective owners.

---
**Happy Learning!**
