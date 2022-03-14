![](https://sweatpantsandcoffee.com/wp-content/uploads/2017/10/940x450-National-Cat-Day-GIFs.jpg)
# My code

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
