# Lucas-Kanade Image Alignment+

![FC_sample_gif](https://github.com/cashiwamochi/LK20_ImageAlignment/blob/master/gif/FC.gif "ForwardCompositional")
![IC_sample_gif](https://github.com/cashiwamochi/LK20_ImageAlignment/blob/master/gif/IC.gif "InverseCompositional")
![ESM_sample_gif](https://github.com/cashiwamochi/LK20_ImageAlignment/blob/master/gif/ESM.gif "Efficient Second-Order Minimization")
 

### What is this ?
I implemented a planar tracking algorithm based on ***Lucas-Kanade 20 years frameworks*** **[1]** . You can try three algorithms, Forward Compositional, Inverse Compositional and Efficient Second-Order Minimization. This system returns a homography matrix and it is parametrized with SL3 in optimization. In addition, this system performs coarse-to-fine optimization using image-pyramid.

### How to Build, Run
```
mkdir build && cd build
cmake .. && make -j2
./LK20_tracker ../lenna.png
```

```LK_example.cc``` shows you how to use this framework.

#### Reference
```
[1] http://www.ncorr.com/download/publications/bakerunify.pdf
[2] http://campar.in.tum.de/pub/benhimane2007ijcv/benhimane2007ijcv.pdf
[3] http://www.robots.ox.ac.uk/~cmei/articles/single_view_track_ITRO.pdf
[4] https://ipsj.ixsq.nii.ac.jp/ej/?action=repository_action_common_download&item_id=77703&item_no=1&attribute_id=1&file_no=1
```

### Note
In dev-se3 branch, SE3(6-DoF) optimization is implemented. It can be built and works, but I cannot make sure that it's correct. My SE3 version worse than SL3 in convergence radius. I think that there should be no large effect in inconvergence radius. 

--------
### 何これ
Lucas-Kanade法による平面追跡を ***Lucas-Kanade 20 years frameworks*** **[1]** を参考にして実装した．ForwardCompositional，InverseCompositional,Efficient Second-Order Minimization を実装し収束範囲を広げるためにイメージピラミッドを用いた最適化を行う．また，二次元射影変換行列を求めるにあたってSL3で表現した．
