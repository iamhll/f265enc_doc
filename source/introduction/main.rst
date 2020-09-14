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

::

    /
    ├── build
    │   ├── linux
    │   └── windows
    ├── doc
    │   ├── doxygen
    │   ├── description
    │   └── performance
    ├── script
    │   ├── run
    │   │   ├── f265.xls
    │   │   ├── f265.cfg
    │   │   └── makefile
    │   ├── getInfo
    │   ├── getBdRate
    │   ├── getPsnr
    │   ├── showDiff
    │   ├── fitCst
    │   └── runListUpdate.sh
    └── src
        ├── sys
        │   └── cfg
        ├── common
        │   └── lcu
        ├── enc
        │   ├── enc_knl
        │   │   ├── enc_r_c
        │   │   ├── enc_fth
        │   │   ├── enc_rmd
        │   │   ├── enc_ime
        │   │   ├── enc_fme
        │   │   ├── enc_rdo
        │   │   ├── enc_ilf
        │   │   ├── enc_e_c
        │   │   ├── enc_knl.cpp
        │   │   └── enc_knl.hpp
        │   ├── enc_top.cpp
        │   └── CMakeLists.txt
        └── dec
            └── dec_knl
                └── dec_e_d


Macro-Definition List
---------------------

.. table::
    :align: left
    :widths: auto

    ======== =================== ===================================================
     Domain   Name                Description
    ======== =================== ===================================================
     TOP      NUMB_CHN            number of channels (1: y; 3: y u v)
     TOP      NUMB_MOD            number of intra modes (35)
     TOP      SIZE_FRA_MAX_X      maximum size of frame width (4096 now)
     TOP      SIZE_FRA_MAX_Y      maximum size of frame height (4096 now)
     TOP      SIZE_LCU            size of LCU (32 now)
     TOP      SIZE_T_U_MAX        maximum size of TU (32)
     TOP      SIZE_C_U_MIN        minimum size of CU (8)
     TOP      SIZE_REC_EXT        size of extended reconstruction data (derived)
     TOP      SIZE_FMV_EXT_X      horizontal size of extended fmv data (derived)
     TOP      SIZE_FMV_EXT_Y      vertical size extended fmv data (derived)
     TOP      SIZE_REF_EXT_MAX    maximum size of extended reference data (derived)
     TOP      DATA_SCL_CH         scaler of chroma channel (1: 4:4:4; 2: 4:2:0)
     TOP      LOG2_SIZE_LCU       log2 of SIZE_LCU (derived)
     TOP      LOG2_SIZE_C_U_MIN   log2 of SIZE_C_U_MIN (derived)
     TOP      LOG2(x)             log2 of x (derived)
     ...      ...                 ...
    ======== =================== ===================================================


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

    ================================== ===========================
     Directory                          Owner
    ================================== ===========================
     build/linux                        Huang Leilei
     build/windows                      Huang Leilei
     doc/                               ...
     script/                            Huang Leilei
     src/sys/                           Huang Leilei
     src/enc/enc_core/enc_fth/          Li Tingting
     src/enc/enc_core/enc_rmd/          Huang Leilei
     src/enc/enc_core/enc_ime/          Huang Leilei, Shi Chunxin
     src/enc/enc_core/enc_fme/          Huang Leilei, Shi Chunxin
     src/enc/enc_core/enc_rdo/          Huang Leilei, Liu Xun
     src/enc/enc_core/enc_ilf/          Liu Xun, Hou Bingjing
     src/enc/enc_core/enc_e_c/          Cai Yujie, Zou Yuliang
     src/enc/enc_core/enc_knl.(c|h)pp   Huang Leilei
     src/enc/enc_top.(c|h)pp            Huang Leilei
     src/common/                        Huang Leilei, Liu Chang
    ================================== ===========================


Task List
---------

gantt

.. image:: task.png

\

.. table:: **2020.09**
    :align: left
    :widths: auto

    ============= ======================================================== ================================================ =========================== ============== =====================
     Number        Task                                                     Start Point                                      Target Module               Owner          Status
    ============= ======================================================== ================================================ =========================== ============== =====================
     20200907-01   create base class and tidy up other whatever I noticed   tidyup/src/004/tidyUpWhatINoticed/master         src/enc/enc_knl/enc_rmd/    Huang Leilei   20200901 - 20200902
     20200907-01   create base class and tidy up other whatever I noticed   tidyup/src/004/tidyUpWhatINoticed/master         src/enc/enc_knl/enc_ime/    Huang Leilei   20200907 - 20200908
     20200907-01   create base class and tidy up other whatever I noticed   tidyup/src/004/tidyUpWhatINoticed/master         src/enc/enc_knl/enc_fme/    Huang Leilei   20200908 - 20200908
     20200907-01   create base class and tidy up other whatever I noticed   tidyup/src/004/tidyUpWhatINoticed/master         src/enc/enc_knl/enc_rdo/    Huang Leilei   20200908 - 20200909
     20200907-01   create base class and tidy up other whatever I noticed   tidyup/src/004/tidyUpWhatINoticed/master         src/enc/enc_knl/enc_knl/    Huang Leilei   20200909 - 20200909
     20200907-01   create base class and tidy up other whatever I noticed   tidyup/src/004/tidyUpWhatINoticed/master         src/common/lcu/             Huang Leilei   20200910 - 20200910
     20200914-01   continue of 20200907-01                                  tidyup/src/005/tailOfTidyUpWhatINoticed/master   src/common                  Liu Chang      \* not stated
     20200914-01   continue of 20200907-01                                  tidyup/src/005/tailOfTidyUpWhatINoticed/master   src/enc/enc_knl/enc_fth     Li Tingting    \* not stated
     20200914-01   continue of 20200907-01                                  tidyup/src/005/tailOfTidyUpWhatINoticed/master   src/enc/enc_knl/enc_ilf/    Hou Bingjing   \* not stated
     20200914-01   continue of 20200907-01                                  tidyup/src/005/tailOfTidyUpWhatINoticed/master   src/enc/enc_knl/enc_e_c/    Zou Yuliang    \* not stated
    ============= ======================================================== ================================================ =========================== ============== =====================

\

.. table:: **2020.08**
    :align: left
    :widths: auto

    ============= ================ ==================================================== =========================== ============== =====================
     Number        Task             Start Point                                          Target Module               Owner          Status
    ============= ================ ==================================================== =========================== ============== =====================
     20200803-01   restructure      tidyup/src/002/restructure/master                    src/enc/enc_core/enc_fth/   Li Tingting    20200804 - 20200805
     20200803-01   restructure      tidyup/src/002/restructure/master                    src/enc/enc_core/enc_rmd/   Huang Leilei   20200803 - 20200803
     20200803-01   restructure      tidyup/src/002/restructure/master                    src/enc/enc_core/enc_ime/   Shi Chunxin    20200806 - 20200810
     20200803-01   restructure      tidyup/src/002/restructure/master                    src/enc/enc_core/enc_fme/   Huang Leilei   20200805 - 20200806
     20200803-01   restructure      tidyup/src/002/restructure/master                    src/enc/enc_core/enc_rdo/   Huang Leilei   20200806 - 20200810
     20200803-01   restructure      tidyup/src/002/restructure/master                    src/enc/enc_core/enc_ilf/   Hou Bingjing   20200806 - 20200810
     20200803-01   restructure      tidyup/src/002/restructure/master                    src/enc/enc_core/enc_e_c/   Zou Yuliang    20200806 - 20200810
     20200811-01   optimize         tidyup/src/003/optimize/master                       src/enc/enc_core/enc_fth/   Li Tingting    20200811 - 20200813
     20200811-01   optimize         tidyup/src/003/optimize/master                       src/enc/enc_core/enc_ime/   Shi Chunxin    20200811 - 20200811
     20200811-01   optimize         tidyup/src/003/optimize/master                       src/enc/enc_core/enc_ilf/   Hou Bingjing   20200811 - 20200817
     20200811-01   optimize         tidyup/src/003/optimize/master                       src/enc/enc_core/enc_e_c/   Zou Yuliang    20200811 - 20200820
     20200814-01   add IinP logic   update/src/enc/enc_core/enc_ime/001/addIinP/master   src/enc/enc_core/enc_ime/   Huang Leilei   20200814 - 20200828
    ============= ================ ==================================================== =========================== ============== =====================

\

.. table:: **2020.07**
    :align: left
    :widths: auto

    ============= ============================================== =================================================== ======================================= =========================== ========================
     Number        Task                                           Start Point                                         Target Module                           Owner                       Status
    ============= ============================================== =================================================== ======================================= =========================== ========================
     20200713-01   relocate files according to new project tree   /                                                   /                                       Huang Leilei                20200713 - 20200714
     20200713-02   maintain                                       /                                                   build/                                  Huang Leilei, Shi Chunxin   20200713 - 20200714
     20200713-03   maintain                                       /                                                   script/                                 Huang Leilei                20200713 - 20200714
     20200713-04   tidy up macro-definitions                      /                                                   src/sys/                                Huang Leilei                \* Not Started
     20200713-05   tidy up configurations                         /                                                   src/sys/                                Huang Leilei, Shi Chunxin   20200715 - 20200716
     20200715-01   optimize cfg.cpp                               /                                                   src/sys/                                Huang Leilei                20200715 - 20200716
     20200717-01   update according to cfg_typ.hpp                tidyup/sys/cfg/000/restructure/global               src/sys/                                Huang Leilei                20200720 - 20200720
     20200717-01   update according to cfg_typ.hpp                tidyup/sys/cfg/000/restructure/global               src/sys/                                Shi Chunxin                 20200717 - 20200717
     20200717-01   update according to cfg_typ.hpp                tidyup/sys/cfg/000/restructure/global               src/sys/                                Hao Zhijian                 20200722 - 20200722
     20200717-01   update according to cfg_typ.hpp                tidyup/sys/cfg/000/restructure/global               src/sys/                                Li Tinging                  20200718 - 20200718
     20200718-01   perpare some instruction on version control    /                                                   /                                       Huang Leilei                20200718 - 20200719
     20200720-01   perpare cfg.pl                                 /                                                   src/sys/                                Huang Leilei                20200720 - 20200722
     20200722-01   extract the calculation of b-d rate            update/script/000/getBdRate/master                  script                                  Liu Chang                   20200722 - 20200804
     20200723-01   clean warnings                                 tidyup/src/000/cleanWarnings/master                 src/enc/enc_core/enc_fth/               Li Tingting                 20200727 - 20200727
     20200723-01   clean warnings                                 tidyup/src/000/cleanWarnings/master                 src/enc/enc_core/enc_rmd/               Huang Leilei                20200729 - 20200729
     20200723-01   clean warnings                                 tidyup/src/000/cleanWarnings/master                 src/enc/enc_core/enc_ime/               Shi Chunxin                 20200726 - 20200726
     20200723-01   clean warnings                                 tidyup/src/000/cleanWarnings/master                 src/enc/enc_core/enc_fme/               Huang Leilei                20200729 - 20200729
     20200723-01   clean warnings                                 tidyup/src/000/cleanWarnings/master                 src/enc/enc_core/enc_rdo/               Huang Leilei                20200729 - 20200729
     20200723-01   clean warnings                                 tidyup/src/000/cleanWarnings/master                 src/enc/enc_core/enc_ilf/               Hou Bingjing                20200727 - 20200729
     20200723-01   clean warnings                                 tidyup/src/000/cleanWarnings/master                 src/enc/enc_core/enc_e_c/               Zou Yuliang                 20200727 - 20200727
     20200723-01   clean warnings                                 tidyup/src/000/cleanWarnings/master                 src/enc/enc_core/enc_core_top.(c|h)pp   Huang Leilei                20200729 - 20200729
     20200723-01   clean warnings                                 tidyup/src/000/cleanWarnings/master                 src/enc/enc_top.(c|h)pp                 Huang Leilei                20200729 - 20200729
     20200723-01   clean warnings                                 tidyup/src/000/cleanWarnings/master                 src/common/                             Huang Leilei                20200729 - 20200729
     20200723-01   clean warnings                                 tidyup/src/000/cleanWarnings/master                 src/sys/                                Huang Leilei                20200729 - 20200729
     20200723-02   add R_C logic                                  update/src/enc/enc_core/enc_ime/000/addRc/master    src/enc/enc_core/enc_ime/               Hao Zhijian                 20200728 - 20200811
     20200730-01   list functions and members                     tidyup/src/001/listFuncAndMember/master             src/enc/enc_core/enc_fth/               Li Tingting                 \* Not Started
     20200730-01   list functions and members                     tidyup/src/001/listFuncAndMember/master             src/enc/enc_core/enc_rmd/               Huang Leilei                \* Not Started
     20200730-01   list functions and members                     tidyup/src/001/listFuncAndMember/master             src/enc/enc_core/enc_ime/               Shi Chunxin                 \* Not Started
     20200730-01   list functions and members                     tidyup/src/001/listFuncAndMember/master             src/enc/enc_core/enc_fme/               Huang Leilei                \* Not Started
     20200730-01   list functions and members                     tidyup/src/001/listFuncAndMember/master             src/enc/enc_core/enc_rdo/               Huang Leilei                \* Not Started
     20200730-01   list functions and members                     tidyup/src/001/listFuncAndMember/master             src/enc/enc_core/enc_ilf/               Hou Bingjing                \* 20200803 - 20200803
     20200730-01   list functions and members                     tidyup/src/001/listFuncAndMember/master             src/enc/enc_core/enc_e_c/               Zou Yuliang                 \* 20200803 - 20200803
    ============= ============================================== =================================================== ======================================= =========================== ========================

\
