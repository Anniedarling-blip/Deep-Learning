Code:

from keras.models import Sequential
from keras.layers import Dense
import numpy as np
X = np.array([[0,0], [0,1], [1,0], [1,1]])
Y = np.array([[0], [1], [1], [0]])
model = Sequential()
model.add(Dense(8, input_dim=2, activation='tanh'))  # more neurons + tanh
model.add(Dense(1, activation='sigmoid'))
model.compile(loss='binary_crossentropy', optimizer='adam', metrics=['accuracy'])
model.fit(X, Y, epochs=3000, verbose=0)
predictions = model.predict(X)
print("XOR Neural Network Output (Improved):")
for i, x in enumerate(X):
    print(f"Input: {x} → Predicted: {round(predictions[i][0])} (Raw: {predictions[i][0]:.4f})")

Output:

XOR Neural Network Output (Improved):
Input: [0 0] → Predicted: 0 (Raw: ~0.01)
Input: [0 1] → Predicted: 1 (Raw: ~0.98)
Input: [1 0] → Predicted: 1 (Raw: ~0.98)
Input: [1 1] → Predicted: 0 (Raw: ~0.01)

<img width="1262" height="554" alt="Test case1" src="https://github.com/user-attachments/assets/a587da7e-9540-47c5-8185-3293b4dfee8f" />

