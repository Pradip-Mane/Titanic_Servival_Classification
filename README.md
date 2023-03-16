# Titanic_Servival_Classification 
- This is the legendary Titanic ML competition (Kaggle's competition)

- The sinking of the Titanic is one of the most infamous shipwrecks in history.

- On April 15, 1912, during her maiden voyage, the widely considered “unsinkable” RMS Titanic sank after colliding with an iceberg. Unfortunately, there weren’t enough lifeboats for everyone onboard, resulting in the death of 1502 out of 2224 passengers and crew.

- While there was some element of luck involved in surviving, it seems some groups of people were more likely to survive than others.

- In this challenge, we ask you to build a predictive model that answers the question: “what sorts of people were more likely to survive?” using passenger data (ie name, age, gender, socio-economic class, etc).

## Steps

### Import libraries

### Load Datasets
**observations from data in first Glance** 

    * PassengerID => serial no (no use in prediction)
    * Survived    => taget coloum (0=Not Survived, 1=Survived)
    * Pclass      => Passenger class( first class, 2nd, third )
    * Name        => passnger name 
                    * gernerally we delet the name column as it does not usefull, 
                    * but for creative ML algo we can use salvitation(Mr, Miss, or any other) 
                    * for prediction purpose and can improve the performance
                    
    * sex   => male, female
    * age   => age of passanger
    * sibsp => sibling and spouse
    * Parch => parent and children
    * Ticket => ticket details
    * fare => ticket fare
    * Cabin => Cabin no. (this may or may not be useful)
    * Embrked => from which port the came ontothe boat (this may or may not be useful)

### Data Preprocessing

    * there are only 891 rows in tatanic dataframe, 
    * cabin has almost all mising values(687) so we can drop that variable completely,
    * but what about age? age seems to be relevent feature for the prediction, 
    * we want to keep that variable but it has 177 missing values which we have to treat 

### Feature Engineering

    * Survived =>it is(target_variable) obivously relevent

    * Pclass => does a passenger class on the boat affet the their servivability?

    * sex => could a pasenges gender impact their servival rate? 

    * age => Does passenger age impact their servival rate?

    * sibsp => Does the number of relatives(sibling and spouse) on te boat affect a persons servivability?

    * Parch => Does the number of relatives(parent and children) on te boat affect a persons servivability?

    * fare => does the fair of person paid affect the persons servivability? may be- lets keep it

    * Embrked => does the persons point of embarkation matter? It depends on how the boat was filled? lets keep it




* Age, Cabin, and Embarked has missing values
* due large missing values we have alredy deleted cabin column

**for age**
* the standard procedure is
            * first check the Outlier 
            * if outlier present then use median else use mean
            
**we use some diffrent logic**
  *  Speaking roughly, we could say that the younger a passenger is, the more likely it is from to be in the 3rd class. the older a pasenger is the more likely it is from to be in the 1st class. so there is loose relationship between these variables. So, lets write a function that approximates a passener age, based on their class. from the box plot, it looks like the average age of 1st class passengers is about 37, 2nd class passenger is 29 and 3rd class passenger is 24
     
  *  find the each null value in the Age variable and for each null, checks the value of the Pcclass and assign an age value according to the average age of the passengers in that class
        

 Split the data

### 5. Train The SVM Classification Model

### 6. Evaluate the Performance

                            precision    recall  f1-score   support

                        0       0.81      0.87      0.84       388
                        1       0.75      0.67      0.71       234

                 accuracy                           0.79       622

                macro avg       0.78      0.77      0.78       622

             weighted avg       0.79      0.79      0.79       622


**Thumb Rule for overfitting is that**
   * test dataset prediction metrics(Accuracy) should be within 5% of the train dataset prediction metrics(Accuracy)
   * (sometimes 10%)
   * if it is within that 5% then model is **Not Overfitted**
   * if it is more than 5% then the model is **Overfitted**
   
**for this model**
   * accuracy of test dataset is 79% 
   * acuuracy of train dataset is 84%
   * i.e it is nearly within the band of 5% * 79% = 4%
   * (79% + 4% = 83% , 79% - 4% =75%) =(75%-83%)
   * it nearly within that range so we can say that our model is **Not Overfitted**
   
### 7. Pickling of Model
 
### 8. Model Deployment on render
1. README file
2. requirements.txt
3. app.py
4. style.css
5. main.html
6. Dockerfile
7. main.yaml

### 9. Deploy on Render

