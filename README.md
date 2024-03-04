# Classifying Wheelchair Direction from EEG Signals

## Background

Technology has significant potential to improve the lives of people with various disabilities, including limited movement or movement disorders. There are many potential applications in this area, one of which is improving mobility through wheelchair usage.

Particularly for individuals with limited movement, developing wheelchairs with the ability to move without muscular input from the individual would be of huge benefit. A recent approach is to use the brain signals that would usually communicate with the muscles to instead communicate with a technological interface, allowing control of the wheelchair.

The key challenge in this area is interpreting the brain signals in order to allow control through thought. Machine learning is indicated as a potential solution due its ability to process huge amounts of data, determine patterns and make predictions.

## Project Goals

The client would like a system that has the ability to interpret an individuals desire motion in the four basic directions of movement - left, right, forward and backward.

## Dataset Content

Dataset: Wheel Chair EEG Signals ([Kaggle link](https://www.kaggle.com/datasets/mneebahmd/wheel-chair-eeg-signals))

The dataset comprises the following columns (*taken from the dataset description on Kaggle*):

* Start Timestamp: The starting timestamp of the window.
* End Timestamp: The ending timestamp of the window.
* FFT Result: Fast Fourier Transform (FFT) result of the signal within the window.
* Mean: Mean value of the signal within the window.
* Max: Maximum value of the signal within the window.
* Standard Deviation: Standard deviation of the signal within the window.
* RMS: Root Mean Square (RMS) value of the signal within the window.
* Kurtosis: Kurtosis value of the signal within the window.
* Skewness: Skewness value of the signal within the window.
* Peak-to-Peak: Peak-to-peak amplitude of the signal within the window.
* Abs Diff Signal: Absolute difference of the signal within the window.
* Alpha Power: Power in the alpha band of the signal within the window.
* Beta Power: Power in the beta band of the signal within the window.
* Gamma Power: Power in the gamma band of the signal within the window.
* Delta Power: Power in the delta band of the signal within the window.
* Theta Power: Power in the theta band of the signal within the window.
* Label: The corresponding label for the window. 0 for Backward, 1 for Left, 2 for Right, 3 for Forward.


## Business Requirements
* The client would like an assessment of which features are most significant in predicting intended direction, in order to understand what data is most important to be collected in order to optimize the process
* The client would like to be able to predict from EEG data which direction a user is visualizing moving in. Forward, left and right are more important indicators than backward, which is used rarely and could be achieved by turning around. In this context, precision is the key indicator as we need the model to be able to interpret the user's intentions correctly. Therefore, the client requires that as a starting point, precision on forward, left and right should be at least 0.7.


## Hypothesis and how to validate?
* List here your project hypothesis(es) and how you envision validating it (them)


* Hypothesize that it is possible to interpret an intended direction based on the EEG signals of an individual imagining a movement. This will be validated by data analysis, investigating whether there are patterns in the data that correlate with the target, and whether a model can be trained to predict the intended direction from the EEG data.

* Hypothesize that left and right signals will be harder to differentiate from each other, with more similar signals than forward or backward. Therefore, expected that model will perform better on forward and backward classification. Rationale: bi-symetrical animals, including humans, tend to make occasional mistakes distinguishing between left and right. This might be due to the fact that the difference is "arbitrary", in relation to our bodies - left and right are symetrical, so there is no immediate distinction, whereas in front or behind have more obvious differences relative to our bodies. Therefore, it is hypothesized that the EEG signals for left and right visualization will be more similar than any other pair of directions, leading to lower performance in predicting these classes. This will be validated by assessing model performance, and whether left and right have lower overall performance, and also tend to be mislabeled as each other, when compared to the other two directions.

* Hypothesize that the frequency bands will not contribute equally to the tasks, and specifically that beta and gamma bands are likely to be the most significant. These bands of brain activity are related to external attention and concentration, as opposed to the other three which are associated with more restful or introverted states (see, for example, this [Science Direct article](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/brain-waves)).

## The rationale to map the business requirements to the Data Visualizations and ML tasks

* The ML task is a multi-class classification problem with four target labels


## ML Business Case

### Direction classifier

* We want an ML model that can predict which direction an individual is visualizing moving in, based on EEG data
* Processed EEG data has been provided, so the dataset is tabular data. The data is largely numerical, except for the target, which is categorical. The data is labeled.
* The customer requested a dashboard with an embedded ML model
* A fully-functioning brain-computer interface will likely need more development, but success for the client means showing that it is make a connection between brain activity and intended movement, and an indication of what variables may be most important in enabling this prediction. Therefore, informative plots conveying information about key features and a reasonable precision, set at 0.7, on precision for left, right and forward directions (see above for rationale) are key outcomes.
* The data is shared under a non-commercial share-alike license. All data is anonymous. Therefore there are no privacy or concerns.
* The project inputs are a table of processed data from EEG measurements of individuals envisioning intended movement. The ouputs will be plots and a ML pipeline and model.
* The client will benefit by gaining an better understanding of how brain signals can be interpreted to derive an intent to move, thus bringing them closer to a functioning brain-computer interface that will improve the lives of movement-impaired customers or patients.


## Dashboard Design
* List all dashboard pages and their content, either blocks of information or widgets, like buttons, checkboxes, images, or any other item that your dashboard library supports.
* Later, during the project development, you may revisit your dashboard plan to update a given feature (for example, at the beginning of the project you were confident you would use a given plot to display an insight but subsequently you used another plot type).


## Unfixed Bugs
* You will need to mention unfixed bugs and why they were not fixed. This section should include shortcomings of the frameworks or technologies used. Although time can be a significant variable to consider, paucity of time and difficulty understanding implementation is not a valid reason to leave bugs unfixed.

## Deployment
### Heroku

* The App live link is: https://YOUR_APP_NAME.herokuapp.com/ 
* Set the runtime.txt Python version to a [Heroku-20](https://devcenter.heroku.com/articles/python-support#supported-runtimes) stack currently supported version.
* The project was deployed to Heroku using the following steps.

1. Log in to Heroku and create an App
2. At the Deploy tab, select GitHub as the deployment method.
3. Select your repository name and click Search. Once it is found, click Connect.
4. Select the branch you want to deploy, then click Deploy Branch.
5. The deployment process should happen smoothly if all deployment files are fully functional. Click now the button Open App on the top of the page to access your App.
6. If the slug size is too large then add large files not required for the app to the .slugignore file.


## Main Data Analysis and Machine Learning Libraries
* Here you should list the libraries you used in the project and provide an example(s) of how you used these libraries.


## Credits 

* In this section, you need to reference where you got your content, media and extra help from. It is common practice to use code from other repositories and tutorials, however, it is important to be very specific about these sources to avoid plagiarism. 
* You can break the credits section up into Content and Media, depending on what you have included in your project. 

### Content 

- The text for the Home page was taken from Wikipedia Article A
- Instructions on how to implement form validation on the Sign-Up page was taken from [Specific YouTube Tutorial](https://www.youtube.com/)
- The icons in the footer were taken from [Font Awesome](https://fontawesome.com/)

### Media

- The photos used on the home and sign-up page are from This Open-Source site
- The images used for the gallery page were taken from this other open-source site



## Acknowledgements (optional)
* Thank the people that provided support through this project.

