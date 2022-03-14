# *My code*
* some description: I have wasted a long time in researching how to solve the problem that the computer is not compatible with the magick package. I have not tried to do too much innovation. I am still in the groping stage of r. I simply try to combine some statements to make the whole look more concise. . I feel that the picture editing function of R is actually very interesting, and will do better next time.
```r
library(magick)
mememe <- image_read("https://p1.toutiaoimg.com/large/b7680000ff8759c64802")%>%
  image_scale(450)
after <- image_read("https://p3.itc.cn/images01/20210617/6965e770018d41998b54d9d981690f68.jpeg")%>%
  image_scale(450)

cat_grow <- image_append(c(mememe,after),stack = TRUE)

background_1<-image_blank(width = 500, height = 540, color = "orange") %>%
  image_annotate(text = "When orange cat\nwas little ~",
              color = "#000000",
                 size = 40,
                 font = "Impact",
                 gravity = 'center')

background_2<-image_blank(width = 500, height = 540, color = "orange") %>%
  image_annotate(text = "After few\nmonths ~",
                 color = "#000000",
                 size = 40,
                 font = "Impact",
                 gravity = 'center')

bgs<- image_append(c(background_1,background_2),stack = TRUE)

final <- image_append(c(cat_grow,bgs))
final
image_write(final, "my_meme.png")
```
##*The link back to stats220 page*
https://github.com/Wzhu382/stats220
