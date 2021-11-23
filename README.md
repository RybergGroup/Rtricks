# Rtricks
Collection of usefull R code and instructions. It is mainly made for internal use but shared if it could be of use for anybody else.

## Color by value
`heat.colors` can be used to generate a a color map to use for graphs. For example if you have a vector of values for branches

    colours100 <- heat.colors(100,1)
    br_col<-c()
    scale_fun <- function (x) {
        return ((99/(max(br_rates)-min(br_rates)))*(x-min(br_rates))+1)
    }

    for (i in 1:length(br_rates)) br_col[i] <- colours100[scale_fun(br_rates[i])]
