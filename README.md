# GridScope — GitHub Pages edition

This standalone browser application runs the trained ANN and LSTM using exported model weights. It needs no Python server or ChatGPT login. Files are processed locally in the browser.

## Publish
1. Create a public GitHub repository named microgrid-forecasting (or use a dedicated existing website repository).
2. Extract this ZIP. Upload its CONTENTS into the repository root. index.html must be at the top level, not inside another folder. Do not upload the ZIP itself.
3. Commit the files to main.
4. Settings > Pages > Build and deployment > Source: Deploy from a branch.
5. Branch: main; Folder: / (root); Save.
6. Wait for the Pages deployment and use the Visit site link provided there. GitHub indicates publishing can take up to 10 minutes.

## Files
index.html — website interface
inference.js — Dense/LSTM inference and CSV validation
model-weights.json — exported trained model weights and fitted preprocessing
microgrid-hourly.csv — 2013 aggregate of the supplied 20-household data
evaluation.json — full held-out test evaluation reproduced from the saved weights
.nojekyll — disables Jekyll processing when included

## Limitations
Dataset origin is unverified. Historical ANN comparisons use observed weather. Future ANN forecasts require next-day weather. Previous-day baseline outperformed both neural models on the held-out test period. Default forecast dates follow the 2013 data, not the current date.

This browser runtime is separate from the local Flask app; keep your original Python project for development and demonstrations.
