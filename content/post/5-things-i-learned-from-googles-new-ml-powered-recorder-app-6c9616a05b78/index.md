---
image: 5-things-i-learned-from-googles-new-ml-powered-recorder-app-6c9616a05b78.jpg
title: "5 Things I Learned from Google’s New ML-Powered Recorder App"
description: "And what future ML-enabled apps should look like"
slug: 5-things-i-learned-from-googles-new-ml-powered-recorder-app-6c9616a05b78
date: Thu Jan 30 11:13:51 CST 2020
categories: Machine Learning
tags: 
- "Machine Learning"
- "Artificial Intelligence"


---



There are tons of audio recording apps in the app store, but you know things will be a bit different if Google developed a brand new one. Google recently released a new ‘[Recorder](https://play.google.com/store/apps/details?id=com.google.android.apps.recorder)’ app that is powered by its state-of-the-art Machine Learning algorithm that can transcribe what it hears with impressive precision in real-time. This is not the first time Google tried to bless its product with some AI ‘superpower’. Some of their prior attempts failed (I’m talking to you [Google Clips](https://www.engadget.com/2019/10/16/google-discontinues-clips-camera/)!) and some had quite formidable success, for example, Google’s Pixel phone camera app. With the camera hardware spec a little below industry mainstream, Google’s Pixel flagship phone managed to pull off as [one of the best smartphone cameras on the market](https://www.androidauthority.com/best-camera-phones-670620/) thanks to its Machine Learning algorithms for image post-processing. The ‘Recorder’ app is yet another attempt by Google to spice up competition using AI, this time on audio.

After digging deeper into what the app can do differently and how AI played a core role in it, I found some very interesting insights on how Google handles app, AI and user experience that could shed some light on future app development in the AI-era.

## What is Google Recorder?

You can refer to the following short YouTube video on what Recorder does. In short, you can use it to do real-time transcription, search recorded audio by keywords, automatically generate tags or segment the audio into different categories like music, speech, etc.

{{< youtube RVMqB4W_EH4 >}}

I’ve been using it for more than a week and found it to be useful, slick and pleasant to use. Recording audio is not a complicated task, but the AI part makes it even easier. I can see this little app makes a big difference for students and people attending meetings regularly.

## #1 Adoption of Edge-First Model Design

{{< figure caption="Image from[ WishDesk](https://www.google.com/url?sa=i&source=images&cd=&cad=rja&uact=8&ved=2ahUKEwi8qsaS4c7mAhVFXawKHXf6BSsQjB16BAgBEAM&url=https%3A%2F%2Fwishdesk.com%2Fblog%2Fwhat-mobile-first-design&psig=AOvVaw1Z2T4KkHv8kJl4UFvKoWF-&ust=1577293156997339)" src="https://cdn-images-1.medium.com/max/2000/0*ln5CfxKmWRUMQTsG.jpg" >}}

We all heard of the term ‘Mobile-First Design’. When companies develop their applications, they will design and optimize their app based on mobile experience first, then to other platforms like desktop or web. I think the same idea can also be applied to AI-powered application design, hence ‘Edge-First Design’.

Usually, Machine Learning based applications run on the cloud, this is due to the heavy computation requirements for most state-of-the-art ML models. For enterprise applications, this approach is fine since the hardware is hardly a real issue. But if a company wants to build impactful AI-based apps for the consumers, then a cloud-based system often won’t cut it. Running AI-based apps from the cloud is not only slow but also has serious privacy concerns. Also to the normal consumer, they are used to the snappiness modern mobile apps offers. They can care less whether your app is based on some SOTA models or not, if the experience cannot match the high standard they get used to, boosted by many years of modern smartphone hardware/software development. So putting the AI on the ‘Edge’, e.g. user’s phone, tablet, smart home devices will be a better way to success.

{{< figure caption="Image from Lann" src="https://cdn-images-1.medium.com/max/2400/0*qaLMK3_40cM494G1.png" >}}

Google Recorder app did a great job on this. It uses a new model called ‘[**RNN transducer(RNN-T)](https://arxiv.org/pdf/1211.3711.pdf)**’ that is compact enough to reside on the phone while powerful enough to do real-time transcription. Instead of the traditional ‘pipeline’ approach, the RNN-T model uses a [single neural network, end-to-end approach](https://www.youtube.com/watch?v=ImUoubi_t7s) which is growingly more popular to solve complicated problems. Until recently, we’ve seen a lot of research progress being made on increasing the prediction performance by using bigger and bigger models, yet the opposite direction is equally important: Using as compact a model as possible to achieve similar performance so the model can be put on the edge. I expect more research to be done in this area when machine learning matures in the coming years.

## #2 Use Different Technology Stack for Performance

Another interesting development is the introduction of [Swift for TensorFlow](https://www.tensorflow.org/swift). Created by the creator of Swift programming language, [Chris Lattner](https://en.wikipedia.org/wiki/Chris_Lattner). It uses open-source Swift language with TensorFlow and promises both fast development time like Python and high-level performance like C++. [Fast.ai](http://fast.ai) has a great [introductory course](https://blog.tensorflow.org/2019/06/fastais-deep-learning-from-foundations_28.html) on it. With ML moving more and more from research labs to commercial applications, the performance of ML models will play a much bigger role and Swift for TensorFlow has great potential on that. According to the founder of [fast.ai](http://fast.ai), Jeremy Howard:
[**What's New in Machine Learning - WWDC 2019 - Videos - Apple Developer**
*Core ML 3 has been greatly expanded to enable even more amazing, on-device machine learning capabilities in your app…*developer.apple.com](https://developer.apple.com/videos/play/wwdc2019/209/)
> *“Swift can match the performance of hand-tuned assembly code from numerical library vendors. Swift for TensorFlow is the first serious effort I’ve seen to incorporate differentiable programming deep into the heart of a widely used language that is designed from the ground up for performance”*

## #3 Privacy Matters

{{< figure caption="Photo by [Matthew Henry](https://unsplash.com/@matthewhenry?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)" src="https://cdn-images-1.medium.com/max/11520/0*rw-NMk45j3aa8EF9" >}}

One of the biggest concerns for AI applications is privacy. For AI to really show value, it has to know a lot about the user, often times their personal life details people don’t feel comfortable sharing. Take audio recording as an example, you might want to record your family meeting discussing your next Christmas plan but don’t want it to be transferred onto the cloud and get 10 Christmas travel agents calling you to sell their products. This gives ‘offline’ ML apps an advantage. Since the model is deployed locally on the edge and no data need to be transferred to the cloud, the user can feel assured that their privacy can be protected. The Recorder app runs all the models on-device and makes it a bit less reluctance for people to adopt it.

## #4 User Experience Design is Still the Key

The Recorder app has a very slick and elegant UI. It’s a simple app with minimal clutters. You can easily start/pause your recording, toggle between ‘Audio’ or ‘Transcript’ mode to check your recorded content and getting suggestions on tags from the content recorded. All works without friction.

During recording, the app will automatically categorize sections of audio as ‘Speech’, ‘Music’, ‘Whistling’ … etc. and color code them accordingly.

{{< figure caption="" src="https://cdn-images-1.medium.com/max/2560/0*Dxe5mkbWE1L-trgT.gif" >}}

When playback your recorded audio, you can see each word get highlighted when being spoken in the transcript mode and you can search through the transcripts use the keyword you want. Very intuitive.

{{< figure caption="" src="https://cdn-images-1.medium.com/max/2560/0*nEF5vXInKw71Nf2y.gif" >}}

What I’m trying to say is: User experience design will make or break a great AI model. Only when working seamlessly with other parts of the app can an AI feature delivers its value to the end-user. A model that can address the user’s paint-point with high performance is only a start, not the end. AI should serve silently behind the scenes rather take the center stage.

## #5 Responsiveness Come with a Price

In the mobile world, companies strive to offer more responsiveness. Consumers nowadays are very impatient and the last thing they want is to wait. Snappy experience means the user can focus on the content they want or the tasks at hand. But responsiveness on mobile devices is not easy to come by. Computing power, screen size, system resources are all very limited compare to desktop or cloud. To achieve the best responsiveness, more thoughts and research need to be put into the design and development of the app. This includes better use of CPU/GPU, memory optimization, choose fast programming languages for the implementation and reduce dependence on back-end servers. The Machine Learning industry has made great progress on research for the past few years, yet to have more impact on people’s day-to-day life, more investment and work has to be done on the engineering side. And a switch from research to engineering is a sign of matureness for new technology.

## The Right Way of Developing AI Applications?

{{< figure caption="Image from Overwatch" src="https://cdn-images-1.medium.com/max/3840/0*jIEExvGIlAay-wgq" >}}

People have this fantasy of scary AI taking over humanity for many years. Movies, novels, TV Shows all painted a very dramatic future of AI for mankind. To counter this public (biased?) impression on AI, special cautions need to be taken. It’s beneficial to adopt an ‘AI exist as a tool to help human’ mentality instead of an ‘AI vs Mankind’ one. AI can do a lot of things, but rather than develop AI apps that can ‘replace’ humans, it’s better to have AI that exists to help humans perform their tasks easier and faster. Like the Recorder app to help taking notes, image recognition systems to help the doctor diagnose better, augment reality app to help people better navigate the neighborhood, etc.
> # *A quiet, friendly, yet powerful AI diligently working behind the scenes to help people do whatever they do better is so much more comfortable and approachable for people, compare to a robotic killing machine in a SciFi movie.*
