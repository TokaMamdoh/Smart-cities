# Anomaly detection
***
## 1 Overview
The main objective of this assignment is to detect 2 different anomalies are injected into the trajectory of the QBot, and thus it supposedly reflects onto the trajectory of the QDrone as an anomaly: 

the drone will follow the bot by moving out of the trajectory temporarily, and the bot enters a specific area that is a restricted region for the QDrone. we have a dataset from a 2-minute experiment. We will extract 4 attributes from the dataset: “follower x data”, “follower y data”, “leader x data” and “leader y data” (‘x’ and ‘y’ refers to coordinate). We will implement and compare the performance of different machine learning algorithms which are SVM, PCA, KNN, and DBSCAN. Then We will plot the model results alongside with data and compare unsupervised models with respect to accuracy, precision (for both anomaly and normal instances), recall (for both anomaly and normal instances) and F1 scores (for both anomaly and normal instances).

## 2 Methodology
### 2.1 Install important packages
• Markupsafe package: MarkupSafe escapes characters so text is safe to use in HTML and XML. Characters that have special meanings are replaced so that they display as the actual characters. This mitigates injection attacks, meaning untrusted user input can safely be displayed on a page.

• Pycaret package: is an open-source, low-code machine learning library in Python that automates machine learning workflows.

• Jinja2: The main idea of Jinja is to separate data and template. This allows you to use the same template but not the same data.

### 2.2 Modeling:
• First: Setup initializes the training environment and creates the transformation pipeline. Setup function must be called before executing any other function. It takes one mandatory parameter: data. All the other parameters are optional.

• Second: Creating several models. 

  - **SVM**: is a supervised machine learning algorithm used for both classification and regression. Though we say regression problems as well its best suited for classification. The objective of SVM algorithm is to find a hyperplane in an N-dimensional space that distinctly classifies the data points.

  - **KNeighborsClassifier**: is used to implement classification based on voting by nearest k-neighbors of target point, t, while RadiusNeighborsClassifier implements classification based on all neighborhood points within a fixed radius, r, of target point, t.

  - **Principal Component Analysis (PCA)**: is a technique that comes from the field of linear algebra and can be used as a data preparation technique to create a projection of a dataset prior to fitting a model.

  - **DBSCAN**: (Density-Based Spatial Clustering of Applications with Noise) is an unsupervised machine learning technique used to identify clusters of varying shape in a data set
  
  ## 3 Visualize anomalies
  ### 3.1 SVM
  ![](https://github.com/TokaMamdoh/Smart-cities/blob/9724ad0c8b86c84c352fc07c2a2da400eff2da2d/Anomaly%20detection/images/SVM%20anomalies.PNG)
  
  TSNE plot 
  
  ![](https://github.com/TokaMamdoh/Smart-cities/blob/9724ad0c8b86c84c352fc07c2a2da400eff2da2d/Anomaly%20detection/images/SVM-TSNE.PNG)
  ### 3.2 KNN
  ![](https://github.com/TokaMamdoh/Smart-cities/blob/9724ad0c8b86c84c352fc07c2a2da400eff2da2d/Anomaly%20detection/images/KNN%20anomalies.PNG)
  
  TSNE plot
  
  ![](https://github.com/TokaMamdoh/Smart-cities/blob/9724ad0c8b86c84c352fc07c2a2da400eff2da2d/Anomaly%20detection/images/KNN-TSNE.PNG)
  ### 3.3 PCA
  ![](https://github.com/TokaMamdoh/Smart-cities/blob/9724ad0c8b86c84c352fc07c2a2da400eff2da2d/Anomaly%20detection/images/PCA%20anomalies.PNG)
  
  TSNE plot
  
  ![](https://github.com/TokaMamdoh/Smart-cities/blob/9724ad0c8b86c84c352fc07c2a2da400eff2da2d/Anomaly%20detection/images/PCA-TSNE.PNG)
  ### 3.4 DBSCAN
  TSNE plot
  
  ![](https://github.com/TokaMamdoh/Smart-cities/blob/9724ad0c8b86c84c352fc07c2a2da400eff2da2d/Anomaly%20detection/images/DBSCAN-TSNE.PNG)
  
  ## 4 Result 
  | Models | Accuracies|
  | ---    | ---       |
  | SVM    | 93%       |
  | KNN    | 90%       |
  | PCA    | 93%       |
  | DBSCAN | 95%       |
  
  ## 5 Conclusion
In this project, we need to detect the anomalies injected into the trajectory of the bot, and thus, it supposedly reflects onto the trajectory of the drone. Firstly, we implement four models which are SVM, PCA, KNN, and DBSCAN to compare between them. After that, we plotted the TSNE plot to visualize the result of Qbot and Qdrone in each model. Then we compute the evaluation of each model using the true label found in Dataset_to_be_used_in_performance_comparison.csv. the results showed that the DBSCAN model produce a better accuracy score with 95%. PCA & SVM give an accuracy score of 93%. Finally, KNN produce the worst accuracy score with 90%.
