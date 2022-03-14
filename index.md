# Assignment 1
* Due Date: 21st March, 2022

## Meme
This is my newly created meme.
![my_meme](/images/my_meme.png)
## Used R and {magick} package code
```
library(magick)

forecast <- image_read("./images/forecast.png") %>%
  image_scale(480) %>%
  image_extent("500x500",
               color = "#a30000")

reality <- image_read("./images/reality.png") %>%
  image_scale(480) %>%
  image_extent("500x500",
               color = "#a30000")

watch_text <- image_blank(width = 500,
                          height = 500,
                          color = "#fff8ae") %>%
  image_annotate(text = "\n\nWhat I watched in\n the weather forecast",
                 color = "#000000",
                 size = 50,
                 font = "Impact",
                 gravity = "north") %>%
  image_scale(480) %>%
  image_extent("500x500",
               color = "#a30000")

trust_text <- image_blank(width = 500,
                     height = 500,
                     color = "#f0b4ff") %>%
  image_annotate(text = "\n\nWhen I trust it...",
                 color = "#000000",
                 size = 50,
                 font = "Impact",
                 gravity = "north") %>%
  image_scale(480) %>%
  image_extent("500x500",
               color = "#a30000")

meme_photo <- c(forecast, reality) %>%
  image_append(stack = TRUE)

meme_text <- c(watch_text, trust_text) %>%
  image_append(stack = TRUE)

meme <- c(meme_photo, meme_text) %>%
  image_append()

meme <- image_scale(meme, 980) %>%
  image_extent("1000x1000",
               color = "#a30000")

image_write(meme, "./images/my_meme.png")
```
## Motivation of creating this meme
Have you ever trusted a weather forcast and turned out that the weather forcast was wrong?  
Prediction of weather is extrememly difficult as meteorologists are facing various *limitations*[1]:   
1. **Availability** of data
2. **Time allowed** to analyses the data
3. **Complexity** of weather events  

Even though new model and technology are developed every year, sometimes weather forecast might still go wrong.  

*This meme is to describe our feelings when a weather report completely goes wrong:* ***Frustration***.  

The 4-square style meme has long been popular in the internet.  
Below is an illustration of a 4-square meme:
| Photo 1 | Caption |
| --- | --- |
| **Photo 2** | **Caption** |

However, sometimes the readability of memes in this style is rather poor. Thus, I added border around the images and annotations to improve the readability of my meme.  
The two original images are border-free.  
![](/images/forcast.png)
![](/images/reality.png)  

Details of the meme image file:
* Format: png
* File size: 709 KB
* Resolution: 1000 x 1000

## Reference
[1] Tyler Herrington, “Why is the weather so hard to predict?” Let's Talk Science, 23-Sep-2019. [Online].  
Available: [https://letstalkscience.ca/educational-resources/stem-in-context/why-weather-so-hard-predict](https://letstalkscience.ca/educational-resources/stem-in-context/why-weather-so-hard-predict) [Accessed: 13-Mar-2022]
