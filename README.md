# Deep Learning-Based Urban Sound Classification and Acoustic Analysis

Capstone project by Arya. B. Nair and Jesuva Abishek. R.

A pipeline that tags urban sound sources in short audio clips, analyses patterns by time and place, flags unusual recordings, and presents results in a dashboard.

## What is in this repository
| Path | Contents |
|---|---|
| `notebooks/Urban_Sound_Classification_Colab.ipynb` | The whole project as a Google Colab notebook: dataset build, log-Mel features, Model A (small CNN), Model B (frozen PANNs CNN14 + sigmoid head), evaluation, pattern analysis, Isolation Forest screening, dashboard, and a "report evidence" section (baselines, seeds, ablations, latency, robustness). |
| `site/index.html` | Static showcase website. Load the `predictions.csv` saved by the notebook to see accuracy, per-class results, confusion matrix and a clip browser; includes a live log-Mel spectrogram lab. |
| `samples/` | **Synthetic demo files only** (fake scores, computer-made audio) for trying the website. They are not results of the model. |

There is no separate backend server: the training and inference code lives in the notebook, and the website is static.

## Run it
1. Open the notebook in Google Colab (`File > Upload notebook`, or `File > Open notebook > GitHub`).
2. Runtime > Change runtime type > T4 GPU (recommended; CPU also works).
3. Run all. The first run downloads ESC-50 (about 600 MB), builds the 10-class *Urban-10* subset and stores it in `MyDrive/UrbanSoundMini/`.
4. Download `predictions.csv` from that Drive folder and load it in the website.

## View the website
Open `site/index.html` in a browser, or enable GitHub Pages (Settings > Pages > deploy from branch, folder `/site` is not selectable, so move `index.html` to `/docs` or the repo root first).

## Data and licences
Urban-10 is a subset of ESC-50 (K. J. Piczak, 2015; CC BY-NC, non-commercial). The backbone is PANNs CNN14 (Kong et al., 2020). Check each licence before any commercial use. Add a licence for your own code before publishing.

## Results
Measured results are produced by running the notebook (Sections 7 and 14). None are hard-coded in this repository.
