mute-application
================

Simple script for muting and unmuting applications on pulseaudio
systems. Uses pacmd to get information about pulseaudio sink inputs,
parses it, and then mutes or unmutes the applications you specify
using pactl.

I wrote this because I couldn't find a brainless but functional way to
mute a single program's audio. Things that this script does that I
couldn't get with the other solutions I found:
* Can mute audio streams by matching against either the pulseaudio
  application name or the name of the binary feeding the stream. It
  can even match on both at once in case some of your programs are
  being obtuse.
* Uses regexes to do matching, so you don't have to specify the entire
  binary or name perfectly.
* Will operate on _every_ application or binary that matches the
  given criteria. Other solutions I found would only act on the first
  or would entirely fail when an intermediate stage found multiple
  results.
* All functionality is controlled by command-line switches, which, when
  combined with the regexes and ability to act on many streams, means
  you can bind an invocation of this script to a keyboard shortcut
  with consistently good results.
