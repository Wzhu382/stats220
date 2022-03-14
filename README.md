# *stats220*
**This is the link to my stats220 repository** https://github.com/Wzhu382/stats220
## *About my purpose of creating this file*
* The first, of course, is because this is an assignment for my stats220, and it accounts for 4% of the total score! ! !







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
