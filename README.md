# Generating HDR image from a sequence of multi-exposure shots and evaluate them with different methods. 



HDR stands for high dynamic range. Dynamic range is simply the range of the lightest tones to the darkest tones within a photo. Put another way — it’s a measure of the light intensities from the highlights to the shadows. The higher dynamic range your camera has, the closer the photo will compare to what an eye can see. This means that you’ll be able to capture more details in the shadows that might otherwise appear pure black, and you’ll be able to see details in the highlights that might otherwise be washed out with white. 





## Dataset:

Burst photography for high dynamic range and low-light imaging on mobile cameras

Samuel W. Hasinoff, Dillon Sharlet, Ryan Geiss, Andrew Adams, Jonathan T. Barron,
Florian Kainz, Jiawen Chen, and Marc Levoy ACM Transactions on Graphics (Proc.
SIGGRAPH Asia 2016), 35(6), 12 pp.


## Example

HDR image from proposed method


![image](https://user-images.githubusercontent.com/58158450/168421059-4cea486f-4717-4eea-b0fa-ffc6159c737d.png)


![image](https://user-images.githubusercontent.com/58158450/168421066-94af10a7-1644-4c84-9181-520e9f3fd845.png)



## Usage

Here's a minimal example to see the gamma transformation of few images.For 

https://colab.research.google.com/drive/1OnwSc6au_8igxSjT-fW4eupwH_x0ROI7?usp=sharing


def gamma_trans(img, gamma):
    gamma_table=[np.power(x/255.0,gamma)*255.0 for x in range(256)]
    gamma_table=np.round(np.array(gamma_table)).astype(np.uint8)
    return cv2.LUT(img,gamma_table)

## Implementation details

We have analyzed the different methods and compared it with our method for generating best HDR image.


![image](https://user-images.githubusercontent.com/58158450/168420983-8c905e0a-667a-4792-895b-833b0996f92e.png)



## Citation

https://arxiv.org/abs/2106.01439

https://learnopencv.com/high-dynamic-range-hdr-imaging-using-opencv-cpp-python/

Debevec method: 
http://www.pauldebevec.com/Research/HDR/debevec-siggraph97.pdf

Robertson method: 
https://resources.mpi-inf.mpg.de/tmo/EG05_HDRTutorial_Complete.pdf

Mertens fusion: 
https://www.researchgate.net/publication/4295602_Exposure_Fusion

Reinhard Tonemap: 
https://www.cl.cam.ac.uk/~rkm38/pdfs/mantiuk08datm.pdf

https://resources.mpi-inf.mpg.de/tmo/EG05_HDRTutorial_Complete.pdf

https://ieeexplore.ieee.org/abstract/document/8350767

