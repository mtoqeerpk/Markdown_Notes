## some general
* [dplyr introduction ](https://r4ds.had.co.nz/transform.html)
* [Tibbles] (https://r4ds.had.co.nz/tibbles.html)
* [Pipes](https://r4ds.had.co.nz/pipes.html)
* [What is Tidy Data?](http://statseducation.com/Introduction-to-R/modules/tidy%20data/tidy-data/)
* [Tidyverse packages] (https://www.tidyverse.org/packages/)
* [Chapter 4 The tidyverse] (https://rafalab.github.io/dsbook/tidyverse.html)
* [Chapter 20 Introduction to data wrangling] (https://rafalab.github.io/dsbook/introduction-to-data-wrangling.html)

###  List of tidyverse packages
` tidyverse_packages()`

```
Loading tidyverse: ggplot2
Loading tidyverse: tibble
Loading tidyverse: tidyr
Loading tidyverse: readr
Loading tidyverse: purrr
Loading tidyverse: dplyr
Conflicts with tidy packages ---------------------------------------------------
filter(): dplyr, stats
lag():    dplyr, stats
 [1] "broom"     "dplyr"     "forcats"   "ggplot2"   "haven"     "httr"     
 [7] "hms"       "jsonlite"  "lubridate" "magrittr"  "modelr"    "purrr"    
[13] "readr"     "readxl"    "stringr"   "tibble"    "rvest"     "tidyr"    
[19] "xml2"      "tidyverse"

```

####  What are the double colons (::) in R?

```
There may be multiple functions with the same name in multiple packages. 

The double colon operator allows you to specify the specific function you want:

package::functionname

df <- dplyr::data_frame(
  year = c(2015, NA, NA, NA), 
  trt = c("A", NA, "B", NA)
)

```
As you probably have looked up the help page by now usage of :: helps to access the exact function from that specific package. When you load dplyr you probably got a message as follows..

```
The following objects are masked from ‘package:base’:
       intersect, setdiff, setequal, union
```

So, for instance, if you would like to use intersect function from dplyr or base package, you need to specify using the :: double colons. Usage will be as follows

```
mtcars$model <- rownames(mtcars)
first <- mtcars[1:20, ]
second <- mtcars[10:20, ]
dplyr::intersect(first, second)
base::intersect(first, second)

```
### [What are Conflicts?]( http://statseducation.com/Introduction-to-R/modules/getting%20started/packages/)

Conflicts happen when packages have functions with the same names as other functions. This is OK when you prefer the function in a package like tidyverse rather than some other function. Basically the last package loaded in will mask over other functions if they have common names.

We can see a further example of this below:


```
library(MASS)
##
## Attaching package: 'MASS'
## The following object is masked from 'package:dplyr':
## 
##     select

```

