## This project is an improved version of PFClust algorithm implemented in Java.

**Author:** Khadija Musayeva  
**Date:** 20.06.2013  
**Last update:** 31.03.2015  

### Requirements

To run this program you need Java SE Runtime Environment 1.7. For more information about Java environment refer to http://www.oracle.com/technetwork/java/javase/downloads/index.html

### Configuration  

PFClust program reads an input file (similarity matrix) from the input directory and writes the results into the output directory.  
The input and output directories should be specified in the config.txt file.

NOTE: The input file should contain space separated similarity values. See example input files provided with the package.

NOTE: The config.txt should be in the same directory as PFClust.jar

**Contents of config.txt**  
   
	Example:
    
   	input_dir=data/input/
   	output_dir=data/output/
  	data=cath_11.txt,Density.txt,group_10.txt
   
   
- **input_dir**  
   - The input directory is where all similarity matrices are located.  
   - The value of the input_dir should end with forward slash.  
   - It should be correctly specified relative or absolute path.  
   - In the example above the input_dir is in the same directory as PFClust.jar

 - **output_dir**  
   - The output directory where PFClust program writes the results.  
   - The value of the output_dir should end with forward slash.  
   - It should be correctly specified relative or absolute path.  
   - Currently output_dir is in the same directory as PFClust.jar

- **data**  
   - It specifies the list of input files (similarity matrices).  
   - It should contain at least one file.  
   NOTE: These files should exist in the input_dir

### Running Instructions

1. Open the command line
2. ``` cd path_to/PFClust.jar ``` 
3.```java -jar PFClust.jar```

Note: You might need to change file permissions.

While the program is running it will print out the following:

	Example:

	File: s_2.txt
	Clusters=2    Silhouette=0.656    Dunn_Index=3.977    Threshold=0.94
	Execution time = 1.76 sec 

- **File** – the name of the input file  
- **Result of the program** – Number of clusters, Silhouette, Dunn_index, Threshold  
- **Execution time** – the elapsed time of clustering

### Output  
The program writes its output to ```output_dir```. The output is written into two files:

### Data file  

The related information about the clustering output is saved in ```name_of_the_input_file.data```.

Contents of the file:

Example: 
numclust    sil    dunn    threshold
16          0.649  1.595  0.944


- **numclust** – Number of clusters  
- **sil** – Silhouette  
- **dunn** – Dunn Index  
- **threshold** – Threshold  

### Cluster file  

1. **Name of the file**  
   The name of the file is a concatenation of [name of the input file, number of clusters, silhouette, Dunn index, threshold] followed by `.clu`  
   Example: `Density16064915950944.clu`

2. **Contents of the file**  
   Element index | Cluster index
   ```
   1	9
   2	9
```
   
