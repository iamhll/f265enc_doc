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

build/linux
-----------

*   function

    #.  build environment for linux

    \

*   pre-requests

    #.  gcc, g++ (my version is 7.5.0 )
    #.  make     (my version is 4.1   )
    #.  cmake    (my version is 3.10.2)

    \

*   steps

    #.  execute "./build.sh"     to build x64-version environment
        or      "./build.sh x84" to build x86-version environment

        .. image:: buildLinuxStep1.png

        \

    #.  execute "make" to generate f265 executable file

        .. image:: buildLinuxStep2.png

        **sure, we will fix those warnings later**

        \

    #.  modify script/run/f265.cfg according to your requests, for example

        *   InputFile    /mnt/e/DOWNLOAD/SEQUENCE/bitDepth_8/BasketballPass/BasketballPass.yuv

        \

    #.  execute "./f265 -c ../../script/run/f265.cfg" to run the f265 executable file

        .. image:: buildLinuxStep4.png

        \

build/windows
-------------

*   function

    #.  build environment for windows

    \

*   pre-requests

    #.  cmake         (my version is 3.18.0-rc4 )
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

    #.  add "-c ..\..\script\run\f265.cfg" to the command-line parameters of f265

        .. image:: buildWindowsStep5a.png
        .. image:: buildWindowsStep5b.png

        \

    #.  set the stack reserve size of f265 to 10000000

        .. image:: buildWindowsStep6b.png

        \

    #.  modify script/run/f265.cfg according to your requests, for example

        *  InputFile    E:\DOWNLOAD\SEQUENCE\bitDepth_8\BasketballPass\BasketballPass.yuv

        \

    #.  click "Start" to generate and run f265 executable file

        .. image:: buildWindowsStep8.png

        \

script/run
----------

    *   function

        #.  automatically run f265 according to your lists (sequence × qp)
        #.  calculate md5sum of each hevc file
        #.  compare reconstructed and decoded picture and mark any mismatch
        #.  extract PSNR and bit rate information

        \

    *   pre-requests

        #.  gcc, g++ (my version is 7.5.0 )
        #.  make     (my version is 4.1   )
        #.  cmake    (my version is 3.10.2)
        #.  md5sum   (my version is 8.28  )
        #.  ffmpeg   (my version is 3.4.6 )
        #.  python   (my version is 3.6.9 )

        \

    *   steps

        #.  modify f265.sh according to your requests, for example

            *   NAME_DIR_SEQ="/mnt/e/DOWNLOAD/SEQUENCE/bitDepth_8"

            \

        #.  execute "make run"

            .. image:: scriptRunStep2.png

            \

script/showDiff
---------------

    *   function

        #.  compare two pictures

        \

    *   pre-requests

        #.  matlab

        \

    *   steps

        #.  modify showDiff.m according to your requests, for example

            *   A_FILE       = '../run/sessionTest/dump/BasketballPass_22/f265.tmp.yuv';
            *   B_FILE       = '../run/sessionTest/dump/BasketballPass_22/f265.yuv';

            \

        #.  execute showDiff.m

            if no mismatch is detected, it will automatically run to the end

            .. image:: scriptShowDiffStep2a.png

            if mismatch is detected, it will stop, and you can check the mismatch

            .. image:: scriptShowDiffStep2b.png
            .. image:: scriptShowDiffStep2c.png

            \
