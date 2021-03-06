Loading the Auto+MPG data
================

Data downloaded from <http://archive.ics.uci.edu/ml/datasets/Auto+MPG> 2-27-2019

Data loaded into R as follows.

    start_columns = c(0, 7, 11, 22, 33, 44, 51, 55)
    widths <- c(start_columns[-1], 120) - start_columns
    auto_mpg <- read.fwf("auto-mpg.data.txt", widths = widths,
                         stringsAsFactors = FALSE)
    colnames(auto_mpg) <-  c("mpg",
                             "cylinders",
                             "displacement",
                             "horsepower",
                             "weight",
                             "acceleration",
                             "model_year",
                             "origin",
                             "car_name")
    auto_mpg$horsepower <- as.numeric(auto_mpg$horsepower)
    auto_mpg$origin <- factor(auto_mpg$origin)
    saveRDS(auto_mpg, "auto_mpg.RDS")
