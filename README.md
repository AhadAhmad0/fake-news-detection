# Fake News Detection Web App

A Flask web app that classifies a news article as Real or Fake. You paste in the text, and a TF-IDF and Logistic Regression model gives its answer on the page.

**Live demo:** https://fake-news-detection-project-ahad5.onrender.com

The app runs on Render. If it has been idle, the first load may take a while to start.

---

## How it works

1. You paste a news article into the web page.
2. The text is cleaned: noise and extra characters are removed.
3. TF-IDF turns the text into numbers.
4. A Logistic Regression model predicts Fake or Real.
5. The result is shown on the page.

The model is trained from the CSV files when the app starts. It is not saved as a separate file.

## Limitations

- The model learns patterns in how real and fake articles are written. It does not check whether the claims are true.
- It is trained on one dataset, so it may do badly on news from other topics, countries or years.
- On datasets like this, real and fake articles often differ in simple ways, such as the name of the source or the formatting. A high score can come from those clues and not from understanding the news.
- Training at startup makes the app slower to start than loading a saved model.

## Dataset

The project uses a dataset of real and fake news articles. The full dataset is large, so the repo uses a sampled version: `Fake_small.csv` and `True_small.csv`. This keeps the app light on Render and the training at startup short. The smaller sample may lower accuracy compared with the full dataset.

## Tech stack

- Python
- Flask
- Pandas, NumPy
- scikit-learn (TF-IDF, Logistic Regression)
- HTML and CSS
- Render for hosting

## Project structure

```
├── app.py                  # Flask backend and ML code
├── templates/
│   └── index.html          # Web page
├── Fake_small.csv          # Sampled fake news data
├── True_small.csv          # Sampled real news data
├── requirements.txt        # Dependencies
└── runtime.txt             # Python version for Render
```

## Run locally

```bash
git clone https://github.com/AhadAhmad0/fake-news-detection
cd fake-news-detection

pip install -r requirements.txt
python app.py
```

Then open the local address that Flask prints in the terminal.

## Author

Ahad Ahmad
- GitHub: [@AhadAhmad0](https://github.com/AhadAhmad0)
- LinkedIn: [linkedin.com/in/ahadahmad7](https://linkedin.com/in/ahadahmad7/)
