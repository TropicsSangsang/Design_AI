# Design_AI
디자인 하기

!pip install --upgrade keras-cv

import keras_cv
import matplotlib.pyplot as plt

model = keras_cv.models.StableDiffusion(img_width=512, img_height=512, jit_compile=True)

def plot_images(images):
    plt.figure(figsize=(20, 20))
    for i in range(len(images)):
        ax = plt.subplot(1, len(images), i + 1)
        plt.imshow(images[i])
        plt.axis("off")
        plt.tight_layout()

images = model.text_to_image("design of parking tower with flying car", batch_size=3)

plot_images(images)
