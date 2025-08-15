#Scene Localization with Grounding DINO and CLIP

This project provides a simple pipeline to localize Scene in an image using a natural language query. It uses Grounding DINO for open-set object detection and CLIP for re-ranking results, allowing precise localization based on text descriptions.

#Quick start (Colab — recommended)

Open this repository in Google Colab:

Open Colab, then File → Open notebook → GitHub and paste this repo URL.

Navigate to Notebooks/Inference_file.ipynb and open it.

Set Colab runtime to use a GPU (aim for T4):

In Colab choose Runtime → Change runtime type → Hardware accelerator → GPU and click Save.

To confirm GPU type after the runtime starts, run this in a new code cell:

!nvidia-smi


If the shown GPU is not T4, reconnect or restart the runtime and try again until you get a T4 (Colab assigns GPU types; repeated restarts often change the allocation).

Exactly where to add your image & query (paste these lines into the notebook)

Cell 2 — set the image path
Paste this line into Cell 2 (replace the string with the actual path of the image you upload to Colab):

# Cell 2 — paste your uploaded image path here (replace the example path)
IMAGE_PATH = "/content/your_image.jpg"  # <<--- PASTE your uploaded image path between the quotes


How to upload the image in Colab:

Drag-and-drop the file into the left Files pane in Colab


Then use the uploaded filename in IMAGE_PATH, e.g. "/content/myphoto.jpg".

Cell 3 (or the cell that defines queries) — set the query
Find the cell that holds SAMPLE_QUERIES or similar and replace it with the line below 

# Cell 3 — replace with the text query you want to test
SAMPLE_QUERIES = ["a red car on the street"]  # <<--- REPLACE this string with your query



Run the notebook

After setting IMAGE_PATH and SAMPLE_QUERIES, run the notebook cells in order:

Runtime → Run all (or run the cells manually top-to-bottom).

The notebook will:

Install required libraries (if not already installed in the Colab session).

Load your image and run Grounding DINO to get candidate boxes.

Re-rank boxes using CLIP and display the best matches (visualized in the notebook output).

Notes & tips
If you want faster iterations, use Colab Pro for higher chance of getting T4 or faster GPUs.

