# Image_Processing_CUDA

# Image Processing Projects

This repository contains various image processing projects implemented in C++ with CUDA and standard CPU implementations. The projects include:

1. **Box Blur Filter (CUDA and CPU)**
2. **Sharpening Filter (CUDA and CPU)**
3. **Red Channel Manipulation (CUDA and CPU)**

## Overview

1. **Box Blur Filter**: Applies a box blur filter to an image, blurring it by averaging pixel values within a kernel.
2. **Sharpening Filter**: Applies a sharpening filter to an image to enhance edges and details.
3. **Red Channel Manipulation**: Modifies the red channel of an image, for instance, by increasing its intensity.

## Requirements

- **CUDA Toolkit**: Ensure you have the CUDA Toolkit installed for compiling CUDA programs.
- **OpenCV**: Install OpenCV for image reading, processing, and writing.
- **C++ Compiler**: A compatible C++ compiler (e.g., `g++`).

## Building and Running the CUDA Programs

1. **Navigate to the Directory**: Open a terminal and navigate to the directory containing the `.cu` files.

2. **Compile the CUDA Programs**:
    ```sh
    nvcc -o blur blur.cu `pkg-config --cflags --libs opencv4`
    nvcc -o sharpening sharpening.cu `pkg-config --cflags --libs opencv4`
    nvcc -o red red.cu `pkg-config --cflags --libs opencv4`
    ```

3. **Run the Programs**:
    - **Box Blur**:
      ```sh
      ./blur
      ```
    - **Sharpening**:
      ```sh
      ./sharpening
      ```
    - **Red Channel Manipulation**:
      ```sh
      ./red
      ```

   Ensure that the input image (`images.jpeg`) is in the same directory as the executable or specify the correct path.

## Building and Running the CPU Programs

1. **Navigate to the Directory**: Open a terminal and navigate to the directory containing the `.c` files.

2. **Compile the CPU Programs**:
    ```sh
    g++ -o blur_cpu blur.c `pkg-config --cflags --libs opencv4`
    g++ -o sharpening_cpu sharpening.c `pkg-config --cflags --libs opencv4`
    g++ -o red_cpu red.c `pkg-config --cflags --libs opencv4`
    ```

3. **Run the Programs**:
    - **Box Blur**:
      ```sh
      ./blur_cpu
      ```
    - **Sharpening**:
      ```sh
      ./sharpening_cpu
      ```
    - **Red Channel Manipulation**:
      ```sh
      ./red_cpu
      ```

   Ensure that the input image (`images.jpeg`) is in the same directory as the executable or specify the correct path.

## Viewing Output Images

To view the output images in Google Colab:

1. **Upload Images**:
    ```python
    from google.colab import files
    uploaded = files.upload()
    ```

2. **Display Images Using Matplotlib**:
    ```python
    import matplotlib.pyplot as plt
    import matplotlib.image as mpimg

    # Display the blurred image
    img_blur = mpimg.imread('output_blur.jpeg')
    plt.imshow(img_blur)
    plt.title('Blurred Image')
    plt.axis('off')  # Hide axes
    plt.show()

    # Display the sharpened image
    img_sharpened = mpimg.imread('output_sharpened.jpeg')
    plt.imshow(img_sharpened)
    plt.title('Sharpened Image')
    plt.axis('off')  # Hide axes
    plt.show()

    # Display the red channel modified image
    img_red_modified = mpimg.imread('output_red_modified.jpeg')
    plt.imshow(img_red_modified)
    plt.title('Red Channel Modified Image')
    plt.axis('off')  # Hide axes
    plt.show()
    ```

## Notes

- Make sure to adjust the paths to the image files and executables as necessary.
- The image files should be in the JPEG format. Update the file paths if using different formats.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgements

- The CUDA programming guide and OpenCV documentation were used for reference.
https://github.com/ishaanagarwal11/CUDA-image-processing/blob/main/README.md - followed this url and done this.
For any questions or issues, please open an issue in the GitHub repository or contact the author.

