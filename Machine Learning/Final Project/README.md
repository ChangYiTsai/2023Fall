# Development of a model that generates rhythmic drum music matching the individual's heartbeat
## INTRODUCTION
 In today’s business world, more and more people often work too much, sleep
 poorly, stress out, have bad habits and a broken routine. Meditation is a well
 known mental exercise, relaxation and rebooting will be much easier if a person
 starts practicing it. One can reduce stress, increase calmness and clarity, and
 promote happiness by listening to special kinds of music while meditating.
 Therefore, the development of a model, which will help to practice
 meditation, improve overall well-being on one’s own and calm your mind is
 relevant.
 The core idea is creating music that aligns with an individual's heartbeat,
 thus personalizing the rhythm to the listener's physiological state.
 Tasks of the work:
 1. Research existence applications on reducing stress with music.
 2. Finding ways to improve existing applications and create something new.
 3. Choose an appropriate dataset of music.
 4. Creating a program algorithm.
 5. Development of a Python program that generates rhythmic drum music
 matching the individual's heartbeat.
 6. User trial.
To solve the problems, research methods are used, namely:‒‒
 Analysis and generalization of information from the Internet.
 Analysis of the properties of existing applications.
 Practical value of this work lies in the possibility of applying the
 developed model in meditation devices and tools, as well as a soundtrack for
 exercise or fitness routines, and in the fact that the model created is ready for use.
 ## METHODOLOGY
 In the project, to generate the meditation music based on heart beat, a
 methodology was used that includes a well-known machine learning LSTM model
 approach.
 Long Short Term Memory networks– usually just called “LSTMs”– are a
 special kind of RNN, capable of learning long-term dependencies [2].
 The project's methodology revolves around using LSTM to generate drum
 music sequences.
 ### Overview of sequential nature of music
 #### 1. Temporal patterns:
 Drum patterns in music have inherent temporal structures. These include
 rhythms, beats, and the timing of drum hits, which form a sequence over time.
 #### 2. Dependencies:
 Certain drum beats or patterns often depend on preceding beats. For
 example, a drum fill might typically lead into a chorus, or certain rhythms might be
 characteristic of specific musical genres.
 The motivation for building a LSTM based neural network originates from
 the thought that drum patterns are highly repetitive and can therefore be modeled
 quite well by LSTMs since they do not rely on recurring themes of any kind.
### How LSTMs Work with Drum Sequences
 #### 1. Learning Drum Patterns:
 An LSTM model can be trained on a dataset of drum sequences (like the
 Groove MIDI dataset) to learn the typical patterns and structures in drum music.
 This involves understanding timing, velocity, and which drum components (snare,
 bass, hi-hat, etc.) are struck in sequences.
 #### 2. Memory cells:
 LSTMs have memory cells that can maintain information over longer
 sequences. This feature is particularly useful in music, where the relevance of a
 past beat or rhythm might extend over several measures.
 #### 3. Predicting the next beat:
 After training, the LSTM model can predict the next beat in a sequence
 based on the previous beats. This predictive capability is the core of generating
 new drum music.
 ### Generating Drum Music with LSTMs
 #### 1. Starting Seed:
 The generation process begins with a seed input, which can be a set of initial
 beats or rhythms.
 #### 2. Sequential Generation:
 The model uses this seed to generate the next beat. This new output is then
 fed back into the model as part of the input for the next step. This loop continues,
 allowing the LSTM to generate a sequence of drum beats.
#### 3. Variability and Creativity:
 LSTMs can introduce variability and creativity in the generated music.
 While they learn from existing patterns, the stochastic nature of the prediction
 process can lead to new and interesting drum sequences.
 ### Application in Synchronizing with Heartbeat
 #### 1. Adaptation:
 The LSTM model can adapt the tempo or intensity of the generated drum
 pattern to match the user's heartbeat. This requires additional processing to align
 the model's output with real-time heartbeat data.
 #### 2. Real-time Interaction:
 For effective synchronization, the model needs to operate in real-time or
 near-real-time, adjusting to the changing heartbeat data.
 By harnessing LSTMs' ability to handle and predict sequential data, we wish
 to create a dynamic and responsive system that not only generates rhythmic drum
 music but also synchronizes it with physiological data, creating a personalized
 musical experience
## Dataset
 We used the Groove MIDI Dataset for the purpose of building generative
 models. It is composed of 13.6 hours of aligned MIDI and (synthesized) audio of
 human-performed, tempo-aligned expressive drumming. The dataset contains
 1,150 MIDI files and over 22,000 measures of drumming. But training on that
 many MIDI files would take too much time, therefore we used a subset of it. The
 dataset consists of a great variety of genres, reaching from Afrobeat to Pop. When
 training the models, we used MIDI files from numerous genres to achieve an
 evenly distributed set of possible outputs.
 ## Implementation
 Details are in the file: Final_report_group5.pdf
 ## Results and Discussions
 In terms of reaching our goal ”generating rhythmic drum music
 synchronized with the user's heartbeat to help people promote relaxation,
 reduce stress, and enhance overall well-being”, the resulting music beats are
 considered pretty successful.
 The model takes in the heartbeat rate (bpm) of the user, and generates music
 that has a low beat corresponding to their heartbeat. An example music generated
 from our project is in the link below:
 https://drive.google.com/file/d/1sr9ZPu3ZUkBBmNw2t9qGN8zAEC2FZXo
 e/view?usp=drive_link
 Besides generating physiologically synchronized music, we wanted an
 additional feature, that is, the user can choose what kind of music he or she
 wants to listen to by choosing the corresponding seed sequence. For example,
 rock music, blue music, pop music etc. However, the development of this feature
 wasn’t successful. We have tried different model architectures, but could not really
 generate versatile genres of beats.
 The challenge in generating versatile genres of beats in an AI-based music
 generation project can be attributed to several factors:
 ### 1. Data Diversity and Volume:
 Because LSTM training is extremely time consuming, and the Groove
 dataset is big, we only trained our model with a subset of the whole dataset. This
 tradeoff may decrease the richness of the training dataset. And if the dataset lacks
diversity in musical genres or is limited in volume, the model may not learn
 enough variety to generate different genres effectively.
 ### 2. Model Complexity and Architecture:
 The chosen LSTM model, while powerful for sequence prediction, might
 not capture the full complexity of musical composition, especially when it comes
 to capturing the essence of different genres. Exploring more complex or different
 types of neural networks could yield better genre differentiation.
 ### 3. Feature Representation:
 The way musical features (notes, velocity, timing) are represented and
 processed might not fully encapsulate the nuances that differentiate musical genres.
 For instance, subtle variations in rhythm or harmony that are crucial in genre
 distinction may not be adequately captured.
 ### 4. Heartbeat Synchronization:
 The process of synchronizing music with a heartbeat might oversimplify or
 alter the natural rhythm and flow of different music genres. This synchronization
 process could overshadow genre-specific rhythmic patterns.
 ### 5. Post-Processing and Denormalization:
 The steps involved in converting the model’s output back to MIDI format,
 especially the denormalization process, might introduce distortions or inaccuracies,
 affecting the musical quality and genre fidelity.
### 6. Subjectivity in Music:
 Musical genres are often subjectively interpreted and can vary widely. What
 constitutes a particular genre can be nuanced and influenced by small stylistic
 elements that a model might not capture.
 In conclusion, enhancing the diversity and volume of the dataset,
 experimenting with different model architectures, refining feature representation,
 and carefully managing the post-processing steps are key areas for improvement.
 Additionally, considering the inherent subjectivity in music, obtaining user
 feedback and iteratively refining the model based on this feedback could be
 beneficial
