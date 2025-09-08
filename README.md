# Ex. No: 02  
# Image Acquisition using Web Camera  

**Name:** __vishnu km__________    **Reg. No:** __212223240185__________

## Dr. Michael Mahesh K Saveetha Engineering College
- michaelmaheshk@gmail.com 
- CNN using Custom Images 
- 19AI413-Digital Image Processing Techincs 

- EVEN SEM ( Slot: 4D1-1 & 4K1-1)
#i)Write the frameas JPG file
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
```
```
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()
```
```
captured_image = cv2.imread('captured_frame.jpg')
```
```
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```
<img width="639" height="501" alt="image" src="https://github.com/user-attachments/assets/afe67545-64c0-4cd3-8855-abf5114a5526" />


#ii)Display the vedio
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```
<img width="364" height="472" alt="image" src="https://github.com/user-attachments/assets/b296dcae-59c4-4fbc-bdb9-3259080b2106" />

#iii) Display the video by resizing the window
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```

<img width="324" height="473" alt="image" src="https://github.com/user-attachments/assets/50379111-84a5-405b-99bf-1c6925f6d69c" />


# iv) Rotate and display the video
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```
<img width="629" height="463" alt="image" src="https://github.com/user-attachments/assets/25eb3d3f-fd88-4bc5-8bcc-a8b9cc5c7b07" />
