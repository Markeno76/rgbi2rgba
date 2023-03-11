# rgbi2rgba
Commodore 128 RGBI / CGA  to Analog RGB

I made this project to be a RGBI/CGA (RGB Digital) to RGBA (RGB Analog) for the Commodore 128 RGBI 80 Column Video output.  This also works with CGA Video being the same type of video signal.  Both are Digital RGB with an Intensity signal that provides Light/Dark for each of the RGB Signals.  CGA/RGBI both share the "Brown" instead of "Dark Yellow" output.  More basic methods of converting the RGBI to Analog RGB can just ignore the Intensity signal, but that drops half the colors.  It can also ignore the Brown Fix.  This converter includes use of the Intensity Signals and does the Brown fix.

You can view the blog post about the adapter here: https://hobbytronics.home.blog/2023/02/07/commodore-128-80-column-or-cga-rgbi-to-rgba-15khz-vga-adapter-part-2/

I based it on various schematics I found online for a combination of CGA and Commodore 128 RGBI adapters.  The adapter outputs either RGBS or RGBHV, but at 15khz so it was setup to go into a SCART to HDMI Adapter.  It also can work with a GBS Control which takes RGBHV or RGBS and outputs standard VGA output (RGBHV at 31khz).

For this revision of the Adapter I have extended the options for the Commodore 128.  The prototype back in 2019 used the Commodore AV Port for power and passed through Audio and Composite 40 Column Video.  The new version now has passthrough output for Monochrome 80 Column mode (it was easy to include), Composite 40 Column Video, Audio Output, and S-Video 40 Column Video.  When doing that with the Commodore 128 it gets 5V from the Commodore AV Port.  I added a DC Power Jack that can be used to make it easy to connect the adapter up as an adapter for IBM CGA.  Don't connect up both the Commodore AV Port power and the DC Power Jack please..

When only using the adapter for IBM CGA, you can omit the 3 RCA Jacks and the S-Video Jack. There are some header pins that can be ommited as well for the Commodore AV port.  The board has some onboard jumpers to switch between RGBS and RGBHV.  There is also a Sync Invert option for use with the RGBS mode.  I can not remember why I added the sync invert option, but I think it had something to do with GBS boards at this time.

The board uses a DBHD15 VGA type port for 80 Column output.  This can use a standard VGA cable and go into the GBS Control.  It has 2 special use pins I used for my SCART to HDMI device, it has a 5V Blanking signal and outputs Audio to a a pin on the HD15 if the jumpers are set for that.  When using it with the GBS Control those both should be disabled.