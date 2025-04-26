GPTCelltype: Automatic cell type annotation with GPT-4
====

## Installation 

To install the latest version of GPTCelltype package via Github, run the following commands in R:

## 安装数信院GPT注释的两个包
```{r eval = FALSE}
install.packages("remotes")
remotes::install_github("EddieLv/api_sxy", force=T)
remotes::install_github("EddieLv/GPTCelltype_sxy", force=T)
```

##  🚀 Quick start with Seurat pipeline 
## 按照下面代码跑通测试

```{r eval = FALSE}

# Load packages
library(GPTCelltype_sxy)
library(api_sxy)

#跟数信院客服领取独享key
Sys.setenv(OPENAI_API_KEY = 'sk-XXXX')

# Assume you have already run the Seurat pipeline https://satijalab.org/seurat/
# Cell type annotation by GPT-4
# markers是一个list, 也可以是Seurat FindAllMarkers()出来的结果
markers <- list("C0" = c("Ager", "Hopx", "Pdpn")) # 这里的例子为了方便是一个自定义list
# model表示使用哪个大语言模型，gpt-4-turbo很聪明，也可以替换成其他模型
# tissuename表示你提供的markers属于哪个组织，比如肺癌单细胞测序、胚胎发育单细胞测序等
res <- gptcelltype(markers, tissuename = "lung", model = 'gpt-4-turbo')
res

```

### ⚠️Warning: avoid sharing your API key with others or uploading it to public spaces.
### ⚠️警告:不要把你的个人key分享给别人
