# ClassificationProblem

We want to build a machine learning model, which is able to identify:
- apples
- cats
- cups
- dogs
- keyboards
- people


In `./dataset` directory there are pictures of all categories:

    .
    └── dataset
         |── apple
         |    |── apple1.jpg
         |    |── apple2.jpg
         |    ...
         |    └── applen.jpg
         |── cat
         |    |── cat1.jpg
         |    |── cat2.jpg
         |    ...
         |    └── catn.jpg
         |── cup
         |    |── cup1.jpg
         |    |── cup2.jpg
         |    ...
         |    └── cupn.jpg
         |── dog
         |    |── dog1.jpg
         |    |── dog2.jpg
         |    ...
         |    └── dogn.jpg
         |── keyboard
         |    |── keyboard1.jpg
         |    |── keyboard2.jpg
         |    ...
         |    └── keyboardn.jpg
         └── person
              |── person1.jpg
              |── person2.jpg
              ...
              └── personn.jpg
   

We have to feed a machine learning algorithm with these pictures and tell the algorithm what these pictures are. 
We have to show to the algorithm as much apple pictures as possible and tell it that these are apples.
And do the same with all other categories.


#
##### First task

1. Write a function, `get_features`, that takes an image path, image_path, as argument and returns shape, color and texture feautures concatenated in one list.
Use `fd_hu_moments` to get shape features, `fd_haralick` to get texture features and `fd_histogram` to get color features.

2. Write a function, `get_data`, that takes `./dataset` as argument, walks through dataset, loads each image, extract their features and returns two lists:
- `data` (list of lists): each list should contain image features .
- `target` (list of strings): each string is a label (`apple`, `cups`, `keyboards`)

So, each time you add a feature to `data` list, you also add its corresponding label to `target` list.
Make sure not to mix the order you put images and its corresponding category into lists, so if the first item
of `data` list is apple-features, the first element of `target` list should be `apple`.

Use `get_features` to get image features.


3. Encode labels.
Since all data in `data` list are already numbers, we don't need to encode them. But since `target` contains strings, we have to encode them.

Use `LabelEncoder` from `sklearn.preprocessing` 


4. Split the dataset into train and test data.
Use `train_test_split` from `sklearn.model_selection`


5. Train the model
Use `GaussianNB` from `sklearn.naive_bayes` and its `fit` method.


6. Evaluate the model
Use `score` method of `GaussianNB`


7. Load new data
Write a function that walks through `new_data` directory, processes each found image, extract their features and returns a list of lists, `new_data`, where each list contains concatenated image features.
Use `fd_hu_moments` to get shape features, `fd_haralick` to get texture features and `fd_histogram` to get color features.


8. Predict new data and print the results
Use `predict` method of `GaussianNB`.


9. Bring all pieces together and make the project work. 
