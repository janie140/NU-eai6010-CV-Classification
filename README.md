**Introduction**
Computer vision image classification is a machine learning technique that has gained significant popularity in recent years and serves a wide array of applications. In the context of deep learning, transfer learning involves taking a model trained on one task and customizing it for another.
Unlike building a model from scratch, transfer learning involves pulling an existing model off
the shelf and tuning it for a specific use case. This assignment will explore the use of a pre-
trained computer vision model from PyTorch for transfer learning on a new image dataset,
demonstrating how leveraging pre-existing knowledge can enhance performance and efficiency
in new tasks.

**Data Selection and Methods**
In this project, we utilized a dataset comprising 2301 fruit images sourced from Kaggle,
categorized into ten classes: Apple, Orange, Avocado, Kiwi, Mango, Pineapple, Strawberries,
Banana, Cherry, and Watermelon[1]. With approximately 230 images per category, the dataset
ensures a balanced training resource for each classification.
PyTorch's EfficientNetV2 model was chosen for this dataset due to its reputation for balancing
accuracy and computational efficiency. EfficientNetV2 often exhibits strong performance with
fewer parameters and lower computational cost compared to other models, as highlighted in both
the PyTorch documentation and the paper titled "EfficientNetV2: Smaller Models and Faster
Training"[2][3].
To prepare the dataset for modeling, FastAi's features were harnessed to generate a data block,
facilitating the normalization of the dataset view and the creation of a data loader. Subsequently,
the Vision Learner (formerly known as CNN Learner) was employed to establish a base learner using the pre-trained EfficientNetV2 model. The validation metric ‘error_rate’ was chosen to
monitor performance during training.
Fine-tuning the model involved two approaches: first, freezing all layers except the new output
layer and conducting training epochs solely on the output layer; second, unfreezing the entire
model and running the specified number of epochs. Initial results from a single epoch run of the
model with the newly trained fruit dataset demonstrated promising performance and accuracy,
with error rates ranging from only 10-12%, suggesting that the pre-trained model may be well-
suited for this classification problem
