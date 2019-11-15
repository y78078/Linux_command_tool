# USB midi

ALSA devices are in /dev/snd/.
OSS interface

To show incoming MIDI messages, run aseqdump -p xxx with the port name shown by aseqdump -l.

To show the raw MIDI bytes, run amidi --dump -p xxx with the port name shown by amidi -l.

https://superuser.com/questions/737531/how-do-i-view-a-midi-device-stream
