# Stats 220 Assignment 1 part A
## Reason for this meme 
1) I genrally likes Dogs more than Cats however after seeing the affection of Professor. Anna I have start to appericate cats to a greater degree.
2) The reason I converted this into a Crypto meme is because I am really into Crypto. I have seen a lot of people lose money and I thought
this image would portray that nicely.

![](My_meme.png)
### Code

library(magick)

newbies <- image_read("https://images.unsplash.com/photo-1513245543132-31f507417b26?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1935&q=80") %>%
  image_scale(400)
  
chads  <- image_read("https://images.unsplash.com/photo-1533738363-b7f9aef128ce?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=435&q=80") %>%
  image_scale(400)
  
newbies1 <- image_blank(width = 500, 
                        height = 500, 
                        color = "#000000") %>%
  image_annotate(text = "Newbie cats losing $1000 in Crypto",
                 color = "#FFFFFF",
                 size = 30,
                 font = "Impact",
                 gravity = "center")

chads1 <- image_blank(width = 500, 
                      height = 500, 
                      color = "#000000") %>%
  image_annotate(text = "Giga-Cat losing $10,000 in Crypto",
                 color = "#FFFFFF",
                 size = 30,
                 font = "Impact",
                 gravity = "center")

first_row <- c(newbies, newbies1) %>%
  image_append()

second_row <- c(chads, chads1) %>%
  image_append()

mymeme <- c(first_row, second_row) %>%

  image_append(stack = TRUE)

image_write(mymeme, "mymeme.png")
