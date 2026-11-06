# Simple Transfer of Facial Gestures with Appearance

A linear algebra project that transfers facial gestures from one person to another. It detects facial landmarks, aligns face shapes, learns a PCA model, tracks a gesture video, and reconstructs the motion using a reference face's appearance.

**Creators:** [Mehrshad Hosseini](https://www.linkedin.com/in/mehrshadhosseini28/) and [Hanie Masumi](https://www.linkedin.com/in/hanie-masumi/)

**Date:** February 2022

[Open in Google Colab](https://colab.research.google.com/github/ConnectWithMehrshad/linear-algebra-project/blob/master/Simple_Transfer_of_Facial_Gestures_with_Appearance_(Linear_Algebra_Project).ipynb)

## Contents

- `Simple_Transfer_of_Facial_Gestures_with_Appearance_(Linear_Algebra_Project).ipynb`: Main notebook.
- `Mehrshad.zip`: 67 reference face images.
- `Hanie.zip`: One reference image and one gesture video.

## Pipeline

1. Detect 68 facial landmarks with dlib.
2. Center and register faces using similarity and affine transforms.
3. Learn a 16-component PCA face model using SVD.
4. Track landmarks in the gesture video and project them into PCA space.
5. Warp the reference appearance using Delaunay triangulation and barycentric coordinates.

## Run in Colab

Open the notebook link, then run all cells from top to bottom. The notebook downloads the dlib landmark model and extracts the two data archives automatically.

The archive download cells use an older GitHub username. If they fail, replace their URLs with:

```python
!wget https://github.com/ConnectWithMehrshad/linear-algebra-project/raw/master/Mehrshad.zip
!unzip -q /content/Mehrshad.zip
!wget https://github.com/ConnectWithMehrshad/linear-algebra-project/raw/master/Hanie.zip
!unzip -q /content/Hanie.zip
```

## Dependencies

```bash
pip install numpy scipy matplotlib tqdm opencv-python dlib jupyter
```

Local execution also requires `shape_predictor_68_face_landmarks.dat`, extracted archives, and path updates from `/content/...` to local paths. Colab is recommended because dlib installation and interactive animations may require extra configuration locally.

## Limitations

The detector expects a frontal face in every frame. The project has no pinned requirements, tests, CLI, or license file. The landmark model is downloaded from dlib and has separate licensing terms.
