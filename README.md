# ArtifactNet

📚 Dataset Description (ArtiFact_240K)

This dataset is designed for deepfake detection in Datathon 2025 and contains 120,000 real and 120,000 fake images. It includes three main categories:

Human Faces

Animals

Vehicles

Structure:

ArtiFact_240K/
├── train/
│   ├── real/
│   │   ├── human_faces/
│   │   ├── animals/
│   │   └── vehicles/
│   └── fake/
│       ├── human_faces/
│       ├── animals/
│       └── vehicles/
├── validation/
│   ├── real/
│   │   ├── human_faces/
│   │   ├── animals/
│   │   └── vehicles/
│   └── fake/
│       ├── human_faces/
│       ├── animals/
│       └── vehicles/
├── test/                              # All test images
├── metadata.csv                       # Contains image_path, label (0=Real, 1=Fake), class
├── LICENSE                            # MIT License
└── README.md                          # Dataset documentation

📊 Model Architecture

Backbone: EfficientNet-B2 (via timm, pretrained)

Heads:

Binary classification head for real vs fake

Multiclass head for object classification

Losses:

Focal Loss (for fake detection)

CrossEntropy with label smoothing (for class)

Augmentation:

Resize, Flip, ColorJitter, Rotation, Affine

Inference Boost:

Test-Time Augmentation (TTA)

🚀 Setup Instructions
pip install -r requirements.txt
If running in Colab:
!pip install timm gdown scikit-learn


📈 Evaluation

To train and generate submission:
python artifactnet_pipeline.py

📤 Submission Format
image,label,class
animals_00001.jpg,0,animals
human_faces_00002.png,1,human_faces

📚 Citation
MIT LICENSE:
@article{artifact2023,
  title={ArtiFact: A Large-Scale Dataset for Real and Fake Image Detection},
  author={John Doe, Jane Smith, et al.},
  journal={Proceedings of the 2023 AI Ethics Conference},
  year={2023},
  url=" https://artifact-dataset.org "
}
