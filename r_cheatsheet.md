# R Cheatsheet

## map values

```R
library(dplyr)

x <- c("a", "b", "c", NA, "e")

recode(x, a = "A", .missing = "X")
# [1] "A" "b" "c" "X" "e"

recode(x, a = "A", .missing = "X", .default="D")
# [1] "A" "D" "D" "X" "D"
```

Using `case_when` allows for more advanced mapping based on conditions.
All cases not caught will become `NA`, this can be remedied by adding `TRUE ~ x` as
the last condition

```R
library(dplyr)

x <- c("a", "b", "c", NA, "e")
y <- c("A", "B", "C", NA, "E")

case_when(x == "a" ~ "AA", is.na(x) ~ "was NA", x == "E" ~ "*")
# [1] "AA" NA NA "was NA" NA 
case_when(x == "a" ~ "AA", is.na(x) ~ "was NA", x == "E" ~ "*", TRUE ~ x)
# [1] "AA" "b" "c" "was NA" "e" 

# You can mix dependan variables as long as they have the same length
case_when(x == "a" ~ "AA", is.na(x) ~ "was NA", y == "E" ~ "Y")
# [1] "AA" NA NA "was NA" "*" 

```
