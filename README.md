# Speech-Emotion-Recognition
Audio emotion classification is one of the most challenging task and to solve this we build this deep neural network project.
The deep learning neural network was trained to detect emotion using the Ryerson Audio-Visual Database of Emotional Speech and Song (RAVDESS) dataset which was collected from kaggle.

### Dataset
We have used the [Ryerson Audio-Visual Database of Emotional Speech and Song](https://www.kaggle.com/uwrfkaggler/ravdess-emotional-speech-audio) (RAVDESS) which contains 7356 files (total size: 24.8 GB). The database contains 24 professional actors (12 female, 12 male), vocalizing two lexically-matched statements in a neutral North American accent. Speech includes calm, happy, sad, angry, fearful, surprise, and disgust expressions, and the song contains calm, happy, sad, angry, and fearful emotions. Each expression is produced at two levels of emotional intensity (normal, strong), with an additional neutral expression. 
<img src="https://user-images.githubusercontent.com/53137708/129469464-03943c07-47e7-4989-8465-84979f8c4d46.png"/>

### Feature Extraction

For training the model we have converted the Audio singals into various Spectograms, check out this amazing [playlist](https://www.youtube.com/watch?v=iCwMQJnKk2c&list=PL-wATfeyAMNqIee7cH3q1bh4QJFAaeNv0) for an indepth understanding.
#### 1. SPECTOGRAM 

&emsp;Spectrogram is a visual representation of the spectrum of frequencies of a signal as it varies with time. When applied to an audio signal, spectrograms are sometimes called sonographs, voiceprints, or voicegrams. When the data are represented in a 3D plot they may be called waterfalls.

<p align="center">
  <img src="https://user-images.githubusercontent.com/53137708/129469778-edcad6ba-a938-4b1f-894f-9f9c0cfe4c59.png" width="550" height="200"/>
</p>

#### 2. MEL-SPECTOGRAM

&emsp;Mel Spectrograms are spectrograms that visualize sounds on the Mel scale as opposed to the frequency domain.

<p align="center">
  <img src="https://user-images.githubusercontent.com/53137708/129469803-d24cd261-4493-4729-9696-110ce6b7e7b7.png" width="550" height="200"/>
</p>

#### 3. MEL-FREQUENCY CEPSTRUM COEFFICIENTS

&emsp;Mel-frequency cepstral coefficients (MFCCs) are coefficients that collectively make up an MFC. They are derived from a type of cepstral representation of the audio clip (a nonlinear "spectrum-of-a-spectrum").

<p align="center">
  <img src="https://user-images.githubusercontent.com/53137708/129469822-ae052d66-6a72-4d66-8ead-45a6f820bc00.png" width="550" height="200"/>
</p>

### Model
In this project we have used the pretrained ResNet18 network for making the prediction by replacing it's first and last layers, even though it was not trained on the audio data still it produced decent results after training. 

 We used the one cycle learning rate between lower bound and upper bound during complete run. Conventionally, the learning rate is decreased as the learning starts converging with time. As the higher learning rate may help to get out of saddle points. If saddle point is elaborate plateau, the lower learning rates might not be able get gradient out of saddle point. - [Paper link](https://arxiv.org/pdf/1506.01186.pdf)
 
<p align="center">
  <img src="https://user-images.githubusercontent.com/53137708/129469499-347a5fde-b686-4d90-8a20-a50abab15aef.png" width="1200" height="300"/>
</p>

### Results
We started with raw Audio data and applied various techniques of Deep learning and preprocessing on it to convert it into a format which we can use for classification and then created a model which is capable of predicting the emotion in the audio file just by taking it as input with an accuracy of 76%.
<p align="center">
  <img src="https://user-images.githubusercontent.com/53137708/129469532-8f79b187-ad4a-4701-96ea-301c561b5b12.png" width="1200" height="400"/>
</p>
