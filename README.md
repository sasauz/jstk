# What is the JSTK (and what not)
The Jave speech toolkit (JSTK) provides a native implementation of both library/API and applications for speech recognition, speaker verification, speech visualization (including transcription tools), and evaluation of related human rater tasks.
JSTK is *not* a full-blown LVCSR toolkit with pre-trained models, sorry.

# Building JSTK
You can import JSTK as a project to Eclipse, or use the provided gradle file to build the complete jar file (and dependencies) in `build/libs/{jstk-latest,libs/*}.jar`

# Using JSTK
The easiest way to use the command line tools is to make a script like the following:
```
$ cat jstk
#!/bin/bash

CLASSPATH=/home/sikoried/Work/workspace/jstk/bin:/home/sikoried/Work/lib/jtransforms-2.3.jar:/home/sikoried/Work/lib/Jama-1.0.2.jar:/home/sikoried/Work/lib/FJama.jar:/home/sikoried/Work/lib/log4j-1.2.16.jar

java -Xmx7G de.fau.cs.jstk.$@
```

Can be used then as

```
$ ./jstk app.Decoder
```

# Maintenance and Support

The Java Speech Tooklit (JSTK) is developed and maintained by the Speech Group
at the University of Erlangen-Nuremberg. It is designed to provide both API and
applications for the most popular speech tasks such as speech recognition,
speaker verification, speech transcription and annotation and evaluation of
human rater tasks. The current maintainers of the toolkit can be reached at

jstk@speech.informatik.uni-erlangen.de

The JSTK is licensed under GPLv3 and welcomes any contributions in terms of
extensions, bugfixes, feature requests or comments. Note that code maintenance
is (for now) only done at the speech group of Univ. Erlangen. Though this
toolkit is intended to allow full-scale speech applications, special APIs such
as the Google Android Speech API or Java Speech API are not implemented (but may
however be implemented in the future).

The toolkit makes use of the following third party libraries:

JTransforms - http://sites.google.com/site/piotrwendykier/software/jtransforms
> JTransforms provides (discrete) signal processing routines such as FFT, DHT,
> and DCT. It relies on state-of-the-art algorithms and even allows multi-
> threading.

JAMA - http://math.nist.gov/javanumerics/jama/
> The JAMA package provides linear algebra routines such as decompositions
> (e.g. Eigen, LR, QR) and matrix operations (calculus, inversions).
> A single precision copy is maintained at the Speech Group named FJAMA, and
> a snapshot can be found in the download section of this project.

log4j - http://logging.apache.org/log4j
> log4j provides scalable logging capabilities, however, JSTK only uses the
> very basic features of it -- for now. Currently, we use v 1.2.16

jspeex - http://sourceforge.net/projects/jspeex/files/jspeex
> jspeex is used for decoding speex-compressed (`*`.spx) files. speex is a lossy
> codec comparable to MP3 or Ogg Vorbis, but optimized for speech, see http://www.speex.org.
> Currently using version 0.9.7.

junit - http://www.junit.org
> Testing framework for java. currently used only sporadically.
> Currently using version 4.