<img src="http://imgur.com/1ZcRyrc.png" style="float: left; margin: 20px; height: 55px">

# DSI-SG-42

## Capstone Project: Harmony

> Authors: Eugene Matthew Cheong

---

## Executive Summary

---

This project is designed to assist interior designers by optimizing the selection of interior design products. It compiles a detailed catalogue of items such as tiles, laminates, and paints, and employs cosine similarity calculations to find and suggest products that closely match desired colors. This feature enhances the ability to match color palettes with precision, catering to client preferences and design requirements.

Additionally, the system includes an image matching feature, which allows designers to upload images provided by clients or photos of spaces to be redesigned. It automatically identifies and suggests corresponding products from the catalogue. This capability ensures that designers can efficiently align client expectations with the available inventory, thereby streamlining the design process.

## Problem Statement

---

George has spent eight years designing beautiful homes, adjusting to different client preferences. Despite his experience, he often finds it difficult to start new projects because of the vast array of products and colours available. He also struggles to understand what clients want from their text messages alone. George needs a way to simplify the beginning of his design projects and better grasp client needs.

How can we help interior designers recommend designs more efficiently?

## Approach

---

By using arecommendation system, it will be tailored to support interior designers by suggesting products based on an initial color or product choice. The system begins by analyzing the color characteristics of the chosen item. Utilizing cosine similarity calculations, it identifies products within our comprehensive catalogue that have similar color properties.

Once a base color or product is selected, the system generates a color palette that harmonizes with the initial choice. This palette serves as a guide for interior designers, enabling them to recommend a range of products that not only match but also complement the core color scheme.

This approach ensures a cohesive aesthetic across the design project, allowing designers to confidently match products with the overall style and color preferences of their clients. The documentation provided here explains the technical and practical aspects of this approach, offering a clear pathway for designers to leverage the system's capabilities effectively.

## Data Dictionary

---

- liansenghin_df.csv
- hafary_df.csv
- lamitak_df.csv

| Feature        | Type    | Description                  |
| -------------- | ------- | ---------------------------- |
| Model Name     | object  | Model name of the product    |
| Product URL    | object  | URL link for the product     |
| Filename       | object  | File name for the image      |
| Company        | object  | Company selling the product  |
| Type           | object  | Type of product              |
| Application    | object  | Where the product is applied |
| Category Tags  | object  | Description details          |
| Origin Country | object  | Where the product was made   |
| Width (cm)     | object  | Width of the product         |
| Height (cm)    | float64 | Height of the product        |

nippon_df.csv

| Feature        | Type    | Description                   |
| -------------- | ------- | ----------------------------- |
| Application    | object  | Where the product is applied  |
| Category Tags  | float64 | Description details           |
| Color B        | float64 | Value of Blue of the product  |
| Color Code     | object  | Hexcode of the product        |
| Color G        | float64 | Value of Green of the product |
| Color R        | float64 | Value of Red of the product   |
| Company        | object  | Company selling the product   |
| Model Name     | object  | Model name of the product     |
| Model Number   | object  | Model number of the product   |
| Origin Country | float64 | Where the product was made    |
| Product URL    | object  | URL link for the product      |
| Type           | object  | Type of product               |
| Filename       | object  | File name for the image       |

all_products_df.csv

| Feature        | Type   | Description                  |
| -------------- | ------ | ---------------------------- |
| Model Name     | object | Model number of the product  |
| Company        | object | Company selling the product  |
| Type           | object | Type of product              |
| Origin Country | object | Where the product was made   |
| Application    | object | Where the product is applied |
| Filename       | object | File name for the image      |

color_palette_df.csv

| Feature | Type   | Description               |
| ------- | ------ | ------------------------- |
| Name    | object | Name of the color palette |
| Color 1 | object | Hexcode of the Color 1    |
| Color 2 | object | Hexcode of the Color 2    |
| Color 3 | object | Hexcode of the Color 3    |
| Color 4 | object | Hexcode of the Color 4    |

---

## Limitations

---

- Inability to accurately detect complex patterns or identify products with multiple colors.
- Recommendation System is computationally expensive because of the amount of data is in the image per product.
- There are no controls to set the tone/temperature.
- Limitations exist in defining the context's scope and boundaries. Occasionally, the LLM might supplement its responses with additional information.
- Catalogue dataset is not clean. When scraping, there are a lot of images that are not images of the product.

## Recommendations

---

1. More Resources for Data Collection and Cleaning:

   - Expand the dataset by collecting more diverse examples of materials and products. Gathering images that showcase a variety of material types and products with complex patterns and multi-coloured designs to improve the system’s recognition and classification capabilities.
   - Replace the incorrect images of the products to the proper images of the product to allow the recommendation system to recommend.

2. Implement Advanced Image Recognition Technologies:
   Integrate more sophisticated image processing algorithms that can handle complex patterns and multi-color detection more effectively. Consider using deep learning models trained specifically for material recognition and pattern analysis.

3. Explore Retrieval-Augmented Generation (RAG) for LLM:
   Investigate the potential of RAG to enhance the LLM's performance. By integrating a retrieval mechanism, the LLM can access a broader knowledge base during generation, allowing for more contextually relevant and updated responses. This approach would be particularly beneficial in cases where dynamic data and evolving trends influence design decisions.

## Conclusions

---

By automating the task of matching and suggesting interior design products, the system not only saves time but also introduces a level of precision in aligning with client preferences that manual processes cannot easily achieve.

However, recognizing the limitations in pattern recognition and material classification, it is clear that continued improvements and updates are necessary to maintain and enhance the system's effectiveness. By implementing the recommended actions, we can ensure that the system evolves in line with advancements in technology and changes in design trends, thereby providing enduring value to interior designers and their clients.

Through these efforts, we will support interior designers in overcoming the initial difficulties and efficiently navigating client preferences, ultimately leading to more inspired and harmonious design solutions.

### Files

---

**Code**

- 1.1_web_scraping_liansenghin.ipynb
- 1.2_web_scraping_hafary.ipynb
- 1.3_web_scraping_lamitak.ipynb
- 1.4_web_scraping_nippon.ipynb
- 1.5_consolidate_product_database.ipynb
- 2.1_processing_canva_palette.ipynb
- 3.1_matching_input_photo_to_products.ipynb
- 3.2_recommending_canva_palette_to_product.ipynb
- 3.3_recommending_colours_and_colour_palettes_with_llama3.ipynb

**Datasets**

- all_products_df.csv
- color_palette_df.csv
- hafary_df.csv
- lamitak_df.csv
- liansenghin_df.csv
- nippon_df.csv

** H5 Files **

- preprocessed_all_images.h5
- preprocessed_canva_palettes.h5

Could not pushed to GitHub because the file sizes are too large. So I have placed them in Google Drive.
You can find them in the link below and placed it in the '/datasets/h5' folder:

- https://drive.google.com/drive/folders/1WKyZLdANYvIYwXb_LjLqd52vIHx5RsoV?usp=sharing

- README.md

---
