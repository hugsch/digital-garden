---
id: sbp55yigsb1520nsln22ohq
title: Integrate voice-over with background music
desc: 'How lowering the background volume when voice-over is playing?'
updated: 1671310156519
created: 1671302794064
---
Your edited movie has some nice background music and ambient noise. Now, it's time to add the narrative voice or voice-over. Most of time these voice-over fragments are distributed irregularly along the timeline. Ideally, you should lower the volume of the background music when the voice-over starts, so that it becomes more comprehensible. This is called ducking (see figure 1).

![](/assets/images/vse.audio.svg)
Figure 1: Garph Editor window (left) with keyframed Volume (of background music).

You can do this manually by keyframing the volume of the music strip.

- Select the background music strip
- Place the playhead (current frame) at the beginning of the voice-over; e.g. around 00:20'
- Hover over the volume field in the side panel (right). It should be around 1.8 for the example of figure 1.
- Press I (the letter I) or click at the small circle at the right of the field. This will set a keyframe.
- Move the playhead a few frames to the right.
- Lower the volume to around 0.6 (see figure 1) and keyframe (press I).
- Repeat the last two steps in revers at the end of the voice -over (around 00:40').

Of course, this is a lot of work. Fortunately, this could be done automatically in [Audacity](https://www.audacityteam.org/), a free, open source, cross-platform audio software. You also need a Blender add-on to transfer the audio-strips from Blender to Audacity and back again. 

Instal add-on [Audacity tools for Blender](https://github.com/tin2tin/audacity_tools_for_blender) 

	- start Audacity & Blender with project
	- Convert each track to mono?
	- When eveything seems OK (except volumes); send sequence to Audacity. Tracks are in order: music (top), voice-over (middle), environment (bottom)
   - select the music and voice strips.
   - In the sidebar, auacity tools tab in the sidebar (right), swith to selection (in stead of strip)
   - Push send selection. 
   Switch to Audacity
   
	- Indien er voice-track gegroepeerd zijn, worden die in verschillende kanalen geplaatst. Deze tracks (wellicht 3 & 4) moeten dan gemerged worden via Tracks > Mix > Mix and render
	- Normalize : music track = -20db; voice-over: -6db; environment: -14db
	- Autoduck: minus -10 dB (1 second fade up om geen jojo effect te hebben bij kleine spaties)
	- In blender: receive sequence (maar je moet we de langste (=music) strip geselecteerd hebben. Best ook Audacity tussen beurten afsluiten en terug opstarten (problemen met pipe?)
	- Indien environment moet versterkt worden, kan de originele sound-clip worden unhided (in Blender; dus je verkrijgt 2x de omgevingsgeluiden)
Ik heb een macro gemaakt (menu Tools > Apply Macro > Jaarboek) dat alle voorgaande stappen automatisch na elkaar uitvoert: track 1 (normalize & autoduck), track 2 (normalize: -6dB); track 3 (normalize -14dB). De track moeten in de juiste volgorde staan en Track 1 moet blijkbaar wel geselecteerd zijn.

Track Content

9 Tekst voice-over

8 Background music

7 Voice-over

6 Sound media

5 
4
3 VFX media (transition -effect)

2 Media-2 (or group if more)

1 Media-1



https://freesound.org/s/520673

![](/assets/images/2022-12-17-21-47-48.png)

![](/assets/images/2022-12-17-21-48-55.png)