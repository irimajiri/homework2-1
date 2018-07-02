# homework2-1
import cv2

capture = cv2.VideoCapture(0)

def gamma(x):   //ガンマ変換
    gamma = 1/2
    y = 255*(x/255)**(1/gamma)
    return y

while(True):
    ret, frame = capture.read()
    cv2.imshow('frame1',frame)  //何も処理してない画像
    cv2.imshow('frame2',gamma(frame)) //ガンマ変換した画像       
    if cv2.waitKey(1) & 0xFF == ord('q'): //qを押せば終了
        break

capture.release()
cv2.destroyAllWindows()




//Python 3.6.6 |Anaconda custom (64-bit)| (default, Jun 28 2018, 11:07:29) 
//[GCC 4.2.1 Compatible Clang 4.0.1 (tags/RELEASE_401/final)] on darwin
//Type "help", "copyright", "credits" or "license" for more information.

//コントラスト変更としてガンマ変換を行った.
//YOUTUBE:https://www.youtube.com/watch?v=tw66IS6IPQo&feature=youtu.be
