# Anapneo — audio-only sleep-apnea screening (Google Colab)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ayaanmaheshwari/anapneo-colab/blob/main/Anapneo_Colab.ipynb)

A CNN + CRNN ensemble trained on the **APSAA** full-night audio dataset, served
by the **Anapneo** Flask dashboard: upload or pick a night and get a 10-second
event timeline, KPI cards, a severity gauge, an AI-written summary and a
doctor-ready PDF.

## Run it

1. Click the **Open in Colab** badge above (or upload `Anapneo_Colab.ipynb`).
2. `Runtime → Change runtime type → T4 GPU`.
3. Run cells 1 → 7. Cell 3 downloads `anapneo_colab.zip` from this repo and
   extracts it; cell 7 starts the dashboard and shows it inline.
4. Optional: paste a Google **Gemini API key** in the dashboard header for the
   AI report and chat. Without a key the deterministic built-in text is used.

`anapneo_colab.zip` contains the project code, the trained weights
(`checkpoints/best_cnn.pt`, `best_crnn.pt`, `norm.json`) and two 20-minute demo
clips. No dataset download is required; upload your own WAV/MP3 to analyse it.

## Notes

- The ensemble runs on the Colab GPU; a 20-minute clip analyses in ~15 s.
- The Colab proxy link only lives while the launch cell is running.
- Research prototype only — audio cannot measure airflow or SpO₂, so this is a
  pre-screening aid and never a diagnosis.
