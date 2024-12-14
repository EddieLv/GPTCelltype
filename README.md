GPTCelltype: Automatic cell type annotation with GPT-4
====

## Installation 

To install the latest version of GPTCelltype package via Github, run the following commands in R:
#不管你有没有安装过，重装以下两个包
```{r eval = FALSE}
install.packages("remotes")
remotes::install_github("EddieLv/openai")
remotes::install_github("EddieLv/GPTCelltype")
```

##  🚀 Quick start with Seurat pipeline 


```{r eval = FALSE}

#跟数信院客服领取独享key
Sys.setenv(OPENAI_API_KEY = 'your_openai_API_key')

# 卸载加载的包
detach("package:GPTCelltype", unload = T)
detach("package:openai", unload = T)

# Load packages
library(GPTCelltype)
library(openai)

# Assume you have already run the Seurat pipeline https://satijalab.org/seurat/
# "obj" is the Seurat object; "markers" is the output from FindAllMarkers(obj)
# Cell type annotation by GPT-4
# markers可以是一个list
markers <- list("C0" = c("Ager", "Hopx", "Pdpn"))
res <- gptcelltype(markers, tissuename = "lung", model = 'gpt-4o', mine_url="http://sxycloud.cn:3000")
res

```

### ⚠️Warning: avoid sharing your API key with others or uploading it to public spaces.
### ⚠️警告:不要把你的个人key分享给别人
