# Inspiration
We embarked on our mission to clarify the fine line between truth and misinformation. In an era where politicians and influential figures, who are adept at manipulation, confidently present falsehoods, it becomes alarmingly easy for the public to be deceived without a second thought. This pervasive issue inspired us to develop CooCoo, a misinformation detection system, aimed at helping individuals discern fact from fiction at the touch of a finger.

# What it does
CooCoo is all about tackling and quashing misinformation in real-time. CooCoo is a two-part system that features both a physical hardware component and a connected mobile app. The physical bird model component features an embedded microphone with the ability to convert speech-to-text. Taking this data, the app then interprets it and, in the case that it hears something that is false, it sends the user a mobile notification through the app that states the brief sentence that it flagged as untrue. Upon clicking a notification, the user will be presented with a warning message stating that the associated statement/information may not be accurate and an associated link to a credible source that refutes the original statement. Then, once the user has clicked on a notification, they are able to click on either the ‘Save for Later’ button to keep this notification, along with the associated warning message and alternate information source, stored in the app, or the ‘Delete’ button to delete it from the app. Both buttons will return the user to the app’s home page.

# How we built it
For the current demo model, the speech-to-text portion of the system takes in audio directly from the laptop’s built-in microphone. (Due to physical hardware limitations, the current prototype of CooCoo is limited to the app and model Arduino microphone circuit that would hypothetically be implemented in the physical bird component to supplement the laptop’s built in microphone). This audio data is then sent to Google’s Cloud Speech API for transcription. Next, we separated these into individual sentences to send to the OpenAI API for processing. This processed data gets sent to an HTTP through the use of Flask, which the front end will receive and process. Flutter and Dart were used for the front-end development to create the visual effects and the error catches you see within the app. There were a lot of Flutter Packages imported into the framework to allow the calling of the Flask Server and import the information gained from the server.

# Challenges we ran into
Ideally, we would have created a bird model with clay to emulate the size and appearance of our physical hardware component. However, due to time and resource limitations, this was just not feasible, especially given that it was not determined to be as essential of a component to model and implement functionality in, unlike the speech-to-text technology and app components.

While we had also planned on implementing a fully-functional Arduino circuit with a microphone attachment, we realized that the hardware we had didn’t allow us to fulfill the input requirements for the model.

Another limitation that we ran into was that we didn’t have the time to train our own LLM from scratch, thus could not get the most recent up-to-date news.

Additionally, this project was the first time a majority of our group members worked with Flutter and Dart, which caused there to be a significant learning curve regarding front-end development in the beginning. Similarly, another obstacle we ran into throughout the process was a lack of experience with sharing data between different frameworks. This resulted in us being unsure about how to call and request data from another website.

# Accomplishments that we're proud of
We are extremely happy with how the CooCoo concept has come together. From a late concept pivot early Saturday morning to a working product that detects and alerts users of misinformation in real-time, we have achieved our ultimate vision. We are particularly very proud of our app's ability to call a request to the Flask server within the Flutter framework to allow a transfer of data.

# What we learned
With the front-end, we learned new ways to display our program in an app utilizing Flutter and Dart. With the back-end, we learned that the calling of API’s is suboptimal, especially when the server is local and cannot just reference any link.

# What's next for CooCoo
In the future, we hope to implement a locally-trained model to improve speed, accuracy, and reliability compared to the ChatGPT 4.0 model currently being used to detect and flag misinformation. We are also hoping to incorporate additional hardware deployment to improve immediacy and monetization (via a working physical bird component with a built-in microphone).
