# neural style transfer

Neural style transfer is an optimization technique used to take three images, a content image, a style reference image (such as an artwork by a famous painter), and the input image you want to style -- and blend them together such that the input image is transformed to look like the content image, but “painted” in the style of the style image.
For example, let’s take an image of this turtle and Katsushika Hokusai's The Great Wave off Kanagawa:

Drawing Drawing
![image](https://github.com/user-attachments/assets/6b7c820f-3c7d-487b-9693-b2366e029423)

![image](https://github.com/user-attachments/assets/66d7ae65-c83f-4f10-8fa6-a12daceed947)

Image of Green Sea Turtle -By P.Lindgren [CC BY-SA 3.0 (https://creativecommons.org/licenses/by-sa/3.0)], from Wikimedia Commons

Now how would it look like if Hokusai decided to paint the picture of this Turtle exclusively with this style? Something like this?

![image](https://github.com/user-attachments/assets/fd8fd2f9-7b1c-4bbd-83fc-54624a1fda3e)











Now how would it look like if Hokusai decided to paint the picture of this Turtle exclusively with this style? Something like this?

Drawing
Is this magic or just deep learning? Fortunately, this doesn’t involve any witchcraft: style transfer is a fun and interesting technique that showcases the capabilities and internal representations of neural networks.

The principle of neural style transfer is to define two distance functions, one that describes how different the content of two images are ,  Lcontent , and one that describes the difference between two images in terms of their style,  Lstyle . Then, given three images, a desired style image, a desired content image, and the input image (initialized with the content image), we try to transform the input image to minimize the content distance with the content image and its style distance with the style image. In summary, we’ll take the base input image, a content image that we want to match, and the style image that we want to match. We’ll transform the base input image by minimizing the content and style distances (losses) with backpropagation, creating an image that matches the content of the content image and the style of the style image.
