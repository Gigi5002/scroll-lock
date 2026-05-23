SCROLL-LOCK 📱🚫

A Python program that uses your webcam to detect when you're looking down at your phone (aka doomscrolling) and roasts you to get back to work! Features an automatic rickroll video popup when caught!
Features

    Real-time face and eye tracking using OpenCV
    Doomscrolling detection - detects when you tilt your head down
    Motivational roasting - displays harsh but motivating messages when caught
    Rickroll punishment - automatically plays rickroll.mp4 when you're doomscrolling
    Auto-close video - stops the video when you return to good posture
    Automatic fallback - works with dlib or OpenCV Haar Cascades

Installation
Quick Install

pip install -r requirements.txt

Manual Install
Basic (OpenCV only)

pip install opencv-python numpy

Advanced (Better accuracy with dlib)

pip install opencv-python numpy dlib

# Download the face landmarks model
wget http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2
bunzip2 shape_predictor_68_face_landmarks.dat.bz2

Setup

    Place your rickroll.mp4 file in the project directory
    Make sure QuickTime Player (macOS), VLC (Linux), or default video player (Windows) is installed

Usage

python main.py

    The program will open your webcam
    Look at the screen normally = Green "Good posture!" message
    Look down at your phone = Red warning with roasting messages + RICKROLL VIDEO AUTOPLAY 🎵
    Return to good posture = Video automatically closes
    Press 'q' to quit

How It Works

    Face Detection: Detects your face using either dlib or OpenCV Haar Cascades
    Posture Analysis: Tracks head tilt and eye position
    Doomscroll Detection: Triggers when:
        Your head tilts down significantly
        Your face moves to the lower portion of the frame
        Your eyes are positioned low in your face region
    Roasting: Displays motivational (harsh) messages every 3 seconds when caught
    Rickroll: Automatically opens and plays rickroll.mp4 when doomscrolling detected
    Auto-stop: Closes the video when you return to normal posture

Sample Roasts

    "You'll fail if you don't stop!"
    "Your dreams called - they want your attention back!"
    "Future you is watching. They're disappointed."
    "The algorithm wins again. Pathetic."
    "PUT. THE. PHONE. DOWN. NOW."

Requirements

    Python 3.13+
    Webcam
    OpenCV (opencv-python)
    NumPy
    dlib (optional, for better accuracy)
    QuickTime Player (macOS) or VLC (Linux) or Windows Media Player (Windows)
    rickroll.mp4 file in project directory

Customization

Edit main.py to customize:

    Roast messages: Modify the self.roasts list (line 31-45)
    Detection sensitivity: Adjust face_position_ratio thresholds (line 118, 124)
    Roast frequency: Change self.roast_cooldown (line 50, default: 3 seconds)
    Video file: Change self.rickroll_path (line 55) to use a different video

Troubleshooting

Video doesn't autoplay on macOS:

    Make sure QuickTime Player is installed
    The script uses AppleScript to force autoplay

Video doesn't close automatically:

    The script sends a kill command to QuickTime Player
    You may need to manually close it if the process detection fails

Detection is too sensitive/not sensitive enough:

    Adjust the thresholds in detect_doomscroll_opencv() or detect_doomscroll_dlib()
    Change face_position_ratio > 0.55 to a higher (less sensitive) or lower (more sensitive) value

License

Free to use. Stay productive! 💪