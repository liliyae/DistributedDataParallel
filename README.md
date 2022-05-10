# DistributedDataParallel
A framework for training by DistributedDataParallel

这个框架借鉴于[Moco](https://github.com/facebookresearch/moco)，是非常棒的基于DistributedDataParallel的pytorch代码！感谢这份代码，让我在自己实现时面临的各种bug中顺利改出了单机多卡代码。
可以将train.py中的dataset换成自己的dataset、model换成任意model，并修改训练的传参部分即可
运行命令：
```bash
python train.py --dist-url 'tcp://localhost:10001' --multiprocessing-distributed --world-size 1 --rank 0 
```

遇到_pickle.UnpicklingError: pickle data was truncated，[解决方法 调小num-workers](https://blog.csdn.net/leo0308/articyle/details/123585400)

遇到RuntimeError: Expected to have finished reduction in the prior iteration before starting a new one.
[解决方法设置torch.nn.parallel.DistributedDataParallel的参数find_unused_parameters=True](https://blog.csdn.net/weixin_44966641/article/details/120385212)
