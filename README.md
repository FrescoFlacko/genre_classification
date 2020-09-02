# Music Genre Classification Project

This notebook will use various Python libraries to perform build a machine learning model using audio file metadata.

## 1. Problem definition
> Given features extracted from an audio file, can we predict the genre that the audio belongs to

## 2. Data
The data came from the Free Music Archive developed by several people at École Polytechnique Fédérale de Lausann (EPFL) and Nanyang Technological University (NTU). 
The research paper can be found [here](https://arxiv.org/pdf/1612.01840.pdf) and the GitHub repository containing the project files can be found [here](https://github.com/mdeff/fma).

## 3. Evaluation
> If we can reach accuracy that is above the highest benchmark recorded in the research paper, the project is complete.

Here is the benchmarks taken from the FMA research paper:

| Feature set          | LR | kNN | SVM | MLP |
|----------------------|----|-----|-----|-----|
| 1 Chroma             | 44 | 44  | 48  | 49  |
| 2 Tonnetz            | 40 | 37  | 42  | 41  |
| 3 MFCC               | 58 | 55  | 61  | 53  |
| 4 Spec. centroid     | 42 | 45  | 46  | 48  |
| 5 Spec. bandwidth    | 41 | 45  | 44  | 45  |
| 6 Spec. contrast     | 51 | 50  | 54  | 53  |
| 7 Spec. rolloff      | 42 | 46  | 48  | 48  |
| 8 RMS energy         | 37 | 39  | 39  | 39  |
| 9 Zero-crossing rate | 42 | 45  | 45  | 46  |
| 3 + 6                | 60 | 55  | 63  | 54  |
| 3 + 6 + 4            | 60 | 55  | 63  | 53  |
| 1 to 9               | 61 | 52  | 63  | 58  |

The values in the table represent the accuracy % of a feature set and a given model.

The models are defined as:
* LR = Linear Regression with an _L<sup>2</sup>_ penalty
* kNN = k-nearest neighbours with k = 200
* SVM = support vector machines (SVM) with a radial basis function (RBF)
* MLP = multilayer perceptron (MLP) with 100 hidden neurons

## 4. Features
Here are the features that come with each audio file:
- [Chroma](https://en.wikipedia.org/wiki/Chroma_feature)
- [Tonnetz](https://en.wikipedia.org/wiki/Tonnetz)
- [Mel-frequency cepstral coefficients (MFCC)](https://en.wikipedia.org/wiki/Mel-frequency_cepstrum)
- [Spectral centroid](https://en.wikipedia.org/wiki/Centroid)
- [Spectral bandwidth](https://en.wikipedia.org/wiki/Bit_rate)
- [Spectral contrast](https://www.researchgate.net/publication/3968978_Music_type_classification_by_spectral_contrast_feature)
- [Spectral rolloff](https://www.dsprelated.com/freebooks/sasp/Spectral_Roll_Off.html)
- [RMS energy](http://replaygain.hydrogenaud.io/proposal/rms_energy.html)
- [Zero crossing-rate](https://en.wikipedia.org/wiki/Zero-crossing_rate)
