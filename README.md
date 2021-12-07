## checkseq

#### Check the presence and file sizes of a sequence of frames.

```
Usage: checkseq -f <first> -l <last> -s <size-in-bytes-approx> -x <number-regex> <files>

Options:"
  -f     The first expected frame of the sequence. (Required)
  -l     The last expected frame of the sequence. (Required)
  -s     The expected size of the largest file. This is used to scale the width of the ascii chart.
             If you don't provide a value, it will attempt to be 100 characters wide based on the
             size of the first existing file.
  -x     Regular expression to catch the frame number.
             Default is: \".*\.([0-9]+)\..*\". It captures a number between 2 dots, e.g. my_file.0001.exr
             Example: \".*F([0-9]+)_.*\". It captures a number between F and _, e.g. my_file__F0001_exr
  -h     Print this message.

If any frames are missing, a frame spec will be printed at the end. this can be used to start a new render.

Examples:
   checkseq -f 500 -l 600 -s 300000000 -x \".*_([0-9]+).*\" shot1_05??
   Check the sequence expected to start at 500 and end at 600 with filenames where the frame follows an
   underscore. If the file sizes are around 100 Mb, then the width of the chart will be around 30 characters.

   checkseq -f 500 -l 1500 shot1_*
   Check the sequence expected to start at 500 and end at 1500 with filenames are standard format: name.number.ext
   The chart will be about 100 characters wide based on the size of the first file.
```
