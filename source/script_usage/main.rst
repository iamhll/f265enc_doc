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

(20211026) build/linux (linux env)
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

        #.  execute "./build.sh [FLAG_X86=<ON|OFF>] [FLAG_ASM=<ON|OFF>]" to build linux environment

            .. image:: buildLinuxStep1.png

            \

        #.  execute "make" to generate xkcdc executable file

            .. image:: buildLinuxStep2.png

            \

        #.  modify script/run/xkcdc.cfg according to your requests, for example

            *   \-\-strFileYuv    /mnt/e/DOWNLOAD/SEQUENCE/HM/BasketballPass/BasketballPass.yuv

            \

        #.  execute "./xkcdc -c ../../script/run/xkcdc.cfg" to run the executable file xkcdc under encoding mode

            .. image:: buildLinuxStep4.png

            \

        #.  by the way, I have created a single-run script "run.sh" which

            *   executes step 1, 2 and 4.
            *    (the compressed bin file is saved as xkcdc.bin, while the reconstructed yuv file is saved as xkcdc.yuv)
            *   decodes xkcdc.bin with ffmpeg
            *   (the decoded yuv file is saved as xkcdc.tmp.yuv)
            *   differ xkcdc.tmp.yuv and xkcdc.yuv
            *   calculates the md5sum of xkcdc.bin, xkcdc.yuv and xkcdc.tmp.yuv
            *   remove xkcdc.yuv
            *   decodes xkcdc.bin with xkcdc
            *   (the decoded yuv file is saved as xkcdc.yuv)
            *   differ xkcdc.tmp.yuv and xkcdc.yuv
            *   calculates the md5sum of xkcdc.yuv and xkcdc.tmp.yuv

            \


(20211026) build/windows (windows env)
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

        #.  open xkcdc.sln

            .. image:: buildWindowsStep3.png

            \

        #.  set xkcdc as the startup item

            .. image:: buildWindowsStep4.png

            \

        #.  add "-c ../../script/run/xkcdc.cfg" to the command-line parameters of xkcdc
            (both slash and backslash can be recognized)

            .. image:: buildWindowsStep5a.png
            .. image:: buildWindowsStep5b.png

            \

        #.  *set the stack reserve size of xkcdc to 10000000*

            *thanks to the pointer-type varibles adopted now, this step is no longer necessary*

            \

        #.  modify script/run/xkcdc.cfg according to your requests, for example

            *   \-\-strFileYuv    E:\\DOWNLOAD\\SEQUENCE\\HM\\BasketballPass\\BasketballPass.yuv

            \

        #.  click "Start" to generate and run xkcdc executable file

            .. image:: buildWindowsStep8.png

            \


(20211026) doc/doxygen (linux env)
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


(20211026) script/run (linux env)
---------------------------------

    *   function

        #.  automatically run xkcdc according to your lists (sequence × qp)
        #.  calculate and note down md5sum of bin files
        #.  compare the reconstructed and decoded yuv files and mark any mismatch
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

        #.  modify xkcdc.sh according to your requests, for example

            *   CSTR_DIR_SRC="/mnt/e/DOWNLOAD/SEQUENCE/HM"

            \

        #.  execute "make run"

            .. image:: scriptRunStep2.png

            \


(20211026) script/anaYuvForDiff (matlab env)
--------------------------------------------

    *   function

        #.  compare two yuv files

        \

    *   pre-requests

        #.  matlab (my version is 2019b)

        \

    *   steps

        #.  modify anaYuvForDiff.m according to your requests, for example

            *   CSTR_FILE_A = '../run/sessionTest/dump/BasketballPass_22/xkcdc.tmp.yuv';
            *   CSTR_FILE_B = '../run/sessionTest/dump/BasketballPass_22/xkcdc.yuv';

            \

        #.  execute anaYuvForDiff.m

            if no mismatch is detected, it will automatically run to the end

            .. image:: scriptShowDiffStep2a.png

            if mismatch is detected, it will stop

            .. image:: scriptShowDiffStep2b.png

            and you can check the position of any mismatch

            .. image:: scriptShowDiffStep2c.png

            \
