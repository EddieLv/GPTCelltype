GPTCelltype: Automatic cell type annotation with GPT-4
====

## Installation 

To install the latest version of GPTCelltype package via Github, run the following commands in R:
```{r eval = FALSE}
remotes::install_github("EddieLv/openai")
remotes::install_github("EddieLv/GPTCelltype")
```

##  🚀 Quick start with Seurat pipeline 


```{r eval = FALSE}

#跟数信院客服领取独享key
Sys.setenv(OPENAI_API_KEY = 'your_openai_API_key')

# Load packages
library(GPTCelltype)
library(openai)

# Assume you have already run the Seurat pipeline https://satijalab.org/seurat/
# "obj" is the Seurat object; "markers" is the output from FindAllMarkers(obj)
# Cell type annotation by GPT-4
res <- gptcelltype(markers, model = 'gpt-4', mine_url="http://sxycloud.cn:3000")

# Assign cell type annotation back to Seurat object
obj@meta.data$celltype <- as.factor(res[as.character(Idents(obj))])

# Visualize cell type annotation on UMAP
DimPlot(obj,group.by='celltype')
```

### ⚠️Warning: avoid sharing your API key with others or uploading it to public spaces.
### ⚠️警告:不要把你的个人key分享给别人
