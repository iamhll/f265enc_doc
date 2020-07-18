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

    ======== =========== ============= =========== ====== ======================= ======================= ===============
     Domain   Name(Key)   Description   Short Key   Type   Minimum Allowed Value   Maximum Allowed Value   Default Value
    ======== =========== ============= =========== ====== ======================= ======================= ===============
    ======== =========== ============= =========== ====== ======================= ======================= ===============


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

.. table::
    :align: left
    :widths: auto

    ============= =========== ============================================== =========================== ==========================
     Number        Directory   Task                                           Owner                       Status
    ============= =========== ============================================== =========================== ==========================
     20200713-01   /           relocate files according to new project tree   Huang Leilei                20200713 -> 20200714
     20200713-02   build/      maintain                                       Huang Leilei, Shi Chunxin   20200713 -> 20200714
     20200713-03   script/     maintain                                       Huang Leilei                20200713 -> 20200714
     20200713-04   src/sys/    tidy up macro-definitions                      Huang Leilei                **Not Started**
     20200713-05   src/sys/    tidy up configurations                         Huang Leilei, Shi Chunxin   20200715 -> 20200716
     20200715-01   src/sys/    optimize cfg.cpp                               Huang Leilei                20200715 -> 20200716
     20200717-01   src/sys/    update according to cfg_typ.hpp                Huang Leilei                **Not Started**
     20200717-02   src/sys/    update according to cfg_typ.hpp                Shi Chunxin                 20200717 -> 20200717
     20200717-03   src/sys/    update according to cfg_typ.hpp                Hao Zhijian                 **Not Started**
     20200717-04   src/sys/    update according to cfg_typ.hpp                Li Tinging                  **Not Started**
     20200718-01               perpare some instruction on version control    Huang Leilei                20200718 -> 20200719
     20200720-01   src/sys/    perpare cfg.pl                                 Huang Leilei                **Not Started**
    ============= =========== ============================================== =========================== ==========================
