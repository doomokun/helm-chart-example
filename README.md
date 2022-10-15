### helm repo used git pages ###

必要file：
1. helm package
2. index.yaml

git repo: https://github.com/doomokun/helm-chart-example.git

---
# 製作chart repo筆記
- git flow 一樣，一樣係git push
- resource需要一個index.yaml，內有chart資訊
- 加一個helm package，由```$ helm package #{helm create NAME}```創建，會係一個.tgz
- ```$ helm repo index . --url https://github.com/doomokun/helm-chart-example.git ```，index.yaml 更新 .tgz URL資訊，即git pages url
- 使用git pages需要去git repo設定，去git repo setting -> pages -> set branch
- 第一次要得一陣，佢會show git pages URL
- 之後curl test佢，例：```$ curl https://gree-gorey.github.io/helm-example/index.yaml```
---

# Chart Commands
加入repo
```
$ helm repo add #{repo-name} https://gree-gorey.github.io/helm-example
$ helm repo list
```
List repo charts
```
$ helm search repo
```
Install
```
$ helm install #{chart name you like} #{helm search repo NAME}
```
睇Install左既release
```
$ helm list
$ helm delete #{NAME}
$ helm delete --purge #{NAME}
```

---
# 使用現有chart repo筆記
- repo 係一個chart既git repo
- 加左就可以install，直接run落k8s
- upgrade係係呢個install度做version control
- 用pull係成個resource pull落黎
---
Init repo git pages (https://medium.com/containerum/how-to-make-and-share-your-own-helm-package-50ae40f6c221)
---