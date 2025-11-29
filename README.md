# Simple Lane Detection with Classical Computer Vision

This project demonstrates a **classical computer-vision pipeline** for detecting lane lines on the road using **OpenCV**.

The goal is to build an **interpretable, lightweight lane detection system** that mimics one of the fundamental components used in **autonomous vehicles** and **advanced driver-assistance systems (ADAS)**: detecting lane boundaries from camera images.

If you are new to self-driving cars and computer vision, this project gives you a solid hands-on understanding of how lane detection works **before** moving into deep learning.

---

## Business Statement

To develop a simple, efficient, and interpretable **lane detection system** that can serve as a foundational building block for autonomous driving and driver-assistance applications.

This project aims to:

- Detect lane boundaries from road images using classical image-processing techniques.
- Provide a clear, step-by-step pipeline that can be integrated into:
  - Lane keeping assist systems
  - Basic path-planning modules
  - Educational/self-driving research prototypes

By focusing on classic computer vision, this project helps illustrate how machines can understand road structure and lane geometry, contributing to **safer navigation and better situational awareness**.

---

##  Objectives

- Build a **basic lane detection pipeline** using OpenCV.
- Understand and implement each stage of the pipeline:
  - Image loading and visualization
  - Grayscale conversion
  - Gaussian blurring
  - Canny edge detection
  - Region of Interest (ROI) masking
  - Hough Line Transform
  - Lane line drawing/overlay
- Explain **why** each step is necessary in the context of lane detection.
- Produce a clear, visual output showing detected lane lines over the original image.

---

##  Features

### Classical Computer Vision Pipeline

This project implements a complete lane-detection pipeline using only classical methods—no deep learning:

1. **Image Loading & Visualization**
   - Read the road image.
   - Visualize it with Matplotlib to understand pixel dimensions (height and width).

2. **Grayscale Conversion**
   - Convert the image from RGB/BGR to grayscale.
   - Reduce complexity by working with a single intensity channel instead of three color channels.

3. **Gaussian Blurring**
   - Apply Gaussian blur to smooth the image.
   - Remove noise and small variations that can create false edges.

4. **Canny Edge Detection**
   - Detect strong edges corresponding to lane markings.
   - Reduce the image to its most important structural features.

5. **Region of Interest (ROI) Masking**
   - Define a polygon (often triangular or trapezoidal) where lanes are expected to appear.
   - Mask out irrelevant regions like the sky, buildings, and roadside objects.
   - Focus computation on the drivable area only.

6. **Hough Line Transform**
   - Detect straight lines from the edge map.
   - Group edge points into line segments likely to represent lane boundaries.

7. **Line Drawing & Overlay**
   - Draw the detected lane lines.
   - Overlay them on the original image for intuitive visualization.
   - Highlight where the system believes the lanes are.

---

### Clear Explanations for Each Step

The notebook/code is structured with comments and descriptions answering:

- **Why do we convert to grayscale?**
- **Why do we apply Gaussian blur?**
- **Why do we use Canny for edge detection?**
- **Why do we define a Region of Interest?**
- **Why do we use Hough Lines for lane detection?**

This makes the project suitable for:

- Learning
- Teaching
- Demonstrating core CV concepts in interviews or presentations

---

### Extensible Design

The current implementation works on **single images**, but the same pipeline can be extended to:

- Process **video frames** from a dashcam.
- Integrate into a simulation (e.g., CARLA, Gazebo, or custom driving datasets).
- Serve as a baseline for more advanced **deep-learning-based lane detection**.

---

## Results

The pipeline produces a final output where:

- Lane boundaries are detected from the Canny edge map.
- Only the relevant region on the road is used for Hough Transform.
- The detected lane lines are drawn and overlaid on the original image.

**Qualitative outcomes:**

- Lane lines are clearly highlighted on straight-road scenarios.
- The pipeline demonstrates how classical computer vision can approximate lane detection in good conditions (clear markings, daylight, simple backgrounds).

---

##  Observations

- When **Gaussian blur** is disabled, Canny detects too many edges, making lane detection unstable.
- Without **ROI masking**, Hough Transform often picks up building edges and other irrelevant structures.
- With a well-defined ROI and tuned Canny thresholds, the pipeline becomes much more stable and produces clean lane visualizations.



## Future Improvements

Possible directions to extend this project:

- **Video Lane Detection**
  - Apply the same pipeline on each frame of a video stream.
  - Smooth lane detection across frames using temporal filtering.

- **Polynomial / Curve Fitting**
  - Replace straight-line Hough detection with polynomial fitting for curved lanes.
  - Implement sliding-window techniques similar to those used in self-driving car research.

- **Deep Learning–Based Lane Detection**
  - Compare classical CV against neural-network-based lane segmentation.
  - Experiment with models like LaneNet, SCNN, or segmentation networks.



##  Requirements

- `numpy`
- `opencv-python`
- `matplotlib`

  ## About Me
I am a data science and machine learning practitioner with a strong passion for autonomous vehicles and computer vision, focused on building solutions that bridge research and real-world deployment.

Feel free to connect with me:

[Linkedlin](https://www.linkedin.com/in/patrickedosoma/)

[Email](edosomapatrick41@gmail.com)

## Contributions

Contributions and suggestions are welcome! Please open an issue or submit a pull request.



## Star This Repo

If you found this project helpful, please star ⭐️ it to show support!


