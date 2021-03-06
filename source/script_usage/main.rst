.. -----------------------------------------------------------------------------
    ..
    ..  Filename       : main.rst
    ..  Author         : Huang Leilei
    ..  Created        : 2020-07-12
    ..  Description    : script usage related documents
    ..
.. -----------------------------------------------------------------------------

Script Usage
============

(20201117) build/linux (linux env)
----------------------------------

*   function

    #.  generate the executable file

    \

*   pre-requests

    #.  gcc, g++ (my version is 7.5.0)
    #.  make     (my version is 4.1)
    #.  cmake    (my version is 3.10.2)

    \

*   steps

    #.  execute "./build.sh"     to build x64-version environment
        or      "./build.sh x84" to build x86-version environment

        .. image:: buildLinuxStep1.png

        \

    #.  execute "make" to generate f265 executable file

        .. image:: buildLinuxStep2.png

        \

    #.  modify script/run/f265.cfg according to your requests, for example

        *   InputFile    /mnt/e/DOWNLOAD/SEQUENCE/bitDepth_8/BasketballPass/BasketballPass.yuv

        \

    #.  execute "./f265 -c ../../script/run/f265.cfg" to run the f265 executable file

        .. image:: buildLinuxStep4.png

        \

    #.  by the way, I have created a single-run script "run.sh" which

        *   executes step 1, 2 and 4.
        *   calculates the md5sum of f265.hevc
        *   decodes f265.hevc
        *   compares the decoded yuv file with the dumped yuv file f265.yuv

        \

(20201117) build/windows (windows env)
--------------------------------------

*   function

    #.  generate the executable file

    \

*   pre-requests

    #.  cmake         (my version is 3.18.0-rc4)
    #.  visual studio (my version is 2019-16.4.3)

    \

*   steps

    #.  modify build.bat according to your environment, for example

        *   "Visual Studio 16 2019" for vs2019
        *   "Visual Studio 15 2017" for vs2017

        \

    #.  double click build.bat

        .. image:: buildWindowsStep2.png

        \

    #.  open f265.sln

        .. image:: buildWindowsStep3.png

        \

    #.  set f265 as the startup item

        .. image:: buildWindowsStep4.png

        \

    #.  add "-c ..\\..\\script\\run\\f265.cfg" to the command-line parameters of f265

        .. image:: buildWindowsStep5a.png
        .. image:: buildWindowsStep5b.png

        \

    #.  *set the stack reserve size of f265 to 10000000*

        thanks to the pointer-type varibles adopted now, this step is no longer necessary.

        \

    #.  modify script/run/f265.cfg according to your requests, for example

        *  InputFile    E:\\DOWNLOAD\\SEQUENCE\\bitDepth_8\\BasketballPass\\BasketballPass.yuv

        \

    #.  click "Start" to generate and run f265 executable file

        .. image:: buildWindowsStep8.png

        \

(20201117) doc/doxygen (linux env)
----------------------------------

*   function

    *   generate documents

    \

*   pre-requests

    *   doxygen (my version is 1.8.13)
    *   graphviz

    \

*   steps

    *   execute "./doxygen.sh"

        .. image:: docDoxygenStep1.png

        \

(20200917) script/run (linux env)
---------------------------------

*   function

    #.  automatically run f265 according to your lists (sequence × qp)
    #.  calculate and note down md5sum of hevc files
    #.  compare reconstructed and decoded pictures and mark any mismatch
    #.  extract PSNR and bit rate information
    #.  calculate B-D rate

    \

*   pre-requests

    #.  gcc, g++ (my version is 7.5.0)
    #.  make     (my version is 4.1)
    #.  cmake    (my version is 3.10.2)
    #.  md5sum   (my version is 8.28)
    #.  ffmpeg   (my version is 3.4.6)
    #.  python3  (my version is 3.6.9)

    \

*   steps

    #.  modify f265.sh according to your requests, for example

        *   NAME_DIR_SEQ="/mnt/e/DOWNLOAD/SEQUENCE/bitDepth_8"

        \

    #.  execute "make run"

        .. image:: scriptRunStep2.png

        \

(20200917) script/showDiff (matlab env)
---------------------------------------

*   function

    #.  compare two pictures

    \

*   pre-requests

    #.  matlab (my version is 2019b)

    \

*   steps

    #.  modify showDiff.m according to your requests, for example

        *   A_FILE       = '../run/sessionTest/dump/BasketballPass_22/f265.tmp.yuv';
        *   B_FILE       = '../run/sessionTest/dump/BasketballPass_22/f265.yuv';

        \

    #.  execute showDiff.m

        if no mismatch is detected, it will automatically run to the end

        .. image:: scriptShowDiffStep2a.png

        if mismatch is detected, it will stop

        .. image:: scriptShowDiffStep2b.png

        and you can check the mismatch

        .. image:: scriptShowDiffStep2c.png

        \
