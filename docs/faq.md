# Object detection

[Article on EN](https://becominghuman.ai/tensorflow-object-detection-api-tutorial-training-and-evaluating-custom-object-detector-ed2594afcf73)

[Article on RU](https://habr.com/ru/company/nix/blog/422353/)

TF Record [origin](https://github.com/datitran/raccoon_dataset)

Label Image [GitHub](https://github.com/tzutalin/labelImg)

## Tensorflow 2

TF2 converter [origin](https://gist.github.com/nitroxplunge/fdd750465f7ae55afc0d43d37ef65ef5)

Tensorflow models [issue](https://github.com/tensorflow/models/issues/2031)

Protocol Buffers [download](https://github.com/protocolbuffers/protobuf/releases)

Clone Tensorflow repository

```
cd models/research
```

Protoc folder for windows

```
../../../protoc/bin/protoc object_detection/protos/*.proto --python_out=.
```

Train example

```
python train.py --batch_size 100 --dataset ./train.tfrecord --val_dataset ./test.tfrecord --epochs 10 --classes ./data/voc2012.names
```

Test

```
python detect.py --image ./images/6.jpeg --classes ./data/voc2012.names --weights ./checkpoints/yolov3_train_4.tf
```

If has error `Paddings must be non-negative:` than add flag --yolo_max_boxes
