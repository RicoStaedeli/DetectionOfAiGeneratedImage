<h1>Detection of AI generated Images</h1>

---

<table>
  <tr>
    <td>Autor</td>
    <td>Rico Stäedeli</td>
  </tr>
  <tr>
    <td>Modul</td>
    <td>Machnie Learning 2</td>
  </tr>
  <tr>
    <td>Institution</td>
    <td>ZHAW School of Management and Law</td>
  </tr>
    <tr>
    <td>Contact</td>
    <td>staedric@students.zhaw.ch</td>
  </tr>
</table>

---

<h2>Goal and motivation</h2>
Generative AI is getting better the longer it goes on. This has not only advantages. It is possible to create images of unprecedented situations. This also applies to people. For this reason, it is necessary to be able to find out whether a face is a synthetically generated image or whether the image is real.
The goal of this project is to create a machine learning model which can classify faces if they are genereated by an AI or if they are real. 
My personell motivation for this project is to find out the possibility of cutting edge technologies for generative AI. I am interessted to see if there is a way to classify the images correct. 

One of thoese two images is generated with a stable diffusion model. Personally I can't tell which one is the genereated. We will see later if the model is able to classify the image right.
<img width="755" alt="Screenshot 2023-06-10 160637" src="https://github.com/RicoStaedeli/ml2_project/assets/62505224/3c044185-67f8-4b55-a909-24e6521e60c3">

---

<h2>Structure of the Project</h2>

If you want to run the complete Project you can start with the Data Collection Notebook. Personally I would not recommend you to run that notebook because it can be very very time consuming. Pleas just contact me and I will give you the generated dataset from my run. 
After you created the datasaet you can start with the model training. For that you can start with one of the training notebooks. The same here the training can be very time conusming and because of that I stored all the trained models and you can just use them in the further steps. 
The last notebook is the validation notebook.


<h2>How to start</h2>

1. Creaete a Google account
2. Download this repository as .zip 
3. extract the files from the downloaded folder
4. create a folder in your root folder in Google drive with the name ML2
5. Upload the folder ExamProject to Google Drive in the newly created folder ML2
6. Lets start with the exploration of my notebooks


---

<h2>Collecting Data</h2>
In this Notebook I collected the data. For that I used an existing dataset from kaggle. The dataset contains roghly 7000 scrappd images of real human faces. <br>
In a second step I generated all the synthetic images of human faces. To do that I used the GPT model from openai to generate fifty different description of human faces. After that I generated approximately 700 different images. 

<br>

Learnings in this sections where:
* Images will not be better generated if the description is more detailed. I learned that the stable diffusion models are confused if the description is to detailed. I got the best results with the simple prompt "A face of a man/women"
* The second learning where negative prompts. In the beginning I thought to add negative prompts of things I don't want to see like cartoon or drawed pictures. The problem was that all the different models I used where not really able to use that information appropriate. So the output of a prompt where i wrote "I don't want to see drawings" were more than the half of the generated images drawings.

<br>

<h2>Model Training</h2>
In this Notebooks i create a model to classify the images. Because of the small amount of data I used transfer learning. I used two different model as base-model to evaluate which one is better. First I used the pretrained model MobileNetV2 from Keras and as the second model I used the model Xception also from Keras. Detailed description are in the codeblocks. 

<br>

<h2>Model Finetuning</h2>
In this Notebook I finetuned the model MobileNetV2. The result was quite unsatisfying and not unusable. 

<br>

<h2>Validation and interpretation</h2>
In this Notebook the different models where evaluated. For that I used a test-dataset and checked the performance during the training. The interpretation can be found in the section. I used tensorboard to log the data during the training. Ofcourse i saved this in the project folder that you can explore this. In the image bellow you can see the accuracy of the two evaluated models.
<img width="1234" alt="image" src="https://github.com/RicoStaedeli/ml2_exam/assets/62505224/684e1564-0c5c-4f3b-a15e-b810c31b2e4c">

<br>

---
<h2>Used models</h2>


*   gpt-3.5-turbo --> Generate face descriptions
*   SG161222/Realistic_Vision_V1.4 --> generate sythetic images: https://huggingface.co/SG161222/Realistic_Vision_V1.4
*   MobileNetV2 --> Basemodel for image classification: https://keras.io/api/applications/mobilenet/#mobilenetv2-function
*   Xcdeption --> Basemodel for image classification: https://keras.io/api/applications/xception/

<br>

<h2>Used Datasets</h2>
*   First 700 images of the Kaggle Human Faces: https://www.kaggle.com/datasets/ashwingupta3012/human-faces

<br> <br>

---
