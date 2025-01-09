import cv2
from mediapipe import solutions

"""camera satup"""
cap = cv2.VideoCapture(0)
cap.set(cv2.CAP_PROP_FRAME_WIDTH, 700)
cap.set(cv2.CAP_PROP_FRAME_HEIGHT, 700)

mp_draw = solutions.drawing_utils
mp_draw_stayl = solutions.drawing_styles
mo_hand = solutions.hands

hand = mo_hand.Hands(max_num_hands=2)
while True:
    data, image = cap.read()
    image = cv2.cvtColor(cv2.flip(image,1),cv2.COLOR_BGR2RGB)
    result = hand.process(image)

    if result.multi_hand_landmarks:
        #  result.multi_hand_landmarks["hande"].landmark["finger"]

        """fingers"""
        thom_tip = result.multi_hand_landmarks[0].landmark[4]
        index_tip = result.multi_hand_landmarks[0].landmark[8]
        reng_finger_tip = result.multi_hand_landmarks[0].landmark[16]
        pinky_tip = result.multi_hand_landmarks[0].landmark[20]
        mid_finger_tip = result.multi_hand_landmarks[0].landmark[12]
        wrst = result.multi_hand_landmarks[0].landmark[0]
        bf = result.multi_hand_landmarks[0].landmark[17]

        for hand_landmarks in result.multi_hand_landmarks:
            mp_draw.draw_landmarks(image, hand_landmarks, mo_hand.HAND_CONNECTIONS)
    cv2.imshow("hand", image)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

# Release the camera and close all OpenCV windows
cap.release()
cv2.destroyAllWindows()
