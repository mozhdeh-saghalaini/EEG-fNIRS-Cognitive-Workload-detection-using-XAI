**Cognitive Workload Classification via EEG-fNIRS Data**
This pipeline is built for simultaneous EEG and fNIRS data from an n-back working memory task. The goal is to prepare multimodal data for a transformer-based cognitive laod classifier (3 levels: 0-back, 2-back, 3-back).

**Dataset**
Reference: Shin et al., (2018). Science Data, 5, 180003
Participants: 26 healthy subjects (26.1±3.5 years)
Task: n-back with three levels: 0-back (low), 2-back (medium), 3back (high load)
Structure per subject: 3 sessions × 3 series × 20 trials × 3 levels = 540 tirals total

**Preprocessing Steps**
EEG: Filter (1-45Hz), Notch (50Hz), ICA (infomax), Epoch (0-3)
fNIRS: Wavelet denoising, MARA, MBLL (HbO/HbR), Bandpass (0.01-0.1Hz), Downsampling to 10Hz, Spatial map to 16×16 grid
Synchronization: Matching session markers between EEG and fNIRS (EEG has 567 markers, fNIRS has 27). Offsets vary per session block (-16s, -62s, -110s)

**Next Steps**
1. Data Fusion (EEG + fNIRS tensors)
2. Transformer model
3. XAI

**Data Reference**
Shin, J., von Lühmann, A., Kim, D.W., et al. (2018). Simultaneous acquisition of EEG and NIRS during cognitive tasks for an open access dataset. Scientific Data, 5, 180003.

