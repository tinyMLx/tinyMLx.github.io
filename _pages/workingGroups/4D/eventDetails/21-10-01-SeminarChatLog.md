---
title: Chat Log from the Seminar - Software Tools for TinyML with Prof. Marcelo Rovai
layout: splash
permalink: /4D/AcademicNetwork/21-10-01-SeminarChatLog
date: 
header:
  overlay_color: "#00A"
  overlay_filter: "0.5"
  overlay_image: /assets/images/banner.jpg
excerpt: ""
---

Questions from the chat are below. Click the arrow to view the answer:
+ <details>
    <summary>How do I join the ICTP workshop?</summary>
    
    Link for the ICTP workshop: http://indico.ictp.it/event/9622/ Apply by clicking Apply here on the left</details>
+ <details>
    <summary>Xola: Does the preprocessing stage not happen on some computer after acquiring the data. If so, then does the ML model on the tinyML device run on preprocessed data or raw data? Also I wonder how much energy is used at the preprocessing stage on the tiny device and if there is any way to avoid it.</summary>
    
    Brian: @Xola if you run preprocessing before training then the tinyML device also has to run preprocessign before inference as the nerual network model only would know data that has been preprocessed. Also preproprocessing is very dependnet on the application / data source you are working with -- the state of the art for images is generally very little pre-processing whereas audio actually often requires more.</details>
+ <details>
    <summary>Gitesh: Question on the current trend of doing ML on Tiny : - Instead of training on cloud/ PC and then inferencing on Tiny Edge device.... Is it possible to run the state of the art data analytics algorithm on Tiny devices? Also can we not just deploy the data analytics algorithms which don't need training? Just curious about what happened to those algorithms which are not data-driven algorithms.</summary>

    Brian: @Gitesh it is possible to run training on some small devices but often training requires a (relatively large) dataset that is very hard to fit on the device for training -- which is why usually we train in the cloud and then load just the inference model on the device (which can then just react to one input at a time. And yes of course! We can definitely deploy more "standard" algorithms! And sometimes those will be a very good option!</details>
+ <details>
    <summary>James: when we have image as input how could the image be loaded by the tiny devices for inference? And what if the image is heavy in term of memory?</summary>

    Brian: @James often you need to attach a computer to the tiny device (e.g., we attach a camera to the Arduino in our Tiny Machine Learning Kit) and then we can pass the input images to our neural network in software. And due to memory limits sometimes then we have to downsample the image or stream it in (or use some external memory from which to stream it). In fact in the edX course example we do some serious cropping of the camera to get around a lot of those memory issues!</details>
+ <details>
    <summary>Daniel: Can a DSP can be used like "edge device"?</summary>

    Brian: @Daniel you could definitely use a DSP as an edge device! In fact I might argue that most if not all DSPs are used as edge devices today!</details>
+ <details>
    <summary>Joseph:	Hello, Is it possible to pull out the model from the Arduino board. In case you find a board running with a model that someone else has loaded? Suppose that you give me a board with a preloaded model and I want to get that model out and analyze it.</summary>

    Marvin: @Joseph you can overwrite it. Like after you get your library from edge impulse and you are using arduino IDE, you can simply upload and it will overwrite whatever was already on the board. Also that is an interesting idea -- that would mean extracting like the whole code and the libraries, since the model on arduino is a form of library from edge impulse.  
    
    Daniel: @Joseph, The code is compiled to a hex format and then uploaded to the Arduino. You will not be able to pull out the C code from it (or the model details).  
    
    Brian: @Joseph you could definitely extract the binary file from the arduino but/and as Marvin and Daniel are saying it would be very very hard to back out the higher level python code from that binary. Also @Jospeh @Marvin looks like there is some interesting discussion in the lower comments on this thread about extracting the binary code https://arduino.stackexchange.com/questions/68711/how-do-i-extract-code-from-an-arduino</details>
+ <details>
    <summary>Xola: Is it possible to integrate another type of sensor with tinyML? Like a humidity sensor for instance.</summary>

    Daniel: @Xola yes, you can!

    Brian: @Xola you can attach pretty much any sensor to a microcontroller! Most sensors you can buy on the market speak over standard communication protocols!</details>
+ <details>
    <summary>Marvin:	Has anyone else noticed the estimates for RAM and ROM usage from edge impulse are not the same as when you actually deploy the model on a physical board?</summary>

    José: @Marvin The memory usage numbers exclude boot code, peripheral drivers, printf, and memory tracking functions. This is done by first compiling a basic benchmarking application and subtracting the RAM and ROM used.

    Marvin: https://forum.edgeimpulse.com/t/difference-in-estimated-on-device-perfomance-and-actual/2794/3</details>
+ <details>
    <summary>Mbuthuma: Can you connect the electricity consumption device on Edge impulse, to check the consumption of different appliances in the house?</summary>

    Brian: @Mbuthuma I think you could monitor electrical usage without even using machine learning since all you want to know is how much something is using (e.g., you could use a device like this https://www.amazon.com/P3-P4400-Electricity-Usage-Monitor/dp/B00009MDBU) -- if you wanted to monitor for anomolies in their consumption -- then it might make sense to use machine learning to do anomoly detection from normal patterns -- then you'd need to find a way to get the output of one of those kinds of devices and get it into a microcontroller of some sort! (BTW that is just a link to the first device on amazon that does that -- I am not suggesting that particular device -- just using it as an example)</details>
+ <details>
    <summary>Emmanuel: Can we  use  Edge Impulse for solving NLP problems?</summary>

    Brian: @Emmanuel in theory yes for sure -- in practice for tinyML a full NLP model will likely be too large -- but/and if you wanted to e.g., identify a few select words -- we actually do that in the edX course and should talk about it more in the workshop!</details>
+ <details>
    <summary>Gitesh: Does this support RNNs?</summary>

    Brian: @Gitesh Since EI runs TFMirco under the hood, if you go into the "expertmode" pages of EI, you can use anything that TFMirco supports -- but do be careful becuase TFMicro does not support all of the ops that TF (regular) does -- only a subset (which you can find here: https://github.com/tensorflow/tflite-micro/blob/main/tensorflow/lite/micro/all_ops_resolver.cc). That said I know that Pete and the TFMicro team are working to expand support every day!</details>

Additional questions that were answered during Q&A (see the video for the answers):
+ Bruno Bustos: Which board could you recommend us for DSP in neuroscience (like EEG data)? Thanks in advance.
+ Joseph:	Suppose that if I use a mobile phone accellometer or microphone or camera to collect data , train and get a final model. can I say that this model will work well on a board like Arduino 33 blue sens?
+ James: Can we use pre-trained algorithms in Edge inpulse?
+ Gitesh: Can we put our own models using Edge Impulse? And EI would optimize them?
+ Aditya: Is there an option available in edgeimpulse studio to extract custom features from data instead of the in-built ones? 