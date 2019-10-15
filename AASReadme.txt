Apex Audio System v1.11
(c) 2005 Apex Designs


LEGAL:

The contents of this archive should not be altered or reproduced without
permission. The Apex Audio System may be used free of charge in non-commercial
projects as long as the AAS logo is shown when the program is launched using the
AAS_ShowLogo() function call. Commercial developers must email
licensing@apex-designs.net to discuss licensing terms.


CONTENTS:

This archive contains the following files and folders:

AASDocs - Full documentation. Open the "index.html" file in your web browser to
read.
AASExample - Example AAS project demonstrating how to use AAS when there are no
other CPU-intensive interrupts in your code.
AASExample2 - Example AAS project demonstrating how to use AAS when there are
other CPU-intensive interrupts in your code.
AASExample_c++ - Example AAS project demonstrating how to use AAS in C++ when
there are no other CPU-intensive interrupts in your code.
AASFiles - Contains the AAS library and header files, Linux and DOS/Windows
versions of Conv2AAS and a specially modified version of crt0.s that allows AAS
to be used in conjunction with other CPU-intensive interrupts.
AASDemo.gba - Demonstrates AAS's capabilities and performance.
AASReadme.txt - This readme.


HISTORY:

v1.11, 9 January 2005:
  + Fixed several bugs with dynamic mixing.
  + Removed "long_call" from AAS_Mixer.h to allow AAS to work with older
    versions of GCC (pre 3.0).

v1.1, 10 November 2004:
  + Fixed a rare but serious bug that could cause a crash.
  + AAS_SetConfig() now doesn't change any IE flags except for the one that
    controls the Timer 1 interrupt.
  + Changed the AASExample_c++ makefile to link with g++ not gcc. Also included
    a new linkscript to allow AAS to be more easily used at the same time as
    the standard C++ libraries.

v1.09, 22 October 2004:
  + Added support for 16 channels, including support for 1-16 channel MODs.
  + Added special louder mixing modes.
  + Added an optimisation that reduces the mixer's average setup time,
    improving overall performance by ~5%.
  + Conv2AAS's WAV and MOD importers are now more robust and the data size
    limits have been increased.
  + Changed AAS_DoDMA3()'s parameters to void*.
  + EWRAM usage reduced by 0.2K to 3.3K. IWRAM usage increased by 0.1K to 3.2K.
  + AAS now uses a more robust Direct Sound FIFO stop procedure.
  + Fixed a very rare bug with AAS_MOD_Play().
  + Updated the FAQ and documentation.

v1.08, 12 November 2003:
  + Made the audio mixer ~15% faster. IWRAM usage increased by 0.6K to 3.1K.
  + Added AAS_MOD_GetNumChannels(). Returns the number of channels that are
    currently being reserved by the MOD.
  + Added a C++ example.

v1.07, 20 October 2003:
  + Added new MOD effect: "7: Tremolo".
  + Tweaked the "4: Vibrato" and "6: Vibrato + Volume Slide" MOD effects.
  + Added support for the restart song position in MODs.
  + Added AAS_MOD_SetSongPos(). Immediately jumps to the specified song
    position.
  + Added AAS_MOD_QueueSongPos(). Jumps to the specified song position when the
    current pattern finishes.
  + Added AAS_SFX_GetNumChannels(). Returns the number of channels available
    for SFX.
  + Changed the SFX channel arrangement to LRRLLRRL. Unlike before, this does
    not change depending on whether the number of channels used by the MOD is
    even or odd.
  + Fixed a bug in AAS_SFX_ChannelExists() when used in 4 channel mode.
  + Fixed an overflow bug in the demo that meant the average CPU usage
    indicator could go wrong after a while.

v1.06, 14 October 2003:
  + Added MOD/SFX pause/resume commands.
  + Quadrupled pitch accuracy.
  + Put AAS_Channel data in IWRAM and reworked structure for extra speed.
  + Abolished AAS_MixAudio()'s "mix_scale" parameter - the new "delta" element
    in the channel data is used instead. Faster and saves IWRAM.
  + Made MOD playing code 2.5 times faster so that it now uses just 0.025% of
    total CPU time per channel.
  + Improved the performance and accuracy of the "F: Set Speed" effect.
  + Fixed various problems with AAS_MOD_SetVolume().
  + Improved the interpolation inaccuracy when a channel's volume is set to
    zero.

v1.05, 29 September 2003:
  + Added support for Protracker/FastTracker/Falcon/TakeTracker 1-8 channel
    MODs.
  + MOD patterns are now split into seperate channels for better compression
    and support for different numbers of channels. Pattern data compressed by
    40% on average.
  + The demo now includes some 8 channel tunes.
  + Fixed a bug that broke the code that automatically removed redundant sample
    data.
  + A "3: Tone Portamento" effect without a corresponding note to slide to will
    now be ignored.

v1.04, 8 September 2003:
  + Added an alternative interrupt handling method for when there are other
    CPU-intensive interrupts.
  + Added new MOD effect: "0: Arpeggio".
  + Added new MOD effect: "6: Vibrato + Volume Slide".
  + Added new MOD effect: "B: Position Jump".
  + Added new MOD effect: "E6: Set/Jump to Loop".
  + Added new MOD effect: "E9: Retrigger Note".
  + Added new MOD effect: "ED: Note Delay".
  + Added new MOD effect: "EE: Pattern Delay".
  + Added new MOD command: "AAS_MOD_SetLoop()".
  + The last value set by "E0: Set Filter" can now be read using the
    "AAS_MOD_GetLastFilterValue()".
  + A "D: Pattern Break" effect past the end of the song now counts as a loop.
  + Corrected amplitude of vibrato effect.
  + A Linux version of Conv2AAS is now included.
  + The Dos/Windows version of Conv2AAS no longer needs the Cygwin DLL to run.
  + Changed definitions of TRUE, FALSE, u8, s8, etc. to AAS_TRUE, AAS_FALSE,
    AAS_u8, AAS_s8, etc.

v1.03, 21 August 2003:
  + Fixed multiple interrupt support.

v1.02, 20 August 2003:
  + Changed header files (AAS.h and AASMixer.h) to work more easily with C++.
  + Changed Conv2AAS to produce header files that will work more easily with
    C++.
  + Added list of resources used by AAS to the "Getting Started" section of the
    docs.

v1.01, 17 August 2003:
  + Initial release.


CONTACTING US:

AAS Website: http://www.apex-designs.net/tools_aas.html
Licensing (required for commercial projects): licensing@apex-designs.net
Questions, suggestions and bug reports: tools@apex-designs.net
