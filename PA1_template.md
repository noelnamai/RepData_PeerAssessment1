# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data


```r
data <- read.csv(unz("activity.zip", "activity.csv"),
                 sep=",",
                 header=TRUE,
                 stringsAsFactors=FALSE)
head(data, 10)
```

```
##    steps       date interval
## 1     NA 2012-10-01        0
## 2     NA 2012-10-01        5
## 3     NA 2012-10-01       10
## 4     NA 2012-10-01       15
## 5     NA 2012-10-01       20
## 6     NA 2012-10-01       25
## 7     NA 2012-10-01       30
## 8     NA 2012-10-01       35
## 9     NA 2012-10-01       40
## 10    NA 2012-10-01       45
```

## What is mean total number of steps taken per day?

### Make a histogram of the total number of steps taken each day.


```r
library(ggplot2)
qplot(date, 
      data=data, 
      weight=steps, 
      geom="histogram", 
      xlab="Date", 
      ylab="Total Number of Steps") + 
    geom_histogram(colour="black", fill="red") + 
    theme(axis.text.x=element_text(angle=-90, hjust=0))
```

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2.png) 

### Calculate and report the mean and median total number of steps taken per day.


```r
mean(na.omit(data$steps))
```

```
## [1] 37.38
```

```r
median(na.omit(data$steps))
```

```
## [1] 0
```

## What is the average daily activity pattern?

### Make a time series plot (i.e. type = "l") of the 5-minute interval (x-axis) and the average number of steps taken, averaged across all days (y-axis)




## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
