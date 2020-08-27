# VideoTitling

Official github repo for the paper
> Shengyu Zhang, Ziqi Tan, Jin Yu, Zhou Zhao, Kun Kuang, Tan Jiang, Jingren Zhou, Hongxia Yang and Fei Wu. Comprehensive Information Integration Modeling Framework for Video Titling, In SIGKDD Conference on Knowledge Discovery and Data Mining (KDD), 2020.

## Dataset

We now provide the dataset we use in the paper, i.e., T-VTD (**Tabao Video Titling Dataset**). There are 90,000 <video, comment, attributes, title> quadruples in T-VTD.
(We note that Gavotte is trained and tested on a subset with 84,394 samples due to data pre-processing as demonstrated in our paper.)

We only provide the vectorial representations of videos, including the global represenation of frames and the landmark features used by Gavotte, due to the copyright of these videos, i.e., the desensitized version.

- Each file in the **global128_9w** folder is named as `${videoid}.npy`, containing a matrix of shape `[N_{frame}, D_{frame}]`, representing the vectorial representation of frames.

- Each file in the **local64_9w** folder is also named as `${videoid}.npy`, containing a matrix of shape `[N_{frame}, N_{landmark}, D_{frame}]`, representing the vectorial representation of landmarks.

The textual data and annotations are in the **multicate_info_final.json** file. Each element contains the following information:

```
{
${videoid}:
  'comment': ${video comment},
  'category': ${product category}, # belonging to [童装(children wear), 女装(women wear), 男装(men wear)]
  'attributes': [${product attribute 1}, ${product attribute 2}, ..., ${product attribute N}],
  'video_id': ${videoid},
  'title': ${video title}，
  'split': ${belong to which dataset split} $ [0(train), 1(val), 2(test), 3(not used)],
}
```
We note that the 3(not used) split denotes those data samples not used by Gavotte during either training, validation or testing. These samples are removed after data preprocessing as illustrated in the paper.

Due to the **data-release regularities** of Alibaba, we now **remove** the original google drive download link. Dataset now can be downloaded from [Tianchi](https://tianchi.aliyun.com/dataset/dataDetail?dataId=75173).



## Code
Due to a tight schedual, the source code of Gavotte is not ready for a clean release right now. We will pick up the code refracting procedure if we have a time table.



