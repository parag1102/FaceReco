FaceReco
========

Face recognition using PCA and LDA

    Consider the ORL database of faces to perform face recognition using PCA and
    LDA. The dataset is available at (http://www.cl.cam.ac.uk/research/dtg/attarchive/facedatabase.html).
    The database consists of gray scale face image of 40 persons and there are 10 images of each
    person. There are 40 directories in the zip archive provided in the above link.
    Each directory corresponds to a person and there are 10 images files in each
    directory (named as s1.pmg to s10.pmg). Each image is in 92x112 gray image. For
    detail information of the dataset, refer to README file of the dataset.

    Create the training and test datasets as follows:
        
        PCA Training dataset: Convert each image into into a row vector i.e., 92x112 to
        10304 dimensional row vector. Construct training D using the first nine images
        (s1.pmg to s9.pmg) of all 40 subjects. Construct the centered matrix X. You
        should centered across different subjects. Then, reduce the dimension of the
        centered matrix to a dimension of k using PCA.

        PCA Test dataset: Same as training using last image (s10.pmg). Reduce it to the
                          same k-dimension.

        A typical PCA based recognition algo:

            0. Perform dimensionality reduction for both the training and test datasets
            using PCA
            1. Select an image from the faces in the eigenspace of the test example.
            2. Measure the distance between this image and images in the training example.
            Use an appropriate distance measure.
            3. Classify the image by the closest face in the training dataset.
            4. Repeat for all images.

        LDA training: Construct centered matrix using the same approach as that of PCA.
        Reduce dimension using multi class Fisher's LDA approach.

        LDA testing: Same as training. (You ca also try using the PCA testing procedure.
        
        A typical LDA based recognition algo:

            0. Perform dimensionality reduction for both the training and test datasets
            using Multi-class LDA i.e., reduce to c-1 dimension (c-1 eigenvectors of
            S_{w}^{-1}S_{B}). C is the number of classes.
            1. Select an image from the faces in the eigenspace of the test example.
            2. Measure the distance between this image and images in the training example.
            Use an appropriate distance measure.
            3. Classify the image by the closest face in the training dataset.
            4. Repeat for all images.
            
