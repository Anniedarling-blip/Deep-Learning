Code:

!pip install numpy matplotlib tensorflow
from keras.models import Sequential 
from keras.layers import Dense 
import numpy as np 
import matplotlib.pyplot as plt  
X = np.array([[0,0], [0,1], [1,0], [1,1]]) 
Y = np.array([[0], [1], [1], [0]]) 
model = Sequential() 
model.add(Dense(4, input_dim=2, activation='relu')) 
model.add(Dense(1, activation='sigmoid')) 
model.compile(loss='binary_crossentropy', optimizer='adam', metrics=['accuracy']) 
history = model.fit(X, Y, epochs=1000, verbose=0) 
loss, acc = model.evaluate(X, Y) 
print("Accuracy:", acc) 
print("Predictions:", model.predict(X))  
plt.plot(history.history['loss']) 
plt.title('Model Loss') 
plt.xlabel('Epoch') 
plt.ylabel('Loss') 
plt.grid(True) 
plt.show()

Output:

<img width="1228" height="425" alt="1)Core-Code" src="https://github.com/user-attachments/assets/30bf2d30-8218-42c0-ae16-222a3df507e4" />
<img width="1229" height="631" alt="1)Core-Output" src="https://github.com/user-attachments/assets/51de03c7-bf0f-4776-a8e5-f8f75cbece7f" />
