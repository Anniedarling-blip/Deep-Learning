Code:

import numpy as np
from tensorflow.keras.datasets import mnist
from tensorflow.keras.models import load_model
(_, _), (X_test, y_test) = mnist.load_data()
X_test = X_test.reshape(-1, 28, 28, 1).astype('float32') / 255.0
sample_indices = [0, 1, 2, 3, 4, 5]  
X_sample = X_test[sample_indices]
y_true = y_test[sample_indices]
y_pred_probs = model.predict(X_sample)
y_pred = np.argmax(y_pred_probs, axis=1)
print("Input Digit Image | Expected Label | Model Output | Correct (Y/N)")
for i in range(len(sample_indices)):
    correct = "Y" if y_true[i] == y_pred[i] else "N"
    print(f"Image of {y_true[i]}       | {y_true[i]}            | {y_pred[i]}            | {correct}")

Output:

<img width="1426" height="576" alt="image" src="https://github.com/user-attachments/assets/f455eec6-ca18-42b8-b3a5-77c51905f817" />
