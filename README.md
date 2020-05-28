# RedShirtTour-IoT-Edge-AI-Lab
(pour le français, cf. README-FR.md)
<p><em>Authors : Artem SHEIKO + Taras CHIEN
Directed by : Vincent Thavonekham + Igor Leontiev</em></p>

<p>Nowadays customers are increasingly looking for ways to obtain insights from all their data. Volume, speed and complexity of data now defeats traditional analytics tools, that’s why more and more customers now realize that traditional approaches in conjunction with Business Intelligence are not enough. While <strong>Business Intelligence</strong> addresses <strong>descriptive</strong> and <strong>diagnostic analysis</strong>, <strong>Data Science</strong> unlocks new opportunities through <strong>predictive</strong> and <strong>prescriptive analysis</strong>. This causes a high demand for solutions using Data Science and Machine Learning in a near-real time that can adapt to a rapidly changing environment, that can work « at the edge » (i.e. directly on the sensors’ side, thanks to “Edge Computing”).</p>
<p>Through various Labs, we are going to focus on an innovative part consisting in working with <strong>devices “at the edge” with Machine Learning processing, in near-real time. All disconnected from the Cloud, but with a Cloud management and supervision</strong> as soon as the connectivity is back.</p>

---
The Labs are based **on true example of Drones** transporting parcels, but with simplified assumptions to ease the understanding. The Drones has to take decisions real-time based on its sensors, and the telemetry sent to the Cloud will help predict maintenance time.

<img src="https://raw.githubusercontent.com/azugfr/RedShirtTour-IoT-Edge-AI-Lab/master/img/drone_%28C%29_openfogconsortium.org.jpg" alt="IoT Edge with emedded Machine Learning inside a Drone. Image source : openfogconsortium.org">
>image source: https://www.openfogconsortium.org


Here is the overall architecture of the Labs
<img src="https://raw.githubusercontent.com/azugfr/RedShirtTour-IoT-Edge-AI-Lab/master/img/Overview-architecture.png" alt="Overall architecture of the Labs">



Learn how to create a custom logic modules, use Azure Stream Analytics and Machine Learning module during IoT Edge Runtime, send information to IoT Hub and visualize the results through Azure Time Series Insights in the first series of Hands-On Labs. In this series, you will see how you can use a simple dataset and Logistic Regression model to predict a severity status of drone’s state. The architecture of the solution is presented below.

<img src="img/root_0.png">



Simplified hypothesis for the sake of this HOL (see advanced and realistic version in the [PDF](/Red%20Shirt%20Dev%20Tour%20Hands-On%20Lab%202nd%20Series.pdf)):

In this HOL, the Data Generation module (that mimics the Drone) sends real-time data to Azure Stream Analytics (ASA).

However, often times, data are corrupted or could be wrong. Here, let us assume that we are tracking if the battery with two cells sends back a realistic value.

<img src="img/root_1.jpg">

ASA aggregates the data so that less data are streamed across the wire to Azure, then the next module is able to detect the corruption in real-time:

- If one cell of the battery is KO, we are raising an error, then we call the module “Data treatment” to correct the error (by taking the default expected value, multiply by the number of expected cells)
- If everything is fine, there is no post-data treatment

In all cases, we perform a ML treatment (using “Python ML Model” written using Azure ML).

 

Finally, we send all this to Azure Cloud, hitting Azure IoT Hub, then display all this on TimeSeries Insights



Get started quickly with Hands-On Labs :

- [Lab 1 - Create an IoT Hub](/Lab%201%20-%20Create%20an%20IoT%20Hub)
- [Lab 2 - Register an IoT Edge Device](/Lab%202%20-%20Register%20an%20IoT%20Edge%20Device)
- [Lab 3 - Configure an IoT Edge runtime](/Lab%203%20-%20Configure%20an%20IoT%20Edge%20runtime)
- [Lab 4 - Create and deploy a module which will generate telemetry data](/Lab%204%20-%20Create%20and%20deploy%20a%20module%20which%20will%20generate%20telemetry%20data)
- [Lab 5 - Create and deploy a Stream Analytics module](/Lab%205%20-%20Create%20and%20deploy%20a%20Stream%20Analytics%20module)
- [Lab 6 - Create and deploy a process data module](/Lab%206%20-%20Create%20and%20deploy%20a%20process%20data%20module)
- [Lab 7 - Setup environment to manage Azure Machine Learning models](/Lab%207%20-%20Setup%20environment%20to%20manage%20Azure%20Machine%20Learning%20models)
- [Lab 8 - Create an Azure Machine Learning model for an IoT Edge module](/Lab%208%20-%20Create%20an%20Azure%20Machine%20Learning%20model%20for%20an%20IoT%20Edge%20module)
- [Lab 9 - Deploy an Azure Machine Learning model as an IoT Edge module](/Lab%209%20-%20Deploy%20an%20Azure%20Machine%20Learning%20model%20as%20an%20IoT%20Edge%20module)
- [Lab 10 - Visualize results](/Lab%2010%20-%20Visualize%20results)



For more examples discover more examples in [Next Steps](/Red%20Shirt%20Dev%20Tour%20Hands-On%20Lab%202nd%20Series.pdf).

# RedShirtTour-IoT-Edge-AI-Lab-VMTemplate

//Prepared VM with preinstaled software for the HOL

[![Deploy to Azure](https://azuredeploy.net/deploybutton.svg)](https://deploy.azure.com/?repository=https://github.com/Jiycefer/RedShirtTour-IoT-Edge-AI-Lab-VMTemplate?ptmpl=azuredeploy.parameters.json)

/!\ Attention. The exectuion of script can take long, due to the size of VM (127 GB), also you can arrive of Timeout Exeption

This is Work-In-Progress so new Labs will be added and others will be refined on an on-going basis. 



# Souvenir of the RedShirtTour

These 10 Labs has been made public and presented when Scott Guthrie came over in Paris during the Microsoft RedShirt Tour https://twitter.com/hashtag/redshirtdevtour?src=hash 
https://twitter.com/ShelPF/status/955804078122168321?s=20 
https://twitter.com/vThavo/status/955806487988850688?s=20

Here is a souvenir of us with Scott Gu !

<img src="/img/root_ScottGuthrie_ArtemSheiko_VincentThavonekham.jpg" alt="Vincent Thavonekham & Artem Sheiko next to THE MAN, Scott Guthrie" width=25% height=25%>

