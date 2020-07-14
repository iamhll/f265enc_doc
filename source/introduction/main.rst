.. -----------------------------------------------------------------------------
  ..
  ..  Filename       : main.rst
  ..  Author         : Huang Leilei
  ..  Created        : 2020-07-12
  ..  Description    : introduction related documents
  ..
.. -----------------------------------------------------------------------------

Introduction
============

Project Tree
------------

current tree
............

::

    branch/f265_4th_iteration
    ├── build
    │   ├── linux
    │   ├── macos
    │   └── win
    ├── config
    │   └── f265_encode.cfg
    ├── doc
    │   ├── description
    │   └── performance
    ├── run
    │   ├── compare.xls
    │   ├── makefile
    │   └── script
    └── src
        ├── CMakeLists.txt
        ├── bitstream
        ├── cabac
        ├── common.cpp
        ├── db_sao
        ├── fetch
        ├── fme
        ├── ime
        ├── include
        ├── main.cpp
        ├── param_config.cpp
        ├── post_intra
        ├── pre_intra
        ├── rate_control
        ├── rec_loop
        ├── sys_ctrl.cpp
        └── transform_quant


targeted tree
.............

::

    branch/f265_5th_iteration
    ├── build
    │   ├── linux
    │   ├── mac
    │   └── windows
    ├── doc
    │   ├── description
    │   └── performance
    ├── script
    │   ├── run
    │   │   ├── f265.xls
    │   │   ├── f265.cfg
    │   │   └── makefile
    │   ├── fitCst
    │   ├── getInfo
    │   ├── getPsnr
    │   ├── showDiff
    │   └── runListUpdate.sh
    └── src
        ├── sys
        ├── enc
        │   ├── enc_core
        │   │   ├── enc_r_c
        │   │   ├── enc_fth
        │   │   ├── enc_rmd
        │   │   ├── enc_ime
        │   │   ├── enc_fme
        │   │   ├── enc_rdo
        │   │   ├── enc_ilf
        │   │   ├── enc_e_c
        │   │   ├── enc_core_top.cpp
        │   │   └── enc_core_top.hpp
        │   ├── enc_top.cpp
        │   └── CMakeLists.txt
        ├── common
        └── dec

Owner
-----

.. table::
    :align: left
    :widths: auto

    ======================================= ===========================
     Directory                               Owner
    ======================================= ===========================
     build/linux                             Shi Chunxin
    --------------------------------------- ---------------------------
     build/mac                               ???
    --------------------------------------- ---------------------------
     build/windows                           Huang Leilei
    --------------------------------------- ---------------------------
     doc/                                    ...
    --------------------------------------- ---------------------------
     script/                                 Huang Leilei
    --------------------------------------- ---------------------------
     src/sys/                                Huang Leilei
    --------------------------------------- ---------------------------
     src/enc/enc_core/enc_r_c/               Hao Zhijian
    --------------------------------------- ---------------------------
     src/enc/enc_core/enc_fth/               Shi Chunxin, Li Tingting
    --------------------------------------- ---------------------------
     src/enc/enc_core/enc_rmd/               Huang Leilei
    --------------------------------------- ---------------------------
     src/enc/enc_core/enc_ime/               Huang Leilei, Shi Chunxin
    --------------------------------------- ---------------------------
     src/enc/enc_core/enc_fme/               Huang Leilei
    --------------------------------------- ---------------------------
     src/enc/enc_core/enc_rdo/               Huang Leilei, Liu Xun
    --------------------------------------- ---------------------------
     src/enc/enc_core/enc_ilf/               Liu Xun, Hou Bingjing
    --------------------------------------- ---------------------------
     src/enc/enc_core/enc_e_c/               Cai Yujie, Zou Yuliang
    --------------------------------------- ---------------------------
     src/enc/enc_core/enc_core_top.(c|h)pp   Huang Leilei
    --------------------------------------- ---------------------------
     src/enc/enc_top.(c|h)pp                 Huang Leilei
    --------------------------------------- ---------------------------
     src/common/                             Huang Leilei
    ======================================= ===========================

LiuChang ?


Macro-Definition List
---------------------

.. table::
    :align: left
    :widths: auto

    ======== ====== =============
     Domain   Name   Description
    ======== ====== =============
    ======== ====== =============


Parameter List
--------------

.. table::
    :align: left
    :widths: auto

    ======== ====== ============= =============== ===============
     Domain   Name   Description   Allowed Value   Default Value
    ======== ====== ============= =============== ===============
    ======== ====== ============= =============== ===============


Task List
---------

.. table::
    :align: left
    :widths: auto

    ============= =========== ============================================== =========================== ============================
     Number        Directory   Task                                           Owner                       Status
    ============= =========== ============================================== =========================== ============================
     20200713-01   /           relocate files according to new project tree   Huang Leilei                Done @ 20200714
     20200713-02   build/      maintain                                       Huang Leilei, Shi Chunxin   Done @ 20200714
     20200713-03   script/     maintain                                       Huang Leilei                Done @ 20200714
     20200713-04   src/sys/    tidy up macro-definitions                      Huang Leilei                **Undergoing @ 20200714**
     20200713-05   src/sys/    tidy up parameters                             Huang Leilei, Shi Chunxin   **Undergoing @ 20200714**
    ============= =========== ============================================== =========================== ============================
