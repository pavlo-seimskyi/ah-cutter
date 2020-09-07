# ah-cutter
Ah-cutter software has been the absolute dream of every podcaster. Never edit the "ahhhh", "ummm", "hmmm", and other filler sounds manually again!

## Environment
```
conda create -n audio --file requirements.txt
```

## Jupyter Notebook
```
python -m ipykernel install --user --name=audio
```
Now you can activate this environment as kernel in Jupyter Notebooks.

![Selecting kernel](/docs/jupyter-kernel.png)

## Part 1 - Preparing the data (clean-16khz.ipynb)
In the first notebook, audiofiles are transformed from time domain into frequency domain creating Fourier Transform spectrograms. Class 0 represents audio that is not a filler sound and class 1 an audio that contains "ah", "uhm" or similar. Audiofiles of different lengths in folders `audiofiles/0` and `audiofiles/1` get cut into chunks of 0.1 seconds and saved in `audiofiles_chunks/0` and `audiofiles_chunks/1` respectively. Then, each audio chunk gets transformed into a spectrogram that is saved in `images/0` and `images/1`, respectively.

![Spectrogram](/docs/spectro-preview.jpg)

## Part 2 - Training the model (training.ipynb)
In the second notebook, a resnet34 CNN pretrained model is fine-tuned.


