# Test



## Background

This project is used to reconstruct three-dimensional model of pearl OCT slice image and analyze roundness to evaluate pearl shape grade. Pearl OCT slice images were processed by NLM, adaptive local threshold and Marching cube method. The above processing calls the methods in avizo. Deriving 3D models into ply files. The three-dimensional model is imported into the ply file, and the pearl surface point set is obtained by using the region growing algorithm. The 3D coordinates of the local surface points are input into the spherical surface fitting algorithm to obtain the pearl fitting sphere. The local roundness fraction is obtained according to the shape data of the pearl fitting sphere. OCT volume scanning was carried out at different positions of the same pearl, and the local roundness fractions at different positions were counted. The average value of local roundness fraction (LRF) was calculated according to the number of scanning to obtain the global roundness fraction (GRF).The flowchart is are shown in Fig 1.

#### Fig 1

![image](https://github.com/wodouwudi/md_test/blob//Flowchart.png)

​	We use the diameter difference method to classify the roundness of pearls, that is, the maximum thickness and minimum thickness of pearls are measured by a jewelry thickness gauge. The maximum thickness is set as , and the minimum thickness is set as . The difference between and is set to . Calculated pearl diameter difference percentage (Pd):
$$
Pd\%=100(\frac{d}{x}+ \frac{d}{x})/2
$$
The lower the Pd % is, the better the pearl roundness grade is, and vice versa. At the same time, referring to the “National Standard of the People’s Republic of China GB/T18781-2008”, is divided into four roundness grades, and the classification error is ± 0.1 % (Pd). Details are shown in Table 1. Oval-grade pearls contain some pear-shaped pearls and flat-shaped pearls.

#### Table 1 Roundness Grading of Standard Samples

| Pearl Grade             | Pd (%)         |
| ----------------------- | -------------- |
| Perfect Roundness  (PR) | 0 - 1.5 (±0.1) |
| Roundness (RD)          | 1.5 - 5 (±0.1) |
| Near Roundness  (NR)    | 5 - 10 (±0.1)  |
| Oval (OV)               | >10 (±0.1)     |

​	The experiment scanned 59 pearl samples from all over the world, and each pearl scanned four regions. A total of 236 OCT slice images were obtained by scanning, with 256 images in each group. A total of 5 pearls were misidentified, and the recognition rate reached 93 %. We upload the .ply file and present it in the sample folder, Shown in Table 2. Each sample scanned four different regions, so each sample had 4 .ply files.

#### Table 2

| Sample number | Pd (%)  | GRF      |
| :------------ | ------- | -------- |
| 1             | 0.549%  | 44.69628 |
| 2             | 0.816%  | 104.1754 |
| 3             | 1.439%  | 108.1874 |
| 4             | 1.872%  | 138.634  |
| 5             | 2.529%  | 148.2113 |
| 6             | 3.608%  | 174.0701 |
| 7             | 5.742%  | 213.9538 |
| 8             | 6.942%  | 267.0914 |
| 9             | 9.864%  | 298.5088 |
| 10            | 13.198% | 319.5435 |
| 11            | 20.000% | 426.1282 |
| 12            | 20.000% | 527.9425 |



## Requirements

The programming language uses C + + (visual studio 2015) and Matlab (2018), also you need to install PCL 1.8.1(C++). Although visual studio can be programmed jointly with Matlab, the setting is very troublesome. To allow users to run projects as quickly as possible, we separate the code. When the C + + program runs out, you will get the txt file with pearl surface point coordinates. The Matlab program gets these points and then simulates the sphere and calculates the GRF, while the output is saved to excel file.
