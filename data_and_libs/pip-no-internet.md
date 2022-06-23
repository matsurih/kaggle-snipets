- インターネット利用不可のコンペでpip installしたいときのsnipets

### 1. ローカルでpipのpackageをdownloadする
```shell
$ pip download facenet-pytorch -d ./facenet_pytorch
```

### 2. packageをkaaggle datasetにuploadする
```shell
$ kaggle datasets init -p ./facenet_pytorch  # create and init dataset-metadata.json
$ vim ./facenet_pytorch/dataset-metadata.json  # if you need
$ kaggle datasets create -p ./facenet_pytorch
```

### 4. kernel内でpip installする
```shell
!pip install facenet-pytorch --no-index --find-links=file:///kaggle/input/facenet_pytorch/ 
```
