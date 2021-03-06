---
title: "2020-05-16"
output: github_document
---

# `gt::web_image()` - i know this one!

```
{r old, echo = TRUE, warning = FALSE}
library(gt)
library(tibble)

acnh_bugs_n <- tribble(
  ~name, ~price, ~location, ~time, ~months, ~image,
  "Yellow butterfly", 160, "Flying", "4 AM - 7 PM", "Mar - Jun, Sep - Oct", "https://vignette.wikia.nocookie.net/animalcrossing/images/f/fa/NH-Icon-yellowbutterfly.png",
  "Peacock butterfly", 2500, "Flying by Hybrid Flowers", "4 AM - 7 PM", "Mar - June", "https://vignette.wikia.nocookie.net/animalcrossing/images/8/8f/NH-Icon-peacockbutterfly.png",
  "Atlas moth", 3000, "On Trees", "7 PM - 4 AM", "Apr - Sep", "https://vignette.wikia.nocookie.net/animalcrossing/images/6/6a/NH-Icon-atlasmoth.png",
  "Centipede", 300, "Hitting Rocks", "4 PM - 11 PM", "Sep - June", "https://vignette.wikia.nocookie.net/animalcrossing/images/0/00/NH-Icon-molecricket.png",
  "Snail", 250, "On Rocks and Bushes (Rain)	", "All Day", "Jan - Dec", "https://vignette.wikia.nocookie.net/animalcrossing/images/b/b1/NH-Icon-snail.png",
  "Mole cricket", 500, "Underground", "All Day", "Nov - May", "https://vignette.wikia.nocookie.net/animalcrossing/images/3/30/NH-Icon-centipede.png"
)

# Add an image via URL
# Use text_transform() to apply a function to text
# Use cells_body() to specify which column will have the function applied
# Then specify the function! In this case, use web_image() to insert an image from a URL
acnh_bugs_n %>%
  gt() %>%
  text_transform(
    locations = cells_body(
      columns = vars(image)
    ),
    fn = function(x) {
      web_image(x, height = 50)
    }
  )
```

# `gt::cols_move_to_start()` - new to me!

```{r new, echo = TRUE}
library(gt)
library(tibble)

acnh_bugs_n <- tribble(
  ~name, ~price, ~location, ~time, ~months, ~image,
  "Yellow butterfly", 160, "Flying", "4 AM - 7 PM", "Mar - Jun, Sep - Oct", "https://vignette.wikia.nocookie.net/animalcrossing/images/f/fa/NH-Icon-yellowbutterfly.png",
  "Peacock butterfly", 2500, "Flying by Hybrid Flowers", "4 AM - 7 PM", "Mar - June", "https://vignette.wikia.nocookie.net/animalcrossing/images/8/8f/NH-Icon-peacockbutterfly.png",
  "Atlas moth", 3000, "On Trees", "7 PM - 4 AM", "Apr - Sep", "https://vignette.wikia.nocookie.net/animalcrossing/images/6/6a/NH-Icon-atlasmoth.png",
  "Centipede", 300, "Hitting Rocks", "4 PM - 11 PM", "Sep - June", "https://vignette.wikia.nocookie.net/animalcrossing/images/0/00/NH-Icon-molecricket.png",
  "Snail", 250, "On Rocks and Bushes (Rain)	", "All Day", "Jan - Dec", "https://vignette.wikia.nocookie.net/animalcrossing/images/b/b1/NH-Icon-snail.png",
  "Mole cricket", 500, "Underground", "All Day", "Nov - May", "https://vignette.wikia.nocookie.net/animalcrossing/images/3/30/NH-Icon-centipede.png"
)

# Relocate a column without altering the underlying data!
# Use cols_move_to_start() to move the image column to the start
acnh_bugs_n %>%
  gt() %>%
  text_transform(
    locations = cells_body(
      columns = vars(image)
    ),
    fn = function(x) {
      web_image(x, height = 50)
    }
  ) %>%
  cols_move_to_start(columns = vars(image))
---
title: "2020-05-16"
output: github_document
---

# `gt::web_image()` - i know this one!

```{r old, echo = TRUE, warning = FALSE}
library(gt)
library(tibble)

acnh_bugs_n <- tribble(
  ~name, ~price, ~location, ~time, ~months, ~image,
  "Yellow butterfly", 160, "Flying", "4 AM - 7 PM", "Mar - Jun, Sep - Oct", "https://vignette.wikia.nocookie.net/animalcrossing/images/f/fa/NH-Icon-yellowbutterfly.png",
  "Peacock butterfly", 2500, "Flying by Hybrid Flowers", "4 AM - 7 PM", "Mar - June", "https://vignette.wikia.nocookie.net/animalcrossing/images/8/8f/NH-Icon-peacockbutterfly.png",
  "Atlas moth", 3000, "On Trees", "7 PM - 4 AM", "Apr - Sep", "https://vignette.wikia.nocookie.net/animalcrossing/images/6/6a/NH-Icon-atlasmoth.png",
  "Centipede", 300, "Hitting Rocks", "4 PM - 11 PM", "Sep - June", "https://vignette.wikia.nocookie.net/animalcrossing/images/0/00/NH-Icon-molecricket.png",
  "Snail", 250, "On Rocks and Bushes (Rain)	", "All Day", "Jan - Dec", "https://vignette.wikia.nocookie.net/animalcrossing/images/b/b1/NH-Icon-snail.png",
  "Mole cricket", 500, "Underground", "All Day", "Nov - May", "https://vignette.wikia.nocookie.net/animalcrossing/images/3/30/NH-Icon-centipede.png"
)

# Add an image via URL
# Use text_transform() to apply a function to text
# Use cells_body() to specify which column will have the function applied
# Then specify the function! In this case, use web_image() to insert an image from a URL
acnh_bugs_n %>%
  gt() %>%
  text_transform(
    locations = cells_body(
      columns = vars(image)
    ),
    fn = function(x) {
      web_image(x, height = 50)
    }
  )
```

# `gt::cols_move_to_start()` - new to me!

```{r new, echo = TRUE}
library(gt)
library(tibble)

acnh_bugs_n <- tribble(
  ~name, ~price, ~location, ~time, ~months, ~image,
  "Yellow butterfly", 160, "Flying", "4 AM - 7 PM", "Mar - Jun, Sep - Oct", "https://vignette.wikia.nocookie.net/animalcrossing/images/f/fa/NH-Icon-yellowbutterfly.png",
  "Peacock butterfly", 2500, "Flying by Hybrid Flowers", "4 AM - 7 PM", "Mar - June", "https://vignette.wikia.nocookie.net/animalcrossing/images/8/8f/NH-Icon-peacockbutterfly.png",
  "Atlas moth", 3000, "On Trees", "7 PM - 4 AM", "Apr - Sep", "https://vignette.wikia.nocookie.net/animalcrossing/images/6/6a/NH-Icon-atlasmoth.png",
  "Centipede", 300, "Hitting Rocks", "4 PM - 11 PM", "Sep - June", "https://vignette.wikia.nocookie.net/animalcrossing/images/0/00/NH-Icon-molecricket.png",
  "Snail", 250, "On Rocks and Bushes (Rain)	", "All Day", "Jan - Dec", "https://vignette.wikia.nocookie.net/animalcrossing/images/b/b1/NH-Icon-snail.png",
  "Mole cricket", 500, "Underground", "All Day", "Nov - May", "https://vignette.wikia.nocookie.net/animalcrossing/images/3/30/NH-Icon-centipede.png"
)

# Relocate a column without altering the underlying data!
# Use cols_move_to_start() to move the image column to the start
acnh_bugs_n %>%
  gt() %>%
  text_transform(
    locations = cells_body(
      columns = vars(image)
    ),
    fn = function(x) {
      web_image(x, height = 50)
    }
  ) %
  cols_move_to_start(columns = vars(
Kamm
