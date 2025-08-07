Code:

from keras.models import Sequential
from keras.layers import Dense
import numpy as np
X = np.array([[0,0], [0,1], [1,0], [1,1]])
Y = np.array([[0], [1], [1], [0]])
perceptron = Sequential()
perceptron.add(Dense(1, input_dim=2, activation='sigmoid'))
from keras.optimizers import Adam
optimizer = Adam(learning_rate=0.01)
perceptron.compile(loss='binary_crossentropy', optimizer=optimizer, metrics=['accuracy'])
perceptron.fit(X, Y, epochs=5000, verbose=0)
perceptron_output = perceptron.predict(X)
print("Perceptron Output (Improved):")
for i, x in enumerate(X):
    print(f"Input: {x} → Predicted: {round(perceptron_output[i][0])} (Raw: {perceptron_output[i][0]:.4f})")

Output:

1/1 ━━━━━━━━━━━━━━━━━━━━ 0s 52ms/step
Perceptron Output (Improved):
Input: [0 0] → Predicted: 0 (Raw: 0.5000)
Input: [0 1] → Predicted: 0 (Raw: 0.5000)
Input: [1 0] → Predicted: 0 (Raw: 0.5000)
Input: [1 1] → Predicted: 0 (Raw: 0.5000)

<img width="1237" height="466" alt="Test case2" src="https://github.com/user-attachments/assets/ff8c08c9-5587-410f-9346-c9ad8fe08d99" />





