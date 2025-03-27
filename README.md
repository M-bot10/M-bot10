## Hi there 👋

<!--
**M-bot10/M-bot10** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
import cv2
cap = cv2.VideoCapture('video.avi')
car_cascade = cv2.CascadeClassifier('cars.xml')
while True:
    ret, frames = cap.read()
    gray = cv2.cvtColor(frames, cv2.COLOR_BGR2GRAY)
    cars = car_cascade.detectMultiScale(gray, 1.1, 1) 
    for (x,y,w,h) in cars:
        cv2.rectangle(frames,(x,y),(x+w,y+h),(255,0,0),2)
    cv2.imshow('video', frames)
    if cv2.waitKey(30) == 27:
        break
cv2.destroyAllWindows()
