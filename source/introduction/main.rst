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
        │   └── cfg
        ├── enc
        ├── dec
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
        └── common


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

    .. include:: cfg.rst


Owner
-----

.. table::
    :align: left
    :widths: auto

    ======================================= ===========================
     Directory                               Owner
    ======================================= ===========================
     build/linux                             Shi Chunxin
     build/windows                           Huang Leilei
     doc/                                    ...
     script/                                 Huang Leilei
     src/sys/                                Huang Leilei
     src/enc/enc_core/enc_r_c/               Hao Zhijian
     src/enc/enc_core/enc_fth/               Shi Chunxin, Li Tingting
     src/enc/enc_core/enc_rmd/               Huang Leilei
     src/enc/enc_core/enc_ime/               Huang Leilei, Shi Chunxin
     src/enc/enc_core/enc_fme/               Huang Leilei
     src/enc/enc_core/enc_rdo/               Huang Leilei, Liu Xun
     src/enc/enc_core/enc_ilf/               Liu Xun, Hou Bingjing
     src/enc/enc_core/enc_e_c/               Cai Yujie, Zou Yuliang
     src/enc/enc_core/enc_core_top.(c|h)pp   Huang Leilei
     src/enc/enc_top.(c|h)pp                 Huang Leilei
     src/common/                             Huang Leilei
    ======================================= ===========================


Task List
---------

.. table:: 2020.07
    :align: left
    :widths: auto

    ============= ======================================= =================================================== ============================================== =========================== ============================
     Number        Directory                               Tag                                                   Task                                           Owner                         Status
    ============= ======================================= =================================================== ============================================== =========================== ============================
     20200713-01   /                                       /                                                   relocate files according to new project tree   Huang Leilei                  20200713 -> 20200714
     20200713-02   build/                                  /                                                   maintain                                       Huang Leilei, Shi Chunxin     20200713 -> 20200714
     20200713-03   script/                                 /                                                   maintain                                       Huang Leilei                  20200713 -> 20200714
     20200713-04   src/sys/                                /                                                   tidy up macro-definitions                      Huang Leilei                **Not Started**
     20200713-05   src/sys/                                /                                                   tidy up configurations                         Huang Leilei, Shi Chunxin     20200715 -> 20200716
     20200715-01   src/sys/                                /                                                   optimize cfg.cpp                               Huang Leilei                  20200715 -> 20200716
     20200717-01   src/sys/                                /                                                   update according to cfg_typ.hpp                Huang Leilei                  20200720 -> 20200720
     20200717-02   src/sys/                                tidyup/sys/cfg/000/restructure/global               update according to cfg_typ.hpp                Shi Chunxin                   20200717 -> 20200717
     20200717-03   src/sys/                                tidyup/sys/cfg/000/restructure/global               update according to cfg_typ.hpp                Hao Zhijian                   20200722 -> 20200722
     20200717-04   src/sys/                                tidyup/sys/cfg/000/restructure/global               update according to cfg_typ.hpp                Li Tinging                    20200718 -> 20200718
     20200718-01   /                                       /                                                   perpare some instruction on version control    Huang Leilei                  20200718 -> 20200719
     20200720-01   src/sys/                                /                                                   perpare cfg.pl                                 Huang Leilei                  20200720 -> 20200722
     20200722-01   script                                  update/script/000/getBdRate/master                  extract the calculation of b-d rate            Liu Chang                     20200722 -> 20200804
     20200723-01   src/sys/                                tidyup/src/000/cleanWarnings/master                 clean warnings                                 Huang Leilei                  20200729 -> 20200729
     20200723-02   src/enc/enc_core/enc_r_c/               update/src/enc/enc_core/enc_r_c/000/create/master   clean warnings                                 Hao Zhijian                   20200728 -> **20200804**
     20200723-03   src/enc/enc_core/enc_fth/               tidyup/src/000/cleanWarnings/master                 clean warnings                                 Li Tingting                   20200727 -> 20200727
     20200723-04   src/enc/enc_core/enc_rmd/               tidyup/src/000/cleanWarnings/master                 clean warnings                                 Huang Leilei                  20200729 -> 20200729
     20200723-05   src/enc/enc_core/enc_ime/               tidyup/src/000/cleanWarnings/master                 clean warnings                                 Shi Chunxin                   20200726 -> 20200726
     20200723-06   src/enc/enc_core/enc_fme/               tidyup/src/000/cleanWarnings/master                 clean warnings                                 Huang Leilei                  20200729 -> 20200729
     20200723-07   src/enc/enc_core/enc_rdo/               tidyup/src/000/cleanWarnings/master                 clean warnings                                 Huang Leilei                  20200729 -> 20200729
     20200723-08   src/enc/enc_core/enc_ilf/               tidyup/src/000/cleanWarnings/master                 clean warnings                                 Hou Bingjing                  20200727 -> 20200729
     20200723-09   src/enc/enc_core/enc_e_c/               tidyup/src/000/cleanWarnings/master                 clean warnings                                 Zou Yuliang                   20200727 -> 20200727
     20200723-10   src/enc/enc_core/enc_core_top.(c|h)pp   tidyup/src/000/cleanWarnings/master                 clean warnings                                 Huang Leilei                  20200729 -> 20200729
     20200723-11   src/enc/enc_top.(c|h)pp                 tidyup/src/000/cleanWarnings/master                 clean warnings                                 Huang Leilei                  20200729 -> 20200729
     20200723-12   src/common/                             tidyup/src/000/cleanWarnings/master                 clean warnings                                 Huang Leilei                  20200729 -> 20200729
     20200730-01   src/enc/enc_core/enc_r_c/               tidyup/src/001/listFuncAndMember/master             list functions and members                     Hao Zhijian                 **Not Started**
     20200730-02   src/enc/enc_core/enc_fth/               tidyup/src/001/listFuncAndMember/master             list functions and members                     Li Tingting                 **Not Started**
     20200730-03   src/enc/enc_core/enc_rmd/               tidyup/src/001/listFuncAndMember/master             list functions and members                     Huang Leilei                **Not Started**
     20200730-04   src/enc/enc_core/enc_ime/               tidyup/src/001/listFuncAndMember/master             list functions and members                     Shi Chunxin                 **Not Started**
     20200730-05   src/enc/enc_core/enc_fme/               tidyup/src/001/listFuncAndMember/master             list functions and members                     Huang Leilei                **Not Started**
     20200730-06   src/enc/enc_core/enc_rdo/               tidyup/src/001/listFuncAndMember/master             list functions and members                     Liu Chang                   **Not Started**
     20200730-07   src/enc/enc_core/enc_ilf/               tidyup/src/001/listFuncAndMember/master             list functions and members                     Hou Bingjing                  20200803 -> **20200803**
     20200730-08   src/enc/enc_core/enc_e_c/               tidyup/src/001/listFuncAndMember/master             list functions and members                     Zou Yuliang                   20200803 -> **20200803**
    ============= ======================================= =================================================== ============================================== =========================== ============================

\

.. table:: 2020.08
    :align: left
    :widths: auto

    ============= =========================== =================================== ============= ============== ==============================
     Number        Directory                   Tag                                   Task          Owner            Status
    ============= =========================== =================================== ============= ============== ==============================
     20200803-01   src/enc/enc_core/enc_r_c/   tidyup/src/002/restructure/master   restructure   Hao Zhijian    **Not Started**
     20200803-02   src/enc/enc_core/enc_fth/   tidyup/src/002/restructure/master   restructure   Li Tingting      20200804 -> **20200805**
     20200803-03   src/enc/enc_core/enc_rmd/   tidyup/src/002/restructure/master   restructure   Huang Leilei     20200803 -> 20200803
     20200803-04   src/enc/enc_core/enc_ime/   tidyup/src/002/restructure/master   restructure   Shi Chunxin    **20200806 ->**
     20200803-05   src/enc/enc_core/enc_fme/   tidyup/src/002/restructure/master   restructure   Huang Leilei     20200805 -> 20200806
     20200803-06   src/enc/enc_core/enc_rdo/   tidyup/src/002/restructure/master   restructure   Liu Chang      **20200806 ->**
     20200803-07   src/enc/enc_core/enc_ilf/   tidyup/src/002/restructure/master   restructure   Hou Bingjing   **20200806 ->**
     20200803-08   src/enc/enc_core/enc_e_c/   tidyup/src/002/restructure/master   restructure   Zou Yuliang    **20200806 ->**
    ============= =========================== =================================== ============= ============== ==============================
