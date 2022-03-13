# Stats220 Assignment 1
## Part A
### Meme
This is my newly created meme.
![my_meme](/images/my_meme.png)
### Used R and {magick} package code
```
library(magick)

forcast <- image_read("./images/forcast.png") %>%
  image_scale(480) %>%
  image_extent("500x500", color = "#a30000")

reality <- image_read("./images/reality.png") %>%
  image_scale(480) %>%
  image_extent("500x500", color = "#a30000")

watch_text <- image_blank(width = 500,
                     height = 500,
                     color = "#fff8ae") %>%
  image_annotate(text = "\n\nWhen I watched the\nweather forcast",
                 color = "#000000",
                 size = 50,
                 font = "Impact",
                 gravity = "north") %>%
  image_scale(480) %>%
  image_extent("500x500", color = "#a30000")

trust_text <- image_blank(width = 500,
                     height = 500,
                     color = "#f0b4ff") %>%
  image_annotate(text = "\n\nWhen I trust it...",
                 color = "#000000",
                 size = 50,
                 font = "Impact",
                 gravity = "north") %>%
  image_scale(480) %>%
  image_extent("500x500", color = "#a30000")

meme_photo <- c(forcast, reality) %>%
  image_append(stack = TRUE)

meme_text <- c(watch_text, trust_text) %>%
  image_append(stack = TRUE)

meme <- c(meme_photo, meme_text) %>%
  image_append()

meme <- image_scale(meme, 980) %>%
  image_extent("1000x1000", color = "#a30000")

image_write(meme, "./images/my_meme.png")
```
### Motivation of creating this meme
Have you ever trusted a weather forcast and turned out that the weather forcast was wrong?  
Prediction of weather is extrememly difficult as it involves some many uncertainties [1]  
Even though new model and technology are developed every year, sometimes weather forecast might still go wrong.  
This meme is describing my feeling when a weather report completely goes wrong.  

## Reference
[1] Tyler Herrington, “Why is the weather so hard to predict?” Let's Talk Science, 23-Sep-2019. [Online].  
Available: [https://letstalkscience.ca/educational-resources/stem-in-context/why-weather-so-hard-predict](https://letstalkscience.ca/educational-resources/stem-in-context/why-weather-so-hard-predict) [Accessed: 13-Mar-2022]
