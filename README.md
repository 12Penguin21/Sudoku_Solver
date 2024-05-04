# Sudoku Solver
THIS PROJECT WAS MADE FOR OUR END TERM EXAMINATIONS OF AIML

MEMBERS

SUJAL KUMAR SINGH - 231010250 ,ECE

UDAY TIWARI -231010255  ,ECE

SAHIL BANJARE - 231010239  ,ECE

HERE IS A POSTER OF OUR PROJECT
<img src="IMAGES/poster.png"> 

HERE IS THE DEMONSTRATION VIDEO

<a href="https://drive.google.com/file/d/1vh6EtKlmPX9vrCbdcVvRj5X990StNb2j/view?usp=drive_link">VIDEO LINK</a>


This projected was made conscidering many references and resources for features like computer vision and digit recognition . 

Sudoku is a puzzle in which players insert the numbers one to nine into a grid consisting of nine squares subdivided into 
a further nine smaller squares in such a way that every number appears once in each horizontal line, vertical line, and square.

This program serves as a way to calculate the solution to any 9x9 sudoku puzzle via webcam.
It identifies the puzzle through the webcam, processes it uses OpenCV, runs against a neural network to predict the digits, 
and runs an efficient sudoku solver to determine the answer. It then displays the answer on the same frame if it is solvable.



<img src="IMAGES/IMG1.png"> 

AI Sudoku Solver

Using OpenCV, Deep Learning, and Backtracking Algorithm, We can solve the sudoku puzzle. First, build the Character Recognition model that can extract digits from a Sudoku grid image and then work on a backtracking approach to solve it. Deep Learning-based AI_Sudoku_Solver architecture uses OpenCV (opencv==4.2.1) and Python (python==3.6). The model Convolution Neural Network(CNN) uses Keras (keras==2.3.1) on Tensorflow for Digit Recognition.
Tested using `Python 3.6` 

'"Approach'"

Here, we can divide the process into 3 parts :

1. Looking for a sudoku puzzle in the image.
2. Extracting numbers from sudoku.
3. Solving the Sudoku using backtracking.

Looking for a sudoku puzzle in the image: In this part, we’ll be focusing on how to extract the sudoku grid i.e. our Region of Interest (ROI) from the input image.

<img src="IMAGES/working1.webp">

1.Converting the input image to a binary image: This step involves converting the input image to a greyscale image, applying a gaussian blur to the grey-scale image, followed by thresholding, bitwise_not, and dilating the image.

2.Detecting the largest polygon in the image: This step involves finding the contours and selecting the largest contour. Now from the largest contour, selecting the extreme most points and would be the 4 corners. The function cv2.findContours returns all the contours it finds in the image. After sorting the returned contours from the image by area, the largest contour can easily be selected.

3.Cropping and Warping the largest contour:
The approach is simple since we have the coordinates of the 4 corners, we can use warping, which gives a better perspective of the image.

After extracting digit, our Sudoku grid will look like…
<img src="IMAGES/working2.webp"> 
Solving the Sudoku using backtracking:

Now that we have converted the image into an array, we just need to make a function that can fill up the blank spaces effectively given the rules of sudoku.
<img src="IMAGES/working3.webp">
<p>HERE IS A REFERENCE OF SOLVING SUDUKO USING BACKTRACKING FROM GFG.<br> <a href="https://www.geeksforgeeks.org/sudoku-backtracking-7/">GFG article for backtracking in sudoku</a></p>

<p>Some References.<br>
<a href="https://github.com/janzd/CNN-MNIST">DIGIT RECOGNITION</a>

HERE ARE SOME REFERENCE SUDOKU PUZZLES WITH SOLUTION FOR VERIFICATION


[Sudoku 1](IMAGES/Sudoku-Puzzle_07.pdf)
[Sudoku 2](IMAGES/Sudoku-Puzzle_08.pdf)
[Sudoku 3](IMAGES/Sudoku-Puzzle_09.pdf)
[Sudoku 4](IMAGES/Sudoku-Puzzle_10.pdf)
[Sudoku 5](IMAGES/Sudoku-Puzzle_11.pdf)




Relevant Packages:

- `opencv-python`: 4.3.0.36
- `numpy`: 1.19.1
- `tensorflow`: 2.2.0
- `scikit-learn`
- `keras`: 2.3.1

```bash
python MAIN.py
```

