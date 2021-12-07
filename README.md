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
             Default is: ".*\.([0-9]+)\..*". It captures a number between 2 dots, e.g. my_file.0001.exr
             Example: ".*F([0-9]+)_.*". It captures a number between F and _, e.g. my_file__F0001_exr
  -h     Print this message.

If any frames are missing, a frame spec will be printed at the end. this can be used to start a new render.

Examples:
   checkseq -f 500 -l 600 -s 300000000 -x ".*_([0-9]+).*" shot1_05??
   Check the sequence expected to start at 500 and end at 600 with filenames where the frame follows an
   underscore. If the file sizes are around 100 Mb, then the width of the chart will be around 30 characters.

   checkseq -f 500 -l 1500 shot1_*
   Check the sequence expected to start at 500 and end at 1500 with filenames are standard format: name.number.ext
   The chart will be about 100 characters wide based on the size of the first file.
```

#### Example session:


```
checkseq -f 500 -l 600 -s 300000000 -x ".*_([0-9]+).*" *_05*
First frame:          500
Last frame:           600
Approximate size:     300000000
Regular expression:   .*_([0-9]+).*
26 missing frames : 500-525
Cam_SHOTB1Shot_B_0526.exr 526 -- 82605732 bytes  ===========================|
Cam_SHOTB1Shot_B_0527.exr 527 -- 83425286 bytes  ===========================|
Cam_SHOTB1Shot_B_0528.exr 528 -- 83907173 bytes  ===========================|
Cam_SHOTB1Shot_B_0529.exr 529 -- 84489881 bytes  ============================|
Cam_SHOTB1Shot_B_0530.exr 530 -- 85318190 bytes  ============================|
Cam_SHOTB1Shot_B_0531.exr 531 -- 86101413 bytes  ============================|
Cam_SHOTB1Shot_B_0532.exr 532 -- 86713060 bytes  ============================|
Cam_SHOTB1Shot_B_0533.exr 533 -- 87291498 bytes  =============================|
Cam_SHOTB1Shot_B_0534.exr 534 -- 87854967 bytes  =============================|
Cam_SHOTB1Shot_B_0535.exr 535 -- 88415317 bytes  =============================|
Cam_SHOTB1Shot_B_0536.exr 536 -- 88834003 bytes  =============================|
9 missing frames : 537-545
Cam_SHOTB1Shot_B_0546.exr 546 -- 94342339 bytes  ===============================|
Cam_SHOTB1Shot_B_0547.exr 547 -- 95023211 bytes  ===============================|
Cam_SHOTB1Shot_B_0548.exr 548 -- 95919796 bytes  ===============================|
Cam_SHOTB1Shot_B_0549.exr 549 -- 95815658 bytes  ===============================|
Cam_SHOTB1Shot_B_0550.exr 550 -- 96239867 bytes  ================================|
Cam_SHOTB1Shot_B_0551.exr 551 -- 96934787 bytes  ================================|
Cam_SHOTB1Shot_B_0552.exr 552 -- 97464145 bytes  ================================|
Cam_SHOTB1Shot_B_0553.exr 553 -- 97398335 bytes  ================================|
Cam_SHOTB1Shot_B_0554.exr 554 -- 97679111 bytes  ================================|
Cam_SHOTB1Shot_B_0555.exr 555 -- 97401826 bytes  ================================|
Cam_SHOTB1Shot_B_0556.exr 556 -- 97205538 bytes  ================================|
Cam_SHOTB1Shot_B_0557.exr 557 -- 96749615 bytes  ================================|
Cam_SHOTB1Shot_B_0558.exr 558 -- 96333459 bytes  ================================|
Cam_SHOTB1Shot_B_0559.exr 559 -- 95821850 bytes  ===============================|
Cam_SHOTB1Shot_B_0560.exr 560 -- 94983850 bytes  ===============================|
Cam_SHOTB1Shot_B_0561.exr 561 -- 94140295 bytes  ===============================|
Cam_SHOTB1Shot_B_0562.exr 562 -- 93218846 bytes  ===============================|
Cam_SHOTB1Shot_B_0563.exr 563 -- 92333254 bytes  ==============================|
Cam_SHOTB1Shot_B_0564.exr 564 -- 90892151 bytes  ==============================|
Cam_SHOTB1Shot_B_0565.exr 565 -- 89840799 bytes  =============================|
Cam_SHOTB1Shot_B_0566.exr 566 -- 89203537 bytes  =============================|
9 missing frames : 567-575
Cam_SHOTB1Shot_B_0576.exr 576 -- 88993233 bytes  =============================|
Cam_SHOTB1Shot_B_0577.exr 577 -- 88947811 bytes  =============================|
8 missing frames : 578-585
Cam_SHOTB1Shot_B_0586.exr 586 -- 88639412 bytes  =============================|
Cam_SHOTB1Shot_B_0587.exr 587 -- 88613347 bytes  =============================|
Cam_SHOTB1Shot_B_0588.exr 588 -- 88464205 bytes  =============================|
Cam_SHOTB1Shot_B_0589.exr 589 -- 88474613 bytes  =============================|
Cam_SHOTB1Shot_B_0590.exr 590 -- 88464631 bytes  =============================|
Cam_SHOTB1Shot_B_0591.exr 591 -- 88615885 bytes  =============================|
Cam_SHOTB1Shot_B_0592.exr 592 -- 89022547 bytes  =============================|
Cam_SHOTB1Shot_B_0593.exr 593 -- 89607072 bytes  =============================|
Cam_SHOTB1Shot_B_0594.exr 594 -- 89469709 bytes  =============================|
Cam_SHOTB1Shot_B_0595.exr 595 -- 89055485 bytes  =============================|
Cam_SHOTB1Shot_B_0596.exr 596 -- 89023833 bytes  =============================|
Cam_SHOTB1Shot_B_0597.exr 597 -- 89154478 bytes  =============================|
Cam_SHOTB1Shot_B_0598.exr 598 -- 89513870 bytes  =============================|
2 missing frames: 599-600
You may paste the following range specification into the custom frames field of the submitter.
500-525,537-545,567-575,578-585,599-600,
```
