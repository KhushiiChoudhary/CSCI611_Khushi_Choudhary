
# Assignment 4: Neural Style Transfer

Implementation of neural style transfer based on Gatys et al. (2016) using a pretrained VGG19 network in PyTorch.

---

## How to Run

1. Open `Style_Transfer_Exercise.ipynb` in Google Colab
2. Enable GPU: **Runtime → Change runtime type → T4 GPU**
3. Upload your content and style images to the Colab session
4. Update the image paths in the **Load the images** cell:
```python
content = load_image('content.jpg').to(device)
style = load_image('style_starry_night.jpg', shape=content.shape[-2:]).to(device)
```
5. Run all cells in order — Part 2 experiments run automatically

---

## File Structure

```
Assignment_4/
├── Images used/                    # Content and style images
├── Style_Transfer_Exercise (1).ipynb  # Main notebook (Part 1 + Part 2 experiments)
├── Assignment4_Report.pdf          # Written report with findings and visualizations
└── Readme.md                       # This file
```
