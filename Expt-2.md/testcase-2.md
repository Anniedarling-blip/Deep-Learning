Code:

import numpy as np
from tensorflow.keras.datasets import fashion_mnist
from tensorflow.keras.utils import to_categorical
class_names = ['T-shirt', 'Trouser', 'Pullover', 'Dress', 'Coat',
               'Sandal', 'Shirt', 'Sneaker', 'Bag', 'Ankle boot']
(_, _), (X_test, y_test) = fashion_mnist.load_data()
X_test = X_test.reshape(-1, 28, 28, 1).astype('float32') / 255.0
sample_indices = [0, 1, 2, 3, 4, 5, 6, 7] 
X_sample = X_test[sample_indices]
y_true = y_test[sample_indices]
y_pred_probs = model.predict(X_sample)
y_pred = np.argmax(y_pred_probs, axis=1)
for i in range(len(sample_indices)):
    true_label = class_names[y_true[i]]
    predicted_label = class_names[y_pred[i]]
    correct = "Y" if y_true[i] == y_pred[i] else "N"
    print(f"{true_label:<12} {true_label:<12} {predicted_label:<16} {correct}")

Output:
<img width="1402" height="637" alt="image" src="https://github.com/user-attachments/assets/153d0dd3-4b6d-43d5-aff7-fb5bc2d5a08d" />
