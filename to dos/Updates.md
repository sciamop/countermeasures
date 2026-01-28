# Repurposing
## 11-01-26
**Problem**: How to build a mixed reality platform on the cheap. 

**Solution**: Scavange parts from a Meta Quest 2 headset (lenses and view screen)

**Approach**: Used Quest 2 headsets have crashed in value. Widely available for $30 - $40 on ebay in used/acceptable condition. 

**Challenge**: After disassembly, discovered that Quest 2 screen has proprietary connector. The only resuable parts are the mechanical viewport and fresnel lenses. 

**Commentary**: Quest 2 is just eWaste if you don't want to run Zuckerberg's spyware. 

---

# Mixed-Up reality
## November 30, 2025

**Problem**: Wearer of the veil will have their face obscured by an outward facing screen  

**Solution**: Provide an MR-enabled immersive view on a high-refresh/hi-resolution screen  

**Approach**: Hi-res/hi-refresh screens are very expensive and may require specialized compute to run at peak performance. Turns out that I have an integrated high-quality screen/compute in my… pocket! Many low cost VR systems use a smartphone as CPU/Display, so why not for Veil? 

**Challenge**: Significantly increases bulk on the front of the Veil (bad). Also its a mobile phone from Google which violates many of the precepts of the project (surviellance capitalism, platform, state surveillance tool, highly trackable).

**Commentary**: The Pixel 7 Pro is a good compromise for prototyping (Android has great development experience) but looking to switch to a screen-only hardware solution for launch. Pixel 7 Pro does have other advantages as well as it could provide most of the compute (except external display image) for the entire project as well.

---

# Facetook Part 1
## December 8, 2025

**Problem**: The opportunity to make commentary art out of the vast surveillance apparatus that engulfs us is enormous. The Veil project starts with a cornerstone of the modern surveillance stack -- facial recognition -- and sticks it in, well, your face.

**Approach**: Have you ever picked up your phone to take a picture and it is in selfie mode? The horror and awkwardness of seeing your own face staring back at you. Now imagine if this thing was projected on someone elses body... without your approval! Since I am using the Pixel 7 Pro (in the interim) as an MR display, I've got a powerful Android 14 compute device. It has built-in facial recognition support via ML Kit so its another good choice for prototyping.
 
**Challenge**: Just as above, this is all Google stuff on a highly-trackable mobile device. Ideally, I can get off this platform before completing this project! 

**Commentary**: Early experiments with ML Kit are VERY positive. It's fast, accurate and tunable. 

---

# Facetook Part 2
## December 12, 2025

**Problem**: ML Kit face capture works! However, displaying a static photo of a face on the external screen would be boring. *Identity* and *agency* are central to the message of Veil, so doing something *more* to the face than simply displaying it is appealing.

**Approach**: Use LivePortrait to bring the face to life on the screen. This should add to the horror of seeing one's own visage unexepectedly AND be a concrete example of how we unwillingly surrender ownership of our identity to digital surfaces. 
 
**Challenge**: While I do have a Raspberry Pi 5 w/ AI hat that I plan on using for onboard compute, it may still be very slow to animate the face. I've prototyped with using my desktop GPU via Tailscale and it was seriously slow. In order for this to be effective, it needs to be near realtime.  
