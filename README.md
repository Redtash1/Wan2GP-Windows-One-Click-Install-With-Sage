<div align="center">


# DON'T CLONE THIS REPO, IT WON'T WORK AS IT ALL DEPENDS ON THE PYTHON_EMBEDED TO WORK! 


## I made Wan2GP Portable/Standalone for Windows that uses Nvidia GPU's only. 1 click install with Sage Attention and Triton. It uses python_embeded 3.10.9, Torch 2.7.1 with Cuda 12.8. During installation it will update Wan2GP, install Torch etc..., Sage Attention, Triton and Create a Launch Wan2GP Desktop Shortcut. All Wan2GP updates comes directly from the original DeepBeepMeep/Wan2GP Repository. 

## Click here to jump to Install 👉 [Installation](#-Installation) 👈

# [![Downloads](https://img.shields.io/github/downloads/Redtash1/Wan2GP-Windows-One-Click-Install-With-Sage/total.svg)](https://github.com/Redtash1/Wan2GP-Windows-One-Click-Install-With-Sage/releases)

</div>

# WanGP

-----
<p align="center">
<b>WanGP by DeepBeepMeep : The best Open Source Video Generative Models Accessible to the GPU Poor</b>
</p>

WanGP supports the Wan (and derived models), Hunyuan Video and LTV Video models with:
- Low VRAM requirements (as low as 6 GB of VRAM is sufficient for certain models)
- Very Fast on the latest GPUs
- Easy to use Full Web based interface
- Auto download of the required model adapted to your specific architecture
- Tools integrated to facilitate Video Generation : Mask Editor, Prompt Enhancer, Temporal and Spatial Generation
- Loras Support to customize each model
- Queuing system : make your shopping list of videos to generate and come back later 

**Discord Server to get Help from Other Users and show your Best Videos:** https://discord.gg/g7efUW9jGV

**Follow DeepBeepMeep on Twitter/X to get the Latest News**: https://x.com/deepbeepmeep

<img width="1919" height="1054" alt="Screenshot 2025-07-31 112759" src="https://github.com/user-attachments/assets/4847b3e2-ee17-4dab-ac4f-aeb46e94a781" />

<img width="1919" height="1079" alt="Screenshot 2025-07-31 112834" src="https://github.com/user-attachments/assets/20238cf2-1c4b-4219-96b5-0a437253343b" />


## 🔥 Latest Updates

### July 30 2025: WanGP v7.5:  Just another release ... Wan 2.2 part 2
Here is now Wan 2.2 image2video a very good model if you want to set Start and End frames. Two Wan 2.2 models delivered, only one to go ...

Please note that although it is an image2video model it is structurally very close to Wan 2.2 text2video (same layers with only a different initial projection). Given that Wan 2.1 image2video loras don't work too well (half of their tensors are not supported), I have decided that this model will look for its loras in the text2video loras folder instead of the image2video folder.

I have also optimized RAM management with Wan 2.2 so that loras and modules will be loaded only once in RAM and Reserved RAM, this saves up to 5 GB of RAM which can make a difference...

And this time I really removed Vace Cocktail Light which gave a blurry vision.

### July 29 2025: WanGP v7.4:  Just another release ... Wan 2.2 Preview
Wan 2.2 is here.  The good news is that WanGP wont require a single byte of extra VRAM to run it and it will be as fast as Wan 2.1. The bad news is that you will need much more RAM if you want to leverage entirely this new model since it has twice has many parameters.

So here is a preview version of Wan 2.2 that is without the 5B model and Wan 2.2 image to video for the moment.

However as I felt bad to deliver only half of the wares, I gave you instead .....** Wan 2.2 Vace Experimental Cocktail** !

Very good surprise indeed, the loras and Vace partially work with Wan 2.2. We will need to wait for the official Vace 2.2 release since some Vace features are broken like identity preservation

Bonus zone: Flux multi images conditions has been added, or maybe not if I broke everything as I have been distracted by Wan...

7.4 update: I forgot to update the version number. I also removed Vace Cocktail light which didnt work well.

### July 27 2025: WanGP v7.3 : Interlude
While waiting for Wan 2.2, you will appreciate the model selection hierarchy which is very useful to collect even more models. You will also appreciate that WanGP remembers which model you used last in each model family.

### July 26 2025: WanGP v7.2 : Ode to Vace
I am really convinced that Vace can do everything the other models can do and in a better way especially as Vace can be combined with Multitalk.

Here are some new Vace improvements:
- I have provided a default finetune named *Vace Cocktail*  which is a model created on the fly using the Wan text 2 video model and the Loras used to build FusioniX. The weight of the *Detail Enhancer* Lora has been reduced to improve identity preservation. Copy the model definition in *defaults/vace_14B_cocktail.json* in the *finetunes/* folder to change the Cocktail composition. Cocktail contains already some Loras acccelerators so no need to add on top a Lora Accvid, Causvid or Fusionix, ... . The whole point of Cocktail is to be able  to build you own FusioniX (which originally is a combination of 4 loras) but without the inconvenient of FusioniX.
- Talking about identity preservation, it tends to go away when one generates a single Frame instead of a Video which is shame for our Vace photoshop. But there is a solution : I have added an Advanced Quality option, that tells WanGP to generate a little more than a frame (it will still keep only the first frame). It will be a little slower but you will be amazed how Vace Cocktail combined with this option will preserve identities (bye bye *Phantom*). 
- As in practise I have observed one switches frequently between *Vace text2video* and *Vace text2image* I have put them in the same place they are now just one tab away, no need to reload the model. Likewise *Wan text2video* and *Wan tex2image* have been merged.
- Color fixing when using Sliding Windows. A new postprocessing *Color Correction* applied automatically by default (you can disable it in the *Advanced tab Sliding Window*) will try to match the colors of the new window with that of the previous window. It doesnt fix all the unwanted artifacts of the new window but at least this makes the transition smoother. Thanks to the multitalk team for the original code.

Also you will enjoy our new real time statistics (CPU / GPU usage, RAM / VRAM used, ... ). Many thanks to **Redtash1** for providing the framework for this new feature ! You need to go in the Config tab to enable real time stats.

### July 21 2025: WanGP v7.12
- Flux Family Reunion : *Flux Dev* and *Flux Schnell* have been invited aboard WanGP. To celebrate that, Loras support for the Flux *diffusers* format has also been added.

- LTX Video upgraded to version 0.9.8: you can now generate 1800 frames (1 min of video !) in one go without a sliding window. With the distilled model it will take only 5 minutes with a RTX 4090 (you will need 22 GB of VRAM though). I have added options to select higher humber frames if you want to experiment

- LTX Video ControlNet : it is a Control Net that allows you for instance to transfer a Human motion or Depth from a control video. It is not as powerful as Vace but can produce interesting things especially as now you can generate quickly a 1 min video. Under the scene IC-Loras (see below) for Pose, Depth and Canny are automatically loaded for you, no need to add them. 

- LTX IC-Lora support: these are special Loras that consumes a conditional image or video
Beside the pose, depth and canny IC-Loras transparently loaded there is the *detailer* (https://huggingface.co/Lightricks/LTX-Video-ICLoRA-detailer-13b-0.9.8) which is basically an upsampler. Add the *detailer* as a Lora and use LTX Raw Format as control net choice to use it.

- Matanyone is now also for the GPU Poor as its VRAM requirements have been divided by 2! (7.12 shadow update)

- Easier way to select video resolution 


### July 15 2025: WanGP v7.0 is an AI Powered Photoshop
This release turns the Wan models into Image Generators. This goes way more than allowing to generate a video made of single frame :
- Multiple Images generated at the same time so that you can choose the one you like best.It is Highly VRAM optimized so that you can generate for instance 4 720p Images at the same time with less than 10 GB
- With the *image2image* the original text2video WanGP becomes an image upsampler / restorer
- *Vace image2image* comes out of the box with image outpainting, person / object replacement, ...
- You can use in one click a newly Image generated as Start Image or Reference Image for a Video generation

And to complete the full suite of AI Image Generators, Ladies and Gentlemen please welcome for the first time in WanGP : **Flux Kontext**.\
As a reminder Flux Kontext is an image editor : give it an image and a prompt and it will do the change for you.\
This highly optimized version of Flux Kontext will make you feel that you have been cheated all this time as WanGP Flux Kontext requires only 8 GB of VRAM to generate 4 images at the same time with no need for quantization.

WanGP v7 comes with *Image2image* vanilla and *Vace FusinoniX*. However you can build your own finetune where you will combine a text2video or Vace model with any combination of Loras.

Also in the news:
- You can now enter the *Bbox* for each speaker in *Multitalk* to precisely locate who is speaking. And to save some headaches the *Image Mask generator* will give you the *Bbox* coordinates of an area you have selected.
- *Film Grain* post processing to add a vintage look at your video
- *First Last Frame to Video* model should work much better now as I have discovered rencently its implementation was not complete
- More power for the finetuners, you can now embed Loras directly in the finetune definition. You can also override the default models (titles, visibility, ...) with your own finetunes. Check the doc that has been updated.

### July 10 2025: WanGP v6.7, is NAG a game changer, you tell me?
Maybe you knew that already but most *Loras accelerators* we use today (Causvid, FusioniX) don't use *Guidance* at all (that it is *CFG* is set to 1). This helps to get much faster generations but the downside is that *Negative Prompts* are completely ignored (including the default ones set by the models). **NAG** (https://github.com/ChenDarYen/Normalized-Attention-Guidance) aims to solve that by injecting the *Negative Prompt* during the *attention* processing phase.

So WanGP 6.7 gives you NAG, but not any NAG, a *Low VRAM* implementation, the default one ends being VRAM greedy. You will find NAG in the *General* advanced tab for most Wan models. 

Use NAG especially when Guidance is set to 1. To turn it on set the **NAG scale** to something around 10. There are other NAG parameters **NAG tau** and **NAG alpha** which I recommend to change only if you don't get good results by just playing with the NAG scale. Don't hesitate to share on this discord server the best combinations for these 3 parameters.

The authors of NAG claim that NAG can also be used when using a Guidance (CFG > 1) and to improve the prompt adherence.

### July 8 2025: WanGP v6.6, WanGP offers you **Vace Multitalk Dual Voices Fusionix Infinite** :
**Vace** our beloved super Control Net has been combined with **Multitalk** the new king in town that can animate up to two people speaking (**Dual Voices**). It is accelerated by the **Fusionix** model and thanks to *Sliding Windows* support and *Adaptive Projected Guidance* (much slower but should reduce the reddish effect with long videos) your two people will be able to talk for very a long time (which is an **Infinite** amount of time in the field of video generation).

Of course you will get as well *Multitalk* vanilla and also *Multitalk 720p* as a bonus.

And since I am mister nice guy I have enclosed as an exclusivity an *Audio Separator* that will save you time to isolate each voice when using Multitalk with two people.

As I feel like resting a bit I haven't produced yet a nice sample Video to illustrate all these new capabilities. But here is the thing, I ams sure you will publish in the *Share Your Best Video* channel your *Master Pieces*. The best ones will be added to the *Announcements Channel* and will bring eternal fame to its authors.

But wait, there is more:
- Sliding Windows support has been added anywhere with Wan models, so imagine with text2video recently upgraded in 6.5 into a video2video, you can now upsample very long videos regardless of your VRAM. The good old image2video model can now reuse the last image to produce new videos (as requested by many of you)
- I have added also the capability to transfer the audio of the original control video (Misc. advanced tab) and an option to preserve the fps into the generated video, so from now on you will be to upsample / restore your old families video and keep the audio at their original pace. Be aware that the duration will be limited to 1000 frames as I still need to add streaming support for unlimited video sizes.

Also, of interest too:
- Extract video info from Videos that have not been generated by WanGP, even better you can also apply post processing (Upsampling / MMAudio) on non WanGP videos
- Force the generated video fps to your liking, works wery well with Vace when using a Control Video
- Ability to chain URLs of Finetune models (for instance put the URLs of a model in your main finetune and reference this finetune in other finetune models to save time)

### July 2 2025: WanGP v6.5.1, WanGP takes care of you: lots of quality of life features:
- View directly inside WanGP the properties (seed, resolutions, length, most settings...) of the past generations
- In one click use the newly generated video as a Control Video or Source Video to be continued 
- Manage multiple settings for the same model and switch between them using a dropdown box 
- WanGP will keep the last generated videos in the Gallery and will remember the last model you used if you restart the app but kept the Web page open
- Custom resolutions : add a file in the WanGP folder with the list of resolutions you want to see in WanGP (look at the instruction readme in this folder)

Taking care of your life is not enough, you want new stuff to play with ?
- MMAudio directly inside WanGP : add an audio soundtrack that matches the content of your video. By the way it is a low VRAM MMAudio and 6 GB of VRAM should be sufficient. You will need to go in the *Extensions* tab of the WanGP *Configuration* to enable MMAudio
- Forgot to upsample your video during the generation ? want to try another MMAudio variation ? Fear not you can also apply upsampling or add an MMAudio track once the video generation is done. Even better you can ask WangGP for multiple variations of MMAudio to pick the one you like best
- MagCache support: a new step skipping approach, supposed to be better than TeaCache. Makes a difference if you usually generate with a high number of steps
- SageAttention2++ support : not just the compatibility but also a slightly reduced VRAM usage
- Video2Video in Wan Text2Video : this is the paradox, a text2video can become a video2video if you start the denoising process later on an existing video
- FusioniX upsampler: this is an illustration of Video2Video in Text2Video. Use the FusioniX text2video model with an output resolution of 1080p and a denoising strength of 0.25 and you will get one of the best upsamplers (in only 2/3 steps, you will need lots of VRAM though). Increase the denoising strength and you will get one of the best Video Restorer
- Choice of Wan Samplers / Schedulers
- More Lora formats support

**If you had upgraded to v6.5 please upgrade again to 6.5.1 as this will fix a bug that ignored Loras beyond the first one**


### June 23 2025: WanGP v6.3, Vace Unleashed. Thought we couldn't squeeze Vace even more ?
- Multithreaded preprocessing when possible for faster generations
- Multithreaded frames Lanczos Upsampling as a bonus
- A new Vace preprocessor : *Flow* to extract fluid motion
- Multi Vace Controlnets: you can now transfer several properties at the same time. This opens new possibilities to explore, for instance if you transfer *Human Movement* and *Shapes* at the same time for some reasons the lighting of your character will take into account much more the environment of your character.
- Injected Frames Outpainting, in case you missed it in WanGP 6.21

Don't know how to use all of the Vace features ? Check the Vace Guide embedded in WanGP as it has also been updated.


### June 19 2025: WanGP v6.2, Vace even more Powercharged
👋 Have I told you that I am a big fan of Vace ? Here are more goodies to unleash its power: 
- If you ever wanted to watch Star Wars in 4:3, just use the new *Outpainting* feature and it will add the missing bits of image at the top and the bottom of the screen. The best thing is *Outpainting* can be combined with all the other Vace modifications, for instance you can change the main character of your favorite movie at the same time  
- More processing can combined at the same time  (for instance the depth process can be applied outside the mask)
- Upgraded the depth extractor to Depth Anything 2 which is much more detailed

As a bonus, I have added two finetunes based on the Safe-Forcing technology (which requires only 4 steps to generate a video): Wan 2.1 text2video Self-Forcing and Vace Self-Forcing. I know there is Lora around but the quality of the Lora is worse (at least with Vace) compared to the full model. Don't hesitate to share your opinion about this on the discord server. 
### June 17 2025: WanGP v6.1, Vace Powercharged
👋 Lots of improvements for Vace the Mother of all Models:
- masks can now be combined with on the fly processing of a control video, for instance you can extract the motion of a specific person defined by a mask
- on the fly modification of masks : reversed masks (with the same mask you can modify the background instead of the people covered by the masks), enlarged masks (you can cover more area if for instance the person you are trying to inject is larger than the one in the mask), ...
- view these modified masks directly inside WanGP during the video generation to check they are really as expected
- multiple frames injections: multiples frames can be injected at any location of the video
- expand past videos in on click: just select one generated video to expand it

Of course all these new stuff work on all Vace finetunes (including Vace Fusionix).

Thanks also to Reevoy24 for adding a Notfication sound at the end of a generation and for fixing the background color of the current generation summary.

### June 12 2025: WanGP v6.0
👋 *Finetune models*: If you find the 20 models supported by WanGP not sufficient ? Too impatient to wait for the next release to get the support for a newly released model ? Your prayers have been answered: if a new model is compatible with a model architecture supported by WanGP, you can add by yourself the support for this model in WanGP by just creating a finetune model definition. You can then store this model in the cloud (for instance in Huggingface) and the very light finetune definition file can be easily shared with other users. WanGP will automatically download the finetuned model for them.

To celebrate the new finetunes support, here are a few finetune gifts (directly accessible from the model selection menu):
- *Fast Hunyuan Video* : generate model t2v in only 6 steps
- *Hunyuan Vido AccVideo* : generate model t2v in only 5 steps
- *Wan FusioniX*: it is a combo of AccVideo / CausVid ans other models and can generate high quality Wan videos in only 8 steps

One more thing...

The new finetune system can be used to combine complementaty models : what happens when you combine  Fusionix Text2Video and Vace Control Net ?

You get **Vace FusioniX**: the Ultimate Vace Model, Fast (10 steps, no need for guidance) and with a much better quality Video than the original slower model (despite being the best Control Net out there). Here goes one more finetune...

Check the *Finetune Guide* to create finetune models definitions and share them on the WanGP discord server.

### June 11 2025: WanGP v5.5
👋 *Hunyuan Video Custom Audio*: it is similar to Hunyuan Video Avatar except there isn't any lower limit on the number of frames and you can use your reference images in a different context than the image itself\
*Hunyuan Video Custom Edit*: Hunyuan Video Controlnet, use it to do inpainting and replace a person in a video while still keeping his poses. Similar to Vace but less restricted than the Wan models in terms of content...


### June 6 2025: WanGP v5.41
👋 Bonus release: Support for **AccVideo** Lora to speed up x2 Video generations in Wan models. Check the Loras documentation to get the usage instructions of AccVideo.\
You will need to do a *pip install -r requirements.txt*

### June 6 2025: WanGP v5.4
👋 World Exclusive : **Hunyuan Video Avatar** Support ! You won't need 80 GB of VRAM nor 32 GB oF VRAM, just 10 GB of VRAM will be sufficient to generate up to 15s of high quality speech / song driven Video at a high speed with no quality degradation. Support for TeaCache included.\
Here is a link to the original repo where you will find some very interesting documentation and examples. https://github.com/Tencent-Hunyuan/HunyuanVideo-Avatar. Kudos to the Hunyuan Video Avatar team for the best model of its kind.\
Also many thanks to Reevoy24 for his repackaging / completing the documentation

### May 28 2025: WanGP v5.31
👋 Added **Phantom 14B**, a model that you can use to transfer objects / people in the video. My preference goes to Vace that remains the king of controlnets.
VACE improvements: Better sliding window transitions, image mask support in Matanyone, new Extend Video feature, and enhanced background removal options.

### May 26, 2025: WanGP v5.3
👋 Settings management revolution! Now you can:
- Select any generated video and click *Use Selected Video Settings* to instantly reuse its configuration
- Drag & drop videos to automatically extract their settings metadata
- Export/import settings as JSON files for easy sharing and backup

### May 20, 2025: WanGP v5.2
👋 **CausVid support** - Generate videos in just 4-12 steps with the new distilled Wan model! Also added experimental MoviiGen for 1080p generation (20GB+ VRAM required). Check the Loras documentation to get the usage instructions of CausVid.

### May 18, 2025: WanGP v5.1
👋 **LTX Video 13B Distilled** - Generate high-quality videos in less than one minute!

### May 17, 2025: WanGP v5.0
👋 **One App to Rule Them All!** Added Hunyuan Video and LTX Video support, plus Vace 14B and integrated prompt enhancer.

See full changelog: **[Changelog](docs/CHANGELOG.md)**

## 📋 Table of Contents

- [🎯 Usage](#-usage)
- [📚 Documentation](#-documentation)
- [🔗 Related Projects](#-related-projects)

-----

# 📦 Installation

---

## Nvidia GPU Compatibility Only
 
- Only Nvidia GPU's GTX 10XX, 16XX and RTX 30XX, 40XX, 50XX: Sage Attention Supported on 30, 40 and 50 series. Use Install_Wan2GP_Torch_2.7.1+cu12.8.bat
---

### All Wan2GP updates comes directly from the original DeepBeepMeep/Wan2GP Repository.

1. Make sure your Nvidia graphics drivers are up-to-date. If they are not or if your not sure, please click on the following link to download Nvidia graphics drivers. 👉 [Nvidia Drivers](https://www.nvidia.com/en-us/software/nvidia-app/) 👈

2. Make sure you have Git installed as it will be needed to update Wan2GP, if not download the Git Standalone Installer and click on Git for Windows/x64 Setup. 👉 [Git Standalone Installer Download](https://git-scm.com/downloads/win) 👈 To install Git, double click Git.exe and just keep clicking next until it's installed, you don't need to change anything.

3. Now after you have made sure Nvidia GPU drivers are up to date and Git is installed, download Wan2GP.exe from here 👉 [Wan2GP-Windows-One-Click-Install-With-Sage](https://github.com/Redtash1/Wan2GP-Windows-One-Click-Install-With-Sage/releases/tag/v1.0.0) 👈 or from the Releases section at the top right of this page.

4. After downloading, double click Wan2GP.exe and pick where you would like to extract the zip files too.

5. Then open Wan2GP main folder and you will see this in the root

<img width="775" height="270" alt="Screenshot 2025-07-14 065810" src="https://github.com/user-attachments/assets/9ad3545c-0221-4221-9252-eae872ceadd9" />

</div>

6. Then double click on Install_Wan2GP_Torch_2.7.1+cu12.8.bat to start the installation. After installation is finished, slowly scroll back up to the top to make sure everything installed correctly.

7. To launch Wan2GP you can use either the Launch_Wan2GP.bat in the current folder or the Desktop shortcut.

### If this worked for you, Please give it a Star ⭐. Thank you. 

### If you have any problems with installation contact me Redtash1 at Discord Channel below but if it's with using or errors with Wan2GP after a successful installation, you can get Help from Deepbeepmeep or other Users from the official WanGP Discord: https://discord.gg/g7efUW9jGV

---

These instructions below won't work for this version of Wan2GP, because this version uses python_embeded and not Conda or a venv. But you can try them if you want to do a manual install without using this Wan2GP Stand-alone version but you should go to the original Wan2GP Repository and Git clone it from there.

For detailed installation instructions for different GPU generations: 
- **[Installation Guide](docs/INSTALLATION.md)** - Complete setup instructions for GTX 10XX to RTX 50XX

## 🎯 Usage

### Basic Usage
- **[Getting Started Guide](docs/GETTING_STARTED.md)** - First steps and basic usage
- **[Models Overview](docs/MODELS.md)** - Available models and their capabilities

### Advanced Features
- **[Loras Guide](docs/LORAS.md)** - Using and managing Loras for customization
- **[Finetunes](docs/FINETUNES.md)** - Add manually new models to WanGP
- **[VACE ControlNet](docs/VACE.md)** - Advanced video control and manipulation
- **[Command Line Reference](docs/CLI.md)** - All available command line options

## 📚 Documentation

- **[Changelog](docs/CHANGELOG.md)** - Latest updates and version history
- **[Troubleshooting](docs/TROUBLESHOOTING.md)** - Common issues and solutions

## 🔗 Related Projects

### Other Models for the GPU Poor
- **[HuanyuanVideoGP](https://github.com/deepbeepmeep/HunyuanVideoGP)** - One of the best open source Text to Video generators
- **[Hunyuan3D-2GP](https://github.com/deepbeepmeep/Hunyuan3D-2GP)** - Image to 3D and text to 3D tool
- **[FluxFillGP](https://github.com/deepbeepmeep/FluxFillGP)** - Inpainting/outpainting tools based on Flux
- **[Cosmos1GP](https://github.com/deepbeepmeep/Cosmos1GP)** - Text to world generator and image/video to world
- **[OminiControlGP](https://github.com/deepbeepmeep/OminiControlGP)** - Flux-derived application for object transfer
- **[YuE GP](https://github.com/deepbeepmeep/YuEGP)** - Song generator with instruments and singer's voice

---

<p align="center">
Made with ❤️ by DeepBeepMeep
</p>  
