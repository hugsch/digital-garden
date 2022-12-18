Finally. Your edited movie is almost finished. You have just added some background music and environmental (ambient) sounds. Now, it's time to add the narrative voice or voice-over. These voice-over fragments are probably distributed irregularly along the timeline. In order to understand the narrative well, you should lower the volume of the background music a bit while talking. This is called ducking (see figure 1).

![](/assets/images/vse.audio.svg)
Figure 1: Graph Editor window (left) with keyframed Volume (right) of the background music strip.

You can do this manually by keyframing the volume of the music strip.

- Select the background music strip. Set the playhead (current frame) at the beginning of the voice-over; e.g. around 00:20' in figure 1.
- Hover over the volume field with the mouse in the side panel (right) and press the shortkey I (the letter I) or click at the small circle at the right of the field. This will set a keyframe.
- Move the playhead a few frames to the right. Lower the volume (around 0.6 in figure 1) and keyframe again (press I).
- Repeat the last two steps in reverse at the end of the voice-over (around 00:40' in figure 1). If you have Display Waveform turned on, you will see the result immediately (see figure 1 - middle panel).

Of course, this is a lot of work and error-prone. Also, if you should move the voice-over strip in the timeline, you have to reverse the volume changes. Fortunately, this ducking could be accomplished automatically with [Audacity](https://www.audacityteam.org/), a free, open source, cross-platform audio software. You may also need a Blender add-on [Audacity tools for Blender](https://github.com/tin2tin/audacity_tools_for_blender) to transfer the audio-strips from Blender to Audacity and back again.

# Without the add-on

- Export each audio channel of your project individually. To export the background music channel of figure 1, you have to disable the voice-over channel.
- Select the menu Render > Render Audio. Apply the appropriate values for container, bitrate, ...
- Import each file in Audacity. You have to place the Background music in the top channel and the voice-over right beneath it. Be sure that you have the Music channel selected.
- Apply the ducking with the menu Effects > Auto Duck. The [default values](https://manual.audacityteam.org/man/auto_duck.html) are quite smart.

# With the add-on Audacity tools for Blender

- Install the add-on. You can find the source-files at [tin2tin's github](https://github.com/tin2tin/audacity_tools_for_blender). Don't forget to specify the Audacity Executable (location); e.g. C:\Program Files\Audacity\Audacity.exe in a Windows machine. Note also the warning in the add-on info panel: "Before running this add-on, Audacity must be running with the Preferences > Modules > mod_script_pipe Enabled".
- Start Audacity and switch to Blender. Select the audio strips, you want to transfer and click the button `Send Selection` in the sidebar. With `Selection`drop-down, you can choose between strip (the active strip with white border in figure 2), `Selection` (the selected strips), `Sequence` (all audio strips) and `Record` (if you have a microphone available; Audacity will start recording).

![](/assets/images/vse.audio.addon.png)
Figure 2: Blender with some audio strips and the Audacity Tools panel visible (right).

- Switch to Audacity. The selected audio strips should be available. The result of `Send Selection` will look like figure 3. Note that the audio strips are placed at the appropriate time slots. 

![](/assets/images/vse.audio.audacity1.png)
Figure 3: Result within Audacity of the `Send Selection` command in Blender.

- Apply the Auto Duck effect. As you can see in figure 4, the background music volume is lowered while the voice-over is playing with about 10 dB (default value).

![](/assets/images/vse.audio.audacity1.png)
Figure 4: Result of the Effect > Auto Duck command with default values.

- The effect kicks in about half a second before the voice-over starts and fades out for about 1 second after the voice over finishes (see figure 5). The music will be lowered with 10 dB.

![](/assets/images/vse.audio.audacity3.png)
Figure 5: Default values of the Auto Duck effect.

- After applying the Auto Duck in Audacity, you can transfer the result back to Blender with the Receive Mixdown button (see figure 2). In reality, the Audacity Tool has saved the result in a separate file in the active directory that you can import. Please, don't forget to mute or delete the original sound tracks; otherwise you will increase the sound level heavily.

Please note that the tracks must be in the correct order: background music on top and right beneath it the voice-over. It's a good habit to have this order also in Blender. For example:

Channel 1: Blanc
Channel 2: blanch
Channel 3: Audio strips, associated with the movie strips from channel 5
Channel 4: Background music. The will probably cover the entire timeline consecutively.
Channel 5: Regular movie strips (visual). The audio part is automatically placed in channel 3 while importing, because channel 4 is already occupied with the background music.
Channel 6 - 9: other movie strips and visual special effects.
Channel 10: subtitles.

While you are in Audacity, it is probably wise to also Normalize your audio and to set some peak levels for the different audio media. For example the background music shouldn't dominate and probably set at a volume level of about -20 dB. While, the voice-over could be set at a peak level of about -6 dB. Normalizing is also one of the many effects you could use in Audacity (menu Effects > Normalize).

It's possible to record/create macro's in Audacity that will execute the above commands automatically.
