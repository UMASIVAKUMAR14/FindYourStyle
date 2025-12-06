# FindYourStyle
Image Classification of Clothing by Type and Style

## 1. Project Title
**Find Your Style: Image Classification of Clothing by Type and Style**

## 2. Names
- Liya Fasil  
- Uma Sivakumar  
- Haimanot Belachew

## 3. Problem statement
Everyone has that moment in the morning when they have 5 minutes to get dressed and they can’t find anything to wear. It is tiring to go digging around in your closet when you are in a rush. One solution is to create a digital store of what clothing a person owns, so they don’t have to go digging around the depths of their closet to decide what to wear. The first step to creating this digital store is to train a model to classify clothing by type and style. This is what we would like to address with our project.

## 4. General approach
Our project aims to create a system that can automatically identify the type and style of a clothing item from an image. Using the **DeepFashion-MultiModal** dataset, which provides labeled images of different clothing types (like shirts, skirts, dresses, and jackets) along with attributes describing their color, fabric, and shape, we will train a multi-head classifier model to sort clothing images into the correct type and a set of style attributes (fabric, color, shape).

### Multi-head structure
- **Head A:** Type  
- **Head B:** Color  
- **Head C:** Fabric  
- **Head D:** Shape

Given a parsed clothing image, the system will analyze its features and assign labels such as:  
`dress – floral pattern – cotton fabric – short length`

To make this possible, we will:
- Convert the categorical labels for clothing type and style attributes into numerical feature vectors suitable for training classification models.
- Represent each image by a feature vector extracted from its attributes and visual features.
- Train the multi-head classifier to output predictions for type, color, fabric, and shape.
- Evaluate accuracy for each head and produce confusion matrices to observe where the model fails most frequently.

**Reach goal:** extend into a simple recommendation system. By creating a *style embedding* (concatenate image embedding + attribute vectors), we can compare a user’s uploaded image with dataset embeddings and recommend similar clothing.

### Challenges
- Adapting the model to handle different lighting conditions.  
- Different poses of the models wearing the clothes may affect classification.  
- Clothes layered over each other — the model must classify based on visible regions.

## 5. Data
Dataset: DeepFashion-MultiModal  
Repository / README: https://github.com/yumingj/DeepFashion-MultiModal?tab=readme-ov-file

- The dataset contains **44,096** high-resolution human images with manually annotated attributes for clothing shapes and textures.
- It includes parsing by clothing type (e.g., skirt, dress, top, tie), which enables prediction of individual clothing items.
- The dataset already has numerical annotations for shape, color, and fabric, giving quantitative style labels.
- It is well-formatted and commonly used in research, so labels and images are reasonably trustworthy.

## 6. Measure of success
We aim to build an application that, given an article of clothing, recognizes its type and style.

Project goals:
1. Classify images into clothing types.  
2. Classify images into clothing styles (color, fabric, shape) within each type.

**Success criteria**
- ≥ 70% accuracy on clothing type classification (test set).  
- Of images correctly classified by type, ≥ 70% accuracy on color and fabric classification.  
- Shape classification will be experimental and may have different accuracy targets.

## 7. Milestones and deliverables

### Milestones
- **1:** Set up repository, local environment, data loading, and parsing.  
- **2:** Baseline training of a multi-head classification model (heads: type, shape, color, fabric).  
- **3:** Improve robustness (random brightness/contrast/noise). Implement hyperparameter tuning.  
- **4 (Reach goal):** Define style embeddings by concatenating image embeddings with attribute vectors. Implement similarity search to find most similar images.  
- **5:** Detailed report of findings.

### Deliverables
- A trained model that, given an image with correct parsing, classifies clothing into types and styles.  
- **Reach Goal:** A basic retrieval/recommendation function that finds similarly styled clothes within the same type.
