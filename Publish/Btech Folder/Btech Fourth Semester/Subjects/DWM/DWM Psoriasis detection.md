---
Title: DWM Psoriasis detection
Status: 
marker:
  - "[[project]]"
tags: 
Date: 2025.02.17
Time: 15:09
---
# DWM Psoriasis detection
Sources:
- https://ieeexplore.ieee.org/abstract/document/8448609/?casa_token=L0ZSF7DcnAcAAAAA:rtFsM8DK1TF0-iuvYDQr21QZo_sGGrZQnbxRJOWHmiA9_6qikAdSi8sBSlQrm0es9ZypEINX7r5M_-yG
- https://www.kaggle.com/datasets/ismailpromus/skin-diseases-image-dataset
- Alex-Net [[36](https://www.mdpi.com/1424-8220/23/16/7295#B36-sensors-23-07295)] is a deep CNN that was first introduced in 2012 and obtained leading performance in the ImageNet Large Scale Visual Recognition Challenge (ILSVRC) that same year. ResNet [[37](https://www.mdpi.com/1424-8220/23/16/7295#B37-sensors-23-07295)] and VGG-16 [[38](https://www.mdpi.com/1424-8220/23/16/7295#B38-sensors-23-07295)] are also CNN architectures that have achieved high accuracy in image classification tasks. We trained the dataset on each of these three algorithms, and we found that the accuracies produced were not suitable for our medical problem. Specifically, Alex-Net obtained an accuracy of 60.75%, ResNet obtained an accuracy of 58.69%, and VGG-16 obtained an accuracy of 82.24%.

https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0217293

https://onlinelibrary.wiley.com/doi/full/10.1155/2022/7541583
3.5 ### 3.5. VGG-19 Pretrained CNN Model

## [[https://www.sciencedirect.com/science/article/pii/S1877050919321295|Psoriasis Dtection]]

[Psoriasis](https://www.sciencedirect.com/science/article/abs/pii/S0169260717303875)

## [[]]

## [Psoriasis Detection CNN](https://www.mdpi.com/1424-8220/23/16/7295)
In this study, we obtained the dataset from Kaggle, which is a popular platform for finding and sharing datasets. However, before using the dataset in the deep learning process, it had to undergo preprocessing to ensure its suitability for the task at hand. One important step in preprocessing the dataset was scaling and resizing the images. This step is necessary because the images in the dataset may have different resolutions and aspect ratios, which can affect the accuracy of the deep learning model. By resizing the images to 180×180×3, we ensured that all images had a uniform size.

 Scaling ensures that the images have consistent dimensions, making them easier to process by the deep learning model. In addition, image filtering techniques are applied to remove noise and unwanted details from the images. Filtering helps to enhance the clarity of the images and remove any artifacts that might interfere with the deep learning model’s performance. Specific filtering techniques could include operations such as blurring, sharpening, denoising, or edge detection. Gaussian blur can be applied to reduce high-frequency noise or smooth out sharp transitions in the images. After preprocessing the dataset, we then augmented the data to increase the number of images available for training the deep learning model. Augmentation involves applying various transformations to the original images, such as rotation, flipping, and cropping, to create new images that are similar to the original ones. Rotating the images from a random angle helps the model generalize to different orientations and viewpoints. Flipping images horizontally or vertically can provide variations that simulate different mirror reflections or orientations.

Cropping involves selecting a portion of the image and discarding the rest. This technique can help focus on specific regions of interest or remove unwanted background. By augmenting the dataset, the researchers were able to increase the number of images to 6286, which is a suitable number for training the deep learning model. These previous steps help to ensure that the images are suitable for the task at hand and that the deep learning model has enough data to learn from and achieve high accuracy.

- [Alex-net](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0217293)
- [Res-net](https://en.wikipedia.org/wiki/Residual_neural_network)
- [VGG-16](https://www.mathworks.com/help/deeplearning/ref/vgg16.html)

After experimenting with these three algorithms and trying many different approaches, we decided to build a CNN from scratch using the TensorFlow and Keras libraries [39](https://www.mdpi.com/1424-8220/23/16/7295#B39-sensors-23-07295).

CNNs are a type of artificial neural network widely used for image and object detection and classification. CNNs play a crucial role in deep learning for recognizing objects in images and are extensively employed in image processing, computer vision tasks such as localization and segmentation, video analysis, obstacle recognition in autonomous vehicles, and speech recognition in natural language processing. Due to their versatility and effectiveness, CNNs have become increasingly popular in deep learning and are often the go-to choose for image classification tasks. The building blocks of a CNN typically include various types of layers, each with a specific function in the network. These include convolution layers (such as conv2D), pooling layers (such as MaxPooling2D), flatten layers, dropout layers, dense layers, and activation functions (such as ReLU). By combining these layers in different ways, it is possible to create a CNN architecture that is optimized for a specific task.

In this study, we built a CNN model using a combination of these layer types. With this model, we were able to train the network to accurately classify images as eczema, psoriasis, or neither. However, one challenge in training neural networks is determining the optimal number of epochs to use. Too many epochs can lead to overfitting of the training dataset, where the network becomes too specialized in recognizing the training dataset but performs poorly on new data. Conversely, too few epochs can result in underfitting of the training dataset, where the network fails to learn the underlying patterns in the data. Therefore, we needed to carefully balance the number of training epochs to ensure that our model was able to generalize well to new data while still achieving high accuracy on the training dataset. This is a common challenge in deep learning, and it requires careful tuning of hyperparameters such as the learning rate and regularization to achieve the best results. [Figure 3](https://www.mdpi.com/1424-8220/23/16/7295#fig_body_display_sensors-23-07295-f003) shows the structure of the proposed model with detailed information for each layer.

# Research
Okay, based on the methodology described in the paper you provided, here's how you could adapt their approach to create a model focused specifically on psoriasis detection:

1. **Gather Your Dataset:**
    
    - You'll need images clearly labeled as "Psoriasis" and "Not Psoriasis" (this could include healthy skin or other skin conditions you don't want to detect).
    - The paper used a dataset originally from Kaggle, which contained 2055 psoriasis images combined from sources like DermNet and HAM10000. You could try to source psoriasis images from similar public datasets and gather corresponding "Not Psoriasis" images.
2. **Preprocess the Images:**
    
    - **Resize:** Make all images a uniform size. The paper resized images to 180x180 pixels with 3 color channels (RGB).
    - **Scale:** Normalize pixel values.
    - **Filter:** Apply image filtering techniques if needed to remove noise, similar to the paper's approach (they mention Gaussian blur as an example ).
3. **Augment the Data:**
    
    - To increase the size and diversity of your training data (which helps the model generalize better), apply transformations to your images. The paper used techniques like rotation, flipping, and cropping. They increased their relevant dataset to 6286 images this way.
4. **Build the CNN Model Architecture:**
    
    - The paper built a custom Convolutional Neural Network (CNN) from scratch using TensorFlow and Keras. You can replicate their 15-layer structure, which is roughly (refer to Figure 3a in the paper ):
        - **Input Rescaling Layer:** Normalizes pixel values.
        - **Convolutional Blocks (x5):** Each block consists of a 2D Convolutional layer (Conv2D) with ReLU activation ('same' padding was used ) followed by a 2D Max Pooling layer (MaxPooling2D). These layers extract features from the images. The number of filters typically increases in deeper layers (e.g., 16, 32, 64, 128, 256 as shown in Figure 3a ).
        - **Flatten Layer:** Converts the 2D feature maps into a 1D vector.
        - **Dropout Layer:** Helps prevent overfitting by randomly ignoring some neurons during training.
        - **Dense Layer (Hidden):** A fully connected layer (the paper used 256 units ).
        - **Dense Layer (Output):** **This is the main layer you'll modify.** Instead of the paper's original output (Eczema/Psoriasis/Neither or Eczema/Psoriasis ), you need it to output "Psoriasis" vs. "Not Psoriasis". This typically means a Dense layer with either:
            - 1 neuron and a 'sigmoid' activation function (for binary output 0 or 1).
            - 2 neurons and a 'softmax' activation function (outputting probabilities for the two classes).
5. **Train the Model:**
    
    - **Split Data:** Divide your dataset into training and testing sets (the paper used an 80% training, 20% testing split ).
    - **Compile:** Choose an optimizer (e.g., Adam is common), and a loss function suitable for binary classification (e.g., 'binary_crossentropy').
    - **Train:** Train the model for a set number of epochs (the paper used 30 epochs ). Monitor the training and validation accuracy/loss to avoid overfitting (training too long ) or underfitting (training too little ). Adjust hyperparameters like learning rate and batch size as needed. The paper used 629 steps per epoch.

By following these steps, adapting the specific layers and training data to your psoriasis-only goal, you can work towards recreating a similar model tailored to your presentation topic. Good luck!
# References

I'll analyze your current approach for psoriasis detection and suggest ways to boost your F1 score from 85% to over 91%. Your current EfficientNet B3 model is showing strong results, with a test F1 score of 88.7%, but there's room for improvement.

Here are several strategies we can implement to boost performance beyond 91%:

## 1. Improved Model Architecture

Your current EfficientNet B3 is a solid choice, but we can try more powerful models or ensemble approaches:

```python
# Try a more powerful base model
def get_model_v2():
    model = efficientnet_b4(weights='IMAGENET1K_V1')  # Upgrade to B4
    model.classifier[1] = nn.Linear(model.classifier[1].in_features, 1)
    return model
```

## 2. Enhanced Data Augmentation

Your augmentation is good, but we can make it more robust for skin lesion images:

```python
train_transforms = transforms.Compose([
    transforms.Resize((320, 320)),  # Slightly larger images
    transforms.RandomHorizontalFlip(),
    transforms.RandomVerticalFlip(),  # Add vertical flips
    transforms.RandomRotation(20),    # More rotation
    transforms.RandomAffine(degrees=0, translate=(0.05, 0.05), scale=(0.95, 1.05)),  # Add scaling
    transforms.ColorJitter(brightness=0.3, contrast=0.3, saturation=0.3, hue=0.1),  # Stronger color augmentation
    transforms.ToTensor(),
    transforms.Normalize([0.485, 0.456, 0.406], [0.229, 0.224, 0.225])  # ImageNet stats for better transfer learning
])
```

## 3. Model Ensemble

Let's combine predictions from multiple models for better results:

```python
import torch
import torch.nn as nn
from torchvision.models import efficientnet_b3, efficientnet_b4, convnext_small, swin_v2_b

class EnsembleModel(nn.Module):
    def __init__(self):
        super(EnsembleModel, self).__init__()
        # Initialize models
        self.model1 = efficientnet_b3(weights='IMAGENET1K_V1')
        self.model1.classifier[1] = nn.Linear(self.model1.classifier[1].in_features, 1)
        
        self.model2 = efficientnet_b4(weights='IMAGENET1K_V1')
        self.model2.classifier[1] = nn.Linear(self.model2.classifier[1].in_features, 1)
        
        self.model3 = convnext_small(weights='IMAGENET1K_V1')
        self.model3.classifier[2] = nn.Linear(self.model3.classifier[2].in_features, 1)
        
        # Final layer to combine predictions
        self.combiner = nn.Linear(3, 1)
        
    def forward(self, x):
        # Get predictions from each model
        out1 = self.model1(x)
        out2 = self.model2(x)
        out3 = self.model3(x)
        
        # Combine predictions
        combined = torch.cat([out1, out2, out3], dim=1)
        return self.combiner(combined)

```

## 4. Learning Rate Scheduling and Optimizers

Let's implement learning rate scheduling to improve training dynamics:

```python
# Optimizer with weight decay
optimizer = optim.AdamW(model.parameters(), lr=2e-4, weight_decay=1e-4)

# Learning rate scheduler
scheduler = torch.optim.lr_scheduler.ReduceLROnPlateau(
    optimizer, mode='max', factor=0.5, patience=2, verbose=True
)
```

## 5. Improved Training Loop with Mixup Augmentation

Implement mixup augmentation which has shown to improve generalization:

```python
def mixup_data(x, y, alpha=0.2):
    '''Returns mixed inputs, pairs of targets, and lambda'''
    if alpha > 0:
        lam = np.random.beta(alpha, alpha)
    else:
        lam = 1

    batch_size = x.size()[0]
    index = torch.randperm(batch_size).to(x.device)

    mixed_x = lam * x + (1 - lam) * x[index, :]
    y_a, y_b = y, y[index]
    return mixed_x, y_a, y_b, lam

def mixup_criterion(criterion, pred, y_a, y_b, lam):
    return lam * criterion(pred, y_a) + (1 - lam) * criterion(pred, y_b)

# Enhanced training function with mixup
def train_with_mixup(model, train_loader, val_loader, epochs=25, patience=7):
    best_f1 = 0
    patience_counter = 0

    for epoch in range(epochs):
        model.train()
        train_loss = 0

        for images, labels in tqdm(train_loader, desc=f"Training Epoch {epoch+1}"):
            images, labels = images.to(device), labels.to(device).float().unsqueeze(1)
            
            # Apply mixup
            if random.random() < 0.8:  # Apply mixup 80% of the time
                images, labels_a, labels_b, lam = mixup_data(images, labels)
                images, labels_a, labels_b = map(
                    torch.autograd.Variable, (images, labels_a, labels_b)
                )
            
            optimizer.zero_grad()

            with torch.amp.autocast('cuda'):
                outputs = model(images)
                
                if random.random() < 0.8:  # If we applied mixup
                    loss = mixup_criterion(criterion, outputs, labels_a, labels_b, lam)
                else:
                    loss = criterion(outputs, labels)

            scaler.scale(loss).backward()
            scaler.step(optimizer)
            scaler.update()

            train_loss += loss.item()

        avg_train_loss = train_loss / len(train_loader)
        val_f1 = evaluate(model, val_loader)
        
        # Update learning rate based on validation performance
        scheduler.step(val_f1)

        print(f"Epoch [{epoch+1}/{epochs}] - Train Loss: {avg_train_loss:.4f} - Val F1: {val_f1:.4f}")

        # Early Stopping with model saving
        if val_f1 > best_f1:
            best_f1 = val_f1
            patience_counter = 0
            torch.save(model.state_dict(), 'best_model.pth')
            print("Saved Best Model!\n")
        else:
            patience_counter += 1
            if patience_counter >= patience:
                print("Early stopping triggered!")
                break

```

## 6. Class Weighting for Imbalanced Data

If there's any class imbalance in your psoriasis detection:

```python
# Calculate class weights
from sklearn.utils.class_weight import compute_class_weight
import numpy as np

labels = [label for _, label in train_dataset.samples]
class_weights = compute_class_weight('balanced', classes=np.unique(labels), y=labels)
class_weights = torch.FloatTensor(class_weights).to(device)

# Use weighted loss
criterion = nn.BCEWithLogitsLoss(pos_weight=class_weights[1])
```

## 7. K-fold Cross Validation

For more reliable training and to utilize all your data effectively:

```python
from sklearn.model_selection import KFold

def train_with_kfold(dataset_paths, dataset_labels, k=5, epochs=20):
    kf = KFold(n_splits=k, shuffle=True, random_state=42)
    
    fold_results = []
    
    for fold, (train_idx, val_idx) in enumerate(kf.split(dataset_paths)):
        print(f"Training fold {fold+1}/{k}")
        
        # Split data for this fold
        train_paths = [dataset_paths[i] for i in train_idx]
        train_labels = [dataset_labels[i] for i in train_idx]
        val_paths = [dataset_paths[i] for i in val_idx]
        val_labels = [dataset_labels[i] for i in val_idx]
        
        # Create datasets
        train_dataset = CustomDataset(train_paths, train_labels, transform=train_transforms)
        val_dataset = CustomDataset(val_paths, val_labels, transform=val_test_transforms)
        
        # Create dataloaders
        train_loader = DataLoader(train_dataset, batch_size=32, shuffle=True, num_workers=4)
        val_loader = DataLoader(val_dataset, batch_size=32, shuffle=False, num_workers=4)
        
        # Initialize model for this fold
        model = get_model().to(device)
        optimizer = optim.AdamW(model.parameters(), lr=2e-4, weight_decay=1e-4)
        scheduler = torch.optim.lr_scheduler.ReduceLROnPlateau(optimizer, mode='max', factor=0.5, patience=2)
        
        # Train model
        best_val_f1 = train_with_mixup(model, train_loader, val_loader, epochs=epochs)
        
        # Save fold results
        torch.save(model.state_dict(), f'model_fold_{fold+1}.pth')
        fold_results.append(best_val_f1)
        
    print(f"K-fold cross validation results: {fold_results}")
    print(f"Average F1 score: {sum(fold_results) / len(fold_results):.4f}")

```

## 8. Test-Time Augmentation (TTA)

Apply augmentations during inference to get more robust predictions:

```python
def evaluate_with_tta(model, loader, n_augmentations=5):
    model.eval()
    preds = []
    targets = []

    with torch.no_grad():
        for images, labels in loader:
            batch_size = images.size(0)
            images, labels = images.to(device), labels.to(device).float().unsqueeze(1)
            
            # Original prediction
            outputs = model(images)
            
            # Test-time augmentation predictions
            for _ in range(n_augmentations):
                # Apply random augmentations
                aug_images = test_time_augment(images)
                aug_outputs = model(aug_images)
                outputs += aug_outputs  # Accumulate predictions
                
            # Average the predictions
            outputs = outputs / (n_augmentations + 1)
            
            preds += torch.sigmoid(outputs).cpu().numpy().tolist()
            targets += labels.cpu().numpy().tolist()

    preds = [1 if p[0] > 0.5 else 0 for p in preds]
    targets = [int(t[0]) for t in targets]

    acc = accuracy_score(targets, preds)
    precision = precision_score(targets, preds)
    recall = recall_score(targets, preds)
    f1 = f1_score(targets, preds)

    return acc, precision, recall, f1
```

## 9. Hyperparameter Tuning

Let's use Optuna for automated hyperparameter optimization:

```python
import optuna
from optuna.trial import TrialState

def objective(trial):
    # Hyperparameters to optimize
    lr = trial.suggest_float('lr', 1e-5, 1e-3, log=True)
    weight_decay = trial.suggest_float('weight_decay', 1e-6, 1e-3, log=True)
    batch_size = trial.suggest_categorical('batch_size', [16, 24, 32, 48])
    image_size = trial.suggest_categorical('image_size', [256, 288, 320, 384])
    model_name = trial.suggest_categorical('model_name', 
                                         ['efficientnet_b3', 'efficientnet_b4', 'convnext_small'])
    
    # Create model based on selected architecture
    if model_name == 'efficientnet_b3':
        model = efficientnet_b3(weights='IMAGENET1K_V1')
        model.classifier[1] = nn.Linear(model.classifier[1].in_features, 1)
    elif model_name == 'efficientnet_b4':
        model = efficientnet_b4(weights='IMAGENET1K_V1')
        model.classifier[1] = nn.Linear(model.classifier[1].in_features, 1)
    else:  # convnext_small
        model = convnext_small(weights='IMAGENET1K_V1')
        model.classifier[2] = nn.Linear(model.classifier[2].in_features, 1)
    
    model = model.to(device)
    
    # Create transforms with selected image size
    train_transforms = transforms.Compose([
        transforms.Resize((image_size, image_size)),
        transforms.RandomHorizontalFlip(),
        transforms.RandomVerticalFlip(),
        transforms.RandomRotation(15),
        transforms.ColorJitter(brightness=0.2, contrast=0.2, saturation=0.2, hue=0.1),
        transforms.ToTensor(),
        transforms.Normalize([0.485, 0.456, 0.406], [0.229, 0.224, 0.225])
    ])
    
    val_transforms = transforms.Compose([
        transforms.Resize((image_size, image_size)),
        transforms.ToTensor(),
        transforms.Normalize([0.485, 0.456, 0.406], [0.229, 0.224, 0.225])
    ])
    
    # Create datasets and dataloaders
    train_dataset = datasets.ImageFolder(train_dir, transform=train_transforms)
    val_dataset = datasets.ImageFolder(val_dir, transform=val_transforms)
    
    train_loader = DataLoader(
        train_dataset, batch_size=batch_size, shuffle=True, num_workers=4
    )
    val_loader = DataLoader(
        val_dataset, batch_size=batch_size, shuffle=False, num_workers=4
    )
    
    # Optimizer and criterion
    optimizer = optim.AdamW(model.parameters(), lr=lr, weight_decay=weight_decay)
    criterion = nn.BCEWithLogitsLoss()
    
    # Train for a few epochs
    best_val_f1 = 0
    
    for epoch in range(5):  # Just train for 5 epochs for each trial
        # Training
        model.train()
        for images, labels in train_loader:
            images, labels = images.to(device), labels.to(device).float().unsqueeze(1)
            optimizer.zero_grad()
            outputs = model(images)
            loss = criterion(outputs, labels)
            loss.backward()
            optimizer.step()
        
        # Validation
        val_f1 = evaluate(model, val_loader)
        
        if val_f1 > best_val_f1:
            best_val_f1 = val_f1
    
    return best_val_f1

# Run the optimization
study = optuna.create_study(direction='maximize')
study.optimize(objective, n_trials=20)

# Print the best parameters
print(f"Best trial F1 score: {study.best_trial.value:.4f}")
print("Best hyperparameters:")
for key, value in study.best_trial.params.items():
    print(f"    {key}: {value}")

```

## 10. Final Implementation

Here's a consolidated approach that combines several of these techniques:

```python
import torch
import torch.nn as nn
import torch.optim as optim
from torch.utils.data import DataLoader
from torchvision import datasets, transforms, models
from sklearn.metrics import f1_score, accuracy_score, precision_score, recall_score
from tqdm import tqdm
import numpy as np
import random
import os

# Set seeds for reproducibility
def set_seed(seed=42):
    random.seed(seed)
    np.random.seed(seed)
    torch.manual_seed(seed)
    torch.cuda.manual_seed(seed)
    torch.backends.cudnn.deterministic = True
    torch.backends.cudnn.benchmark = False

set_seed()

# Check device
device = torch.device('cuda' if torch.cuda.is_available() else 'cpu')
print(f"Using device: {device}")

# Enhanced data augmentation
train_transforms = transforms.Compose([
    transforms.Resize((384, 384)),  # Larger image size
    transforms.RandomHorizontalFlip(),
    transforms.RandomVerticalFlip(),
    transforms.RandomRotation(20),
    transforms.RandomAffine(degrees=0, translate=(0.05, 0.05), scale=(0.95, 1.05)),
    transforms.ColorJitter(brightness=0.3, contrast=0.3, saturation=0.3, hue=0.1),
    transforms.ToTensor(),
    transforms.Normalize([0.485, 0.456, 0.406], [0.229, 0.224, 0.225])  # ImageNet stats
])

val_test_transforms = transforms.Compose([
    transforms.Resize((384, 384)),
    transforms.ToTensor(),
    transforms.Normalize([0.485, 0.456, 0.406], [0.229, 0.224, 0.225])
])

# Datasets
train_dir = './dataset/train'
val_dir = './dataset/val'
test_dir = './dataset/test'

train_dataset = datasets.ImageFolder(train_dir, transform=train_transforms)
val_dataset = datasets.ImageFolder(val_dir, transform=val_test_transforms)
test_dataset = datasets.ImageFolder(test_dir, transform=val_test_transforms)

# Calculate class weights
labels = [label for _, label in train_dataset.samples]
# Map to binary (0 or 1)
binary_labels = [1 if label == 1 else 0 for label in labels]
class_counts = np.bincount(binary_labels)
total_samples = len(binary_labels)
class_weights = total_samples / (2 * class_counts)
pos_weight = torch.tensor([class_weights[1] / class_weights[0]]).to(device)

# DataLoaders with larger batch size
train_loader = DataLoader(train_dataset, batch_size=24, shuffle=True, num_workers=4, pin_memory=True)
val_loader = DataLoader(val_dataset, batch_size=32, shuffle=False, num_workers=4, pin_memory=True)
test_loader = DataLoader(test_dataset, batch_size=32, shuffle=False, num_workers=4, pin_memory=True)

# ConvNeXt model (more advanced architecture)
def get_model():
    model = models.convnext_small(weights='IMAGENET1K_V1')
    model.classifier[2] = nn.Linear(model.classifier[2].in_features, 1)
    return model

model = get_model().to(device)

# Loss, Optimizer with weight decay
criterion = nn.BCEWithLogitsLoss(pos_weight=pos_weight)
optimizer = optim.AdamW(model.parameters(), lr=1e-4, weight_decay=1e-4)
scheduler = torch.optim.lr_scheduler.ReduceLROnPlateau(
    optimizer, mode='max', factor=0.5, patience=3, verbose=True
)

# Mixup function for data augmentation
def mixup_data(x, y, alpha=0.2):
    if alpha > 0:
        lam = np.random.beta(alpha, alpha)
    else:
        lam = 1

    batch_size = x.size()[0]
    index = torch.randperm(batch_size).to(x.device)

    mixed_x = lam * x + (1 - lam) * x[index, :]
    y_a, y_b = y, y[index]
    return mixed_x, y_a, y_b, lam

def mixup_criterion(criterion, pred, y_a, y_b, lam):
    return lam * criterion(pred, y_a) + (1 - lam) * criterion(pred, y_b)

# For mixed precision
scaler = torch.cuda.amp.GradScaler()

# Enhanced training function with mixup
def train(model, train_loader, val_loader, epochs=30, patience=7):
    best_f1 = 0
    patience_counter = 0

    for epoch in range(epochs):
        model.train()
        train_loss = 0

        for images, labels in tqdm(train_loader, desc=f"Training Epoch {epoch+1}"):
            images, labels = images.to(device), labels.to(device).float().unsqueeze(1)
            
            # Apply mixup with 70% probability
            use_mixup = random.random() < 0.7
            if use_mixup:
                images, labels_a, labels_b, lam = mixup_data(images, labels)
            
            optimizer.zero_grad()

            with torch.cuda.amp.autocast():
                outputs = model(images)
                
                if use_mixup:
                    loss = mixup_criterion(criterion, outputs, labels_a, labels_b, lam)
                else:
                    loss = criterion(outputs, labels)

            scaler.scale(loss).backward()
            scaler.step(optimizer)
            scaler.update()

            train_loss += loss.item()

        avg_train_loss = train_loss / len(train_loader)
        
        # Validation with TTA
        val_acc, val_precision, val_recall, val_f1 = evaluate_with_tta(model, val_loader)
        
        # Update learning rate based on validation F1
        scheduler.step(val_f1)

        print(f"Epoch [{epoch+1}/{epochs}] - Train Loss: {avg_train_loss:.4f}")
        print(f"Val Metrics - Acc: {val_acc:.4f}, Precision: {val_precision:.4f}, Recall: {val_recall:.4f}, F1: {val_f1:.4f}")

        # Early Stopping with model saving
        if val_f1 > best_f1:
            best_f1 = val_f1
            patience_counter = 0
            torch.save(model.state_dict(), 'best_model.pth')
            print("✅ Saved Best Model!\n")
        else:
            patience_counter += 1
            if patience_counter >= patience:
                print("Early stopping triggered!")
                break

# Test-time augmentation
def test_time_augment(images):
    # Apply random horizontal and vertical flips
    if random.random() > 0.5:
        images = torch.flip(images, [3])  # Horizontal flip
    if random.random() > 0.5:
        images = torch.flip(images, [2])  # Vertical flip
    return images

# Evaluation with test-time augmentation
def evaluate_with_tta(model, loader, n_augmentations=4):
    model.eval()
    all_preds = []
    all_targets = []

    with torch.no_grad():
        for images, labels in loader:
            images, labels = images.to(device), labels.to(device)
            batch_preds = []
            
            # Original prediction
            outputs = model(images)
            batch_preds.append(torch.sigmoid(outputs))
            
            # TTA predictions
            for _ in range(n_augmentations):
                aug_images = test_time_augment(images)
                aug_outputs = model(aug_images)
                batch_preds.append(torch.sigmoid(aug_outputs))
                
            # Average the predictions
            final_preds = torch.mean(torch.stack(batch_preds), dim=0)
            
            all_preds.extend(final_preds.cpu().numpy())
            all_targets.extend(labels.unsqueeze(1).float().cpu().numpy())

    # Convert to binary predictions
    binary_preds = [1 if p[0] > 0.5 else 0 for p in all_preds]
    binary_targets = [int(t[0]) for t in all_targets]

    # Calculate metrics
    acc = accuracy_score(binary_targets, binary_preds)
    precision = precision_score(binary_targets, binary_preds)
    recall = recall_score(binary_targets, binary_preds)
    f1 = f1_score(binary_targets, binary_preds)

    return acc, precision, recall, f1

# Final evaluation
def final_evaluation(model_path, test_loader):
    model = get_model().to(device)
    model.load_state_dict(torch.load(model_path))
    
    test_acc, test_precision, test_recall, test_f1 = evaluate_with_tta(model, test_loader)
    
    print("Final Test Results:")
    print(f"Accuracy: {test_acc:.4f}")
    print(f"Precision: {test_precision:.4f}")
    print(f"Recall: {test_recall:.4f}")
    print(f"F1 Score: {test_f1:.4f}")
    
    return model

# Start training
print("Starting training...")
train(model, train_loader, val_loader, epochs=30, patience=7)

# Final evaluation
print("Performing final evaluation...")
final_model = final_evaluation('best_model.pth', test_loader)

```

## Expected Improvements

Implementing these changes should significantly improve your F1 score:

1. **ConvNeXt Architecture**: +2-3% improvement over EfficientNet B3
2. **Enhanced Augmentation**: +1-2% from more robust data transformations
3. **Mixup Training**: +1-2% through better generalization
4. **Test-Time Augmentation**: +0.5-1% through more robust predictions
5. **Class Weighting**: +0.5-1% by handling any class imbalance

Many of these improvements are complementary and should collectively push your F1 score well above 91%. The most significant gains will likely come from using a more advanced model architecture (ConvNeXt), implementing mixup training, and using test-time augmentation.

Would you like me to explain any of these techniques in more detail?
###### Information
- date: 2025.02.17
- time: 15:09