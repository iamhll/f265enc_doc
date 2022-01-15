.. -----------------------------------------------------------------------------
    ..
    ..  Filename       : main.rst
    ..  Author         : Huang Leilei
    ..  Created        : 2020-07-23
    ..  Description    : before everything
    ..
.. -----------------------------------------------------------------------------

Before Everything
=================

    Please get the following items ready before you start to work.

(20220115) WSL (windows and linux env)
--------------------------------------

    #.  enable the developer mode

        .. image:: WSL_enableDevMod.png

        \

    #.  install Ubuntu

        .. image:: WSL_install.png

        \

    #.  enable the WSL function

        .. image:: WSL_enableWSL.png

        \

    #.  initialize Ubuntu

        .. image:: WSL_initialize.png

        \

    #.  change the source of apt

        *   open file /etc/apt/sources.list with root privilege.
        *   replace the original contents with the following ones:

            ::

                deb http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
                deb http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
                deb http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
                deb http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
                deb http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
                deb-src http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
                deb-src http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
                deb-src http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
                deb-src http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
                deb-src http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse

            please replace the codename (bionic) of source with that of your system,
            which could be checked with the following command

            ::

                lsb_release -c

            \

        *   execute the following commands

            ::

                sudo apt-get update
                sudo apt-get -f install
                sudo apt-get upgrade

        \

    #.  change the source of pip

        *   create file ~/.pip/pip.conf
        *   add the following statements

            ::

                [global]
                index-url = https://mirrors.aliyun.com/pypi/simple

                [install]
                trusted-host=mirrors.aliyun.com

        \

    #.  install basic tools with the following commands

        ::

            sudo apt-get install cmake ffmpeg g++ gcc gitk make python3 python3-pip tree --fix-missing
            sudo pip3 install numpy sphinx


(20211026) Git (windows env)
----------------------------

    #.  install Git and TortoiseGit

        .. image:: Git_install1.png

        \

        .. image:: Git_install2.png

        \


(20211026) VS code (windows env)
--------------------------------

    #.  install VS code

        ..  image:: VSCode_install.png

        \

    #.  install some extensions

        *   Better Comments
        *   C/C++
        *   Chinese (Simplified) Language Pack for Visual Studio code
        *   Remote - WSL
        *   Git History
        *   Matlab
        *   Jupyter
        *   Python
        *   TCL
        *   Verilog-HDL/SystemVerilog/Bluespec SystemVerilog
        *   vscode-pdf
        *   ...

        \

    #.  change some settings

        *   enable "Indent Using Spaces"
        *   disable "C_Cpp: Code Folding" of C/C++ extension
        *   ...

        \


(20211026) Xming
----------------

    #.  install Xming

        .. image:: Xming_install.png

        \

    #.  set the global variable DISPLAY

        *   open ~/.bashrc with root privilege
        *   add the following statement to this file

            ::

                export DISPLAY=:0.0
