- インターネット利用不可のコンペでpip installしたいときのsnipets
- kaggle downloadする環境のpythonのバージョンとkaggle kernelのpythonのバージョンを一致させる必要がある
  - 面倒であればすべてkaggel kernel上で実行するのが安全
  - step1を/kaggle/working以下に吐き出すようにしたkernelを作成し、outputをdatasetとする

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
