# Face-Detection

Face detection, also known as facial detection, is a computer technology that uses artificial intelligence (AI) to find and recognize human faces in digital photographs. Face detection technology can be used to enable real-time surveillance and tracking of people in a variety of industries, such as security, biometrics, law enforcement, entertainment, and personal safety.

## Steps
1. Collect a video of the persons you want to add into face dection system of atleast - 20 secs

2. Read the video frames
     ```bash
        import glob as gb
        # Reading the video files
        folders = gb.glob('Video')
        list = []
        for folder in folders:
            for i in gb.glob(folder + '/*.mp4'):
                list.append(i)
   ```
3. Extraction of image frame
   Using open-cv extract the image frame from the videos
   ```bash
      # Capture the video
      current_frame = 0
      video = cv2.VideoCapture(frame_list[idx])
      while(True):
          _, frame = video.read()

          # Handel the exception error
          try:
              train_image = cv2.resize(frame, (256,256), interpolation=cv2.INTER_AREA)
          except:
              break

          cv2.imshow("Train", train_image)

          # Saving the image to its corresponding dataset folders
          cv2.imwrite(directory+str(current_frame)+'.jpg', train_image)
          length.append(current_frame)
          current_frame += 1

          interrupt = cv2.waitKey(10)
          if interrupt & 0xFF == 27: 
              break
      video.release()
      cv2.destroyAllWindows()
   ```
4. Image augmentation
   Image augmentation artificially creates training images through different ways of processing or combination of multiple processing, such as random        rotation, shifts, shear and flips.
 
## How to use the code?
To get started with the project.
```bash
   git clone https://github.com/kinley2-glitch/face-detection-using-deep-learning
```

## Authors
- [kinley2-glitch](https://github.com/kinley2-glitch)

