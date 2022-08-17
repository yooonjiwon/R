# Principal Component Analysis
[Websites for detail](http://www.sthda.com/english/articles/31-principal-component-methods-in-r-practical-guide/112-pca-principal-component-analysis-essentials/)

## Packages
```r
library(FactoMineR)
library(factoextra)
```

## Import Dataset
```r
df <- readxl::read_xlsx('data.xlsx')
```

## Select variables for PCA
```r
df1 <- df[,c(2:5)]
```

## PCA
```r
df1.pca <- PCA(df1, graph=FALSE)
```

## Visualization
```r
df$group <- as.factor(df$group)

fviz_pca_biplot(df1.pca, 
                pointsize = 2.5,
                col.ind = df$group, palette = "jco", 
                addEllipses = TRUE, label = "var",
                col.var = "black", repel = TRUE,
                legend.title = "group") 
```
