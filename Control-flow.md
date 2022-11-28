---
title: "Control_Flow"
author: "AnindyaK"
date: "2022-11-28"
output: 
  html_document: 
    keep_md: yes
---



## R Markdown

This is an R Markdown document. Markdown is a simple formatting syntax for authoring HTML, PDF, and MS Word documents. For more details on using R Markdown see <http://rmarkdown.rstudio.com>.

When you click the **Knit** button a document will be generated that includes both content as well as the output of any embedded R code chunks within the document. You can embed an R code chunk like this:

5.2.4 Exercises

Q1:What type of vector does each of the following calls to ifelse() return?


```r
ifelse(TRUE, 1, "no")
```

```
## [1] 1
```

```r
ifelse(FALSE, 1, "no")
```

```
## [1] "no"
```

```r
ifelse(NA, 1, "no")
```

```
## [1] NA
```

```r
#the argument of ifelse() means test, yes and no. Ifelse returns the yes result when the test is TRUE and no result when FALSE. The NA returns a NA result.
```

Q2:Why does the following code work?


```r
x <- 1:10
if (length(x)) "not empty" else "empty"
```

```
## [1] "not empty"
```

```r
#the test is looking for a numeric vector which is fullfilled

x <- numeric()
if (length(x)) "not empty" else "empty"
```

```
## [1] "empty"
```

```r
#the test is looking for a numeric vector which is not fullfilled by the empty argument
```

5.3.3 Exercises

Q1:Why does this code succeed without errors or warnings?


```r
x <- numeric()
out <- vector("list", length(x))
for (i in 1:length(x)) {
  out[i] <- x[i] ^ 2
}
out
```

```
## [[1]]
## [1] NA
```

```r
#as we have seen before in the chapter the 1:length(x) basically means x=1-0 which could have been avoided by using seq_along(x) which would have generated an integer(0).
#when x[1] the output is NA but when x[0] it should give out 0 but somehow the code worked to give an unusual output.
```

Q2: When the following code is evaluated, what can you say about the vector being iterated?

```r
xs <- c(1, 2, 3)
for (x in xs) {
  xs <- c(xs, x * 2)
}
xs
```

```
## [1] 1 2 3 2 4 6
```

```r
#here x is taking the value of the xs and running it only once followed by the *2
```

Q3: What does the following code tell you about when the index is updated?

```r
for (i in 1:3) {
  i <- i * 2
  print(i) 
}
```

```
## [1] 2
## [1] 4
## [1] 6
```

```r
#index is updated in the beginning of each iteration
```
