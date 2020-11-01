.. -----------------------------------------------------------------------------
    ..
    ..  Filename       : main.rst
    ..  Author         : Huang Leilei
    ..  Created        : 2020-09-11
    ..  Description    : check list related documents
    ..
.. -----------------------------------------------------------------------------

Check List
==========

(20200917) Major Developments
-----------------------------

    .. table::
        :align: left
        :widths: auto
    
        +---------+-----------+---------------------------------------------+-----------------------------------------------------------------------------------------------------+
        | Subject | Main Step | Sub Step                                    | Check List                                                                                          |
        +=========+===========+=============================================+=====================================================================================================+
        | manager | assign    | define tasks                                | manager must make tasks clear and as individual as possible                                         |
        |         |           +---------------------------------------------+-----------------------------------------------------------------------------------------------------+
        |         |           | define start points                         | manager should creat start points and push them to the remote                                       |
        |         |           +---------------------------------------------+-----------------------------------------------------------------------------------------------------+
        |         |           | define target modules, due dates and owners | manager must make target modules, due dates and owners clear and release them with Gantt chart      |
        +---------+-----------+---------------------------------------------+-----------------------------------------------------------------------------------------------------+
        | owner   | execute   | create branch                               | | if multiple owners or modules are involved,                                                       |
        |         |           |                                             | |   owner should create a sub-branch named with start_point/owner/module                            |
        |         |           |                                             | |   (for example, undergoing/update/src/000/cleanWarnings/HLL/rmd)                                  |
        |         |           |                                             | | else                                                                                              |
        |         |           |                                             | |   owner could directly works on the start point                                                   |
        |         |           |                                             | |   (for example, undergoing/update/src/enc_core/enc_ime/000/addRc/master)                          |
        |         |           +---------------------------------------------+-----------------------------------------------------------------------------------------------------+
        |         |           | edit                                        | | owner should divide his edits into atomic ones                                                    |
        |         |           |                                             | | owner should code according to the coding style and template                                      |
        |         |           +---------------------------------------------+-----------------------------------------------------------------------------------------------------+
        |         |           | commit                                      | | **owner must avoid dos-format files:**                                                            |
        |         |           |                                             | |   **cd script; ./runListUpdate.sh**                                                               |
        |         |           |                                             | | owner should avoid warnings:                                                                      |
        |         |           |                                             | |   cd ref/linux; ./build; make                                                                     |
        |         |           |                                             | | **if decision logic keeps the same, owner must make sure the results also keep the same:**        |
        |         |           |                                             | |   **cd ref/linux; ./build; make; ./f265 -c ../../script/run/f265.cfg**                            |
        |         |           +---------------------------------------------+-----------------------------------------------------------------------------------------------------+
        |         |           | push                                        | | **if decision logic keeps the same, owner must make sure the results also keep the same:**        |
        |         |           |                                             | |   **cd script/run; make run; diff runs.log sessionTest/runs.log**                                 |
        |         |           |                                             | | if decision logic is optimized, owner should note down the B-D rate log:                          |
        |         |           |                                             | |   modify the SIZE_GOP in script/run/f265.sh according to your target frame type                   |
        |         |           |                                             | |   cd script/run; make run; cp sessionTest/bdRate.log ../../doc/performance/bdRate.log             |
        |         |           +---------------------------------------------+-----------------------------------------------------------------------------------------------------+
        |         |           | feedback                                    | | if one task is finished,                                                                          |
        |         |           |                                             | |   owner should notify the corresponding manager as quick as possible                              |
        |         |           |                                             | | else                                                                                              |
        |         |           |                                             | |   owner should report the percentage of completeness on daily meetings                            |
        +---------+-----------+---------------------------------------------+-----------------------------------------------------------------------------------------------------+
        | manager | verify    | check                                       | manager must rerun the generation of runs.log and bdRate.log                                        |
        |         |           +---------------------------------------------+-----------------------------------------------------------------------------------------------------+
        |         |           | review                                      | | manager must check the differences with master and point out any violation noticed                |
        |         |           |                                             | | violations include but not limited to                                                             |
        |         |           |                                             | |   dos-format files and tailing blanks                                                             |
        |         |           |                                             | |   improper logic like listing all situations instead of using for-loop                            |
        |         |           |                                             | |   improper coding styles like improper naming, magic numbers                                      |
        |         |           +---------------------------------------------+-----------------------------------------------------------------------------------------------------+
        |         |           | feedback                                    | | if another iteration is needed                                                                    |
        |         |           |                                             | |   manager must note down TODOs, push them to the remote and notify corresponding owners           |
        |         |           |                                             | | else                                                                                              |
        |         |           |                                             | |   manager must merge the branch to master by                                                      |
        |         |           |                                             | |   (G) copying the branch from global tree to local tree                                           |
        |         |           |                                             | |   (L) minimizing differences with master                                                          |
        |         |           |                                             | |   (L) doing more checks with local scripts, **which is missing for f265enc**                      |
        |         |           |                                             | |   (L) updating the version number and descriptions in enc_top.cpp                                 |
        |         |           |                                             | |   (L) modifying branch prefix from undergoing to merged                                           |
        |         |           |                                             | |   (L) making a shortcut from master to branch and create a tag                                    |
        |         |           |                                             | |   (L) pushing master, the newly-add tag and the newly-merged branch to orgin, aliyun and github   |
        |         |           |                                             | |   (L) copying the branch from local tree back to global tree                                      |
        |         |           |                                             | |   (G) making a shortcut from master to branch and create a tag                                    |
        |         |           |                                             | |   (G) pushing master, the newly-add tag and the newly-merged branch to aliyun                     |
        |         |           |                                             | |   (G) protecting the merged branch on git@code.aliyun.com:llhuang/f265enc_global.git              |
        |         |           |                                             | |   (S) notify all developers about the change on master                                            |
        |         |           |                                             | | (G for global, L for local, S for system)                                                         |
        +---------+-----------+---------------------------------------------+-----------------------------------------------------------------------------------------------------+

    \


(20201101) Item Status
----------------------

.. table::
    :align: left
    :widths: auto

    ================================== =============================
     Items                              Status
    ================================== =============================
     /build/linux/*                     reset on 2020.11.01
     /build/windows/*                   **to be fixed**
     \-
     /doc/description/RMD*              **to be updated**
     /doc/description/IME*              **to be updated**
     /doc/description/FME*              **to be updated**
     /doc/description/RDO*              **to be updated**
     /doc/description/ILF*              **to be updated**
     /doc/description/E_C*              **to be updated**
     /doc/description/E_D*              **to be updated**
     /doc/description/RFC*              **to be updated**
     \-
     /script/fitCst/*                   **to be maintained**
     /script/getBdRate/*                reset on 2020.11.01
     /script/getInfo/*                  reset on 2020.11.01
     /script/getPsnr/*                  reset on 2020.11.01
     /script/run/*                      reset on 2020.11.01
     /script/runChipsMedia/*            reset on 2020.11.01
     /script/runHM/*                    reset on 2020.11.01
     /script/runVeriSilicon/*           **to be maintained**
     /script/runX265/*                  reset on 2020.11.01
     /script/showDiff/*                 reset on 2020.11.01
     \-
     /src/common/common*                reset on 2020.11.01
     /src/common/lcu/*                  reset on 2020.11.01
     /src/common/rfc/*                  reset on 2020.11.01
     /src/sys/cfg/*                     reset on 2020.11.01
     /src/sys/fbs/*                     **to be tidied up**
     /src/sys/defines_enc.hpp           reset on 2020.11.01
     /src/sys/types_enc.hpp             reset on 2020.11.01
     /src/enc/enc_top.cpp               reset on 2020.11.01
     /src/enc/enc_knl/enc_fth/*         reset on 2020.11.01
     /src/enc/enc_knl/enc_rmd/*         reset on 2020.11.01
     /src/enc/enc_knl/enc_ime/*         reset on 2020.11.01
     /src/enc/enc_knl/enc_fme/*         reset on 2020.11.01
     /src/enc/enc_knl/enc_rdo/*         reset on 2020.11.01
     /src/enc/enc_knl/enc_rec/*         reset on 2020.11.01
     /src/enc/enc_knl/enc_ilf/*         **to be further tidied up**
     /src/enc/enc_knl/enc_e_c/*         **to be further tidied up**
     /src/enc/enc_knl/enc_dmp/*         reset on 2020.11.01
     /src/enc/enc_knl/enc_knl*          reset on 2020.11.01
     /src/dec/dec_knl/dec_e_d/*         **to be integrated**
    ================================== =============================

(20201014) Performance Status
-----------------------------

    |   X265 environment: http://www.openasic.org:8080/svn/f265enc/x265/reference/x265_3.0
    |   Chips&Media environment: http://viplab.fudan.edu.cn/vip/boards/1/topics/35464
    |   VeriSilicon environment: http://viplab.fudan.edu.cn/vip/boards/1/topics/35463
    |   (which will be move to git)
    |   Distance between LCU size 32 and 64 is about 10%
    |   Distance between with and without IinP is about 5%
    |   Distance between with and without Skip&Merge is about 5%
    |   Distance between with and without Nx2N parition is about 5%


Hardware Version
................

    .. table:: **Intra B-D Rate of F265 vs Chips&Media**
        :align: left
        :widths: auto

        ================== ======== ========= ========= ========== ======== ========= ========= ============ ======== ========= ========= ==========
         Version            min(Y)   min(U)    min(V)    min(YUV)   ave(Y)   ave(U)    ave(V)    ave(YUV)     max(Y)   max(U)    max(V)    max(YUV)
        ================== ======== ========= ========= ========== ======== ========= ========= ============ ======== ========= ========= ==========
         syn/20200918 + 2   -3.286   -13.064   -13.169   -5.301     -0.646   -8.855    -9.330      -3.462     1.650    -5.895    -5.322    -0.841
         syn/20200923       -3.286   -13.064   -13.169   -5.301     -0.646   -8.855    -9.330    **-3.462**   1.650    -5.895    -5.322    -0.841
        ================== ======== ========= ========= ========== ======== ========= ========= ============ ======== ========= ========= ==========

    \

    .. table:: **Inter B-D Rate of F265 vs Chips&Media**
        :align: left
        :widths: auto

        ================== ========= ========= ========= ========== ======== ========= ========= =========== ======== ========= ========= ==========
         Version            min(Y)    min(U)    min(V)    min(YUV)   ave(Y)   ave(U)    ave(V)    ave(YUV)    max(Y)   max(U)    max(V)    max(YUV)
        ================== ========= ========= ========= ========== ======== ========= ========= =========== ======== ========= ========= ==========
         syn/20200918 + 2   -12.729    -0.013    -5.517    0.358      6.632   100.576   106.665    38.962     27.441   638.160   641.332   148.273
         syn/20200923        -8.530   -18.849   -20.409   -4.447     11.589     0.894     0.657   **7.985**   31.068    33.130    35.797    26.054
        ================== ========= ========= ========= ========== ======== ========= ========= =========== ======== ========= ========= ==========

    |   Anchor is Chips&Media with LCU size **64**, **with** IinP, Merge&Skip and 2Nx1N
    |   Tester is F265 (hardware version) with LCU size **32**, **without** IinP, Merge&Skip and 2Nx1N

    \

Best Performance Verision
.........................

    .. table:: **Inter B-D Rate of F265 vs X265**
        :align: left
        :widths: auto

        +---------------------------+-----------------------------------------+-----------------------------------------+
        | Feature                   | LCU Size 32                             | LCU Size 64                             |
        +======+============+=======+========+========+========+==============+========+========+========+==============+
        | IinP | Merge&Skip | 2Nx1N | min(Y) | min(U) | min(V) |   min(YUV)   | min(Y) | min(U) | min(V) |   min(YUV)   |
        |      |            |       +--------+--------+--------+--------------+--------+--------+--------+--------------+
        |      |            |       | ave(Y) | ave(U) | ave(V) | **ave(YUV)** | ave(Y) | ave(U) | ave(V) | **ave(YUV)** |
        |      |            |       +--------+--------+--------+--------------+--------+--------+--------+--------------+
        |      |            |       | max(Y) | max(U) | max(V) |   max(YUV)   | max(Y) | max(U) | max(V) |   max(YUV)   |
        +------+------------+-------+--------+--------+--------+--------------+--------+--------+--------+--------------+
        | N    | N          | N     |  -9.59 | -34.61 | -33.27 |     -13.15   | -5.77  | -29.94 | -29.54 |     -10.03   |
        |      |            |       +--------+--------+--------+--------------+--------+--------+--------+--------------+
        |      |            |       |  -4.50 | -20.73 | -20.51 |    **-9.88** |  2.31  | -12.01 | -11.24 |    **-2.34** |
        |      |            |       +--------+--------+--------+--------------+--------+--------+--------+--------------+
        |      |            |       |   0.12 |  -9.70 |  -9.77 |      -5.65   |  12.67 |   3.66 |   2.07 |       6.19   |
        +------+------------+-------+--------+--------+--------+--------------+--------+--------+--------+--------------+
        | N    | N          | Y     |  -9.28 | -30.37 | -29.54 |     -12.25   |  -0.73 | -25.68 | -23.51 |      -5.78   |
        |      |            |       +--------+--------+--------+--------------+--------+--------+--------+--------------+
        |      |            |       |  -0.55 | -16.22 | -15.85 |    **-5.71** |   6.97 |  -6.71 |  -6.02 |     **2.52** |
        |      |            |       +--------+--------+--------+--------------+--------+--------+--------+--------------+
        |      |            |       |   6.73 |  -5.10 |  -5.15 |       2.78   |  15.22 |   5.88 |   4.48 |       9.76   |
        +------+------------+-------+--------+--------+--------+--------------+--------+--------+--------+--------------+
        | N    | Y          | N     |  -3.99 | -34.01 | -32.35 |     -10.97   |  -1.10 | -29.38 | -28.22 |      -8.04   |
        |      |            |       +--------+--------+--------+--------------+--------+--------+--------+--------------+
        |      |            |       |   0.65 | -17.23 | -16.70 |    **-5.23** |   7.55 |  -8.45 |  -7.47 |     **2.38** |
        |      |            |       +--------+--------+--------+--------------+--------+--------+--------+--------------+
        |      |            |       |   5.41 |  -5.14 |  -5.36 |      -0.64   |  20.89 |   7.37 |   6.23 |      12.88   |
        +------+------------+-------+--------+--------+--------+--------------+--------+--------+--------+--------------+
        | N    | Y          | Y     |  -1.34 | -30.49 | -28.41 |      -7.72   |   4.74 | -25.77 | -24.81 |      -3.35   |
        |      |            |       +--------+--------+--------+--------------+--------+--------+--------+--------------+
        |      |            |       |   5.48 | -13.15 | -12.63 |    **-0.64** |  12.75 |  -3.97 |  -3.00 |     **7.34** |
        |      |            |       +--------+--------+--------+--------------+--------+--------+--------+--------------+
        |      |            |       |  12.74 |  -1.33 |  -0.58 |       8.17   |  24.12 |   9.19 |   8.01 |      16.43   |
        +------+------------+-------+--------+--------+--------+--------------+--------+--------+--------+--------------+
        | Y    | N          | N     |  -4.68 | -34.03 | -33.16 |     -13.07   |  -0.45 | -29.71 | -29.20 |      -9.83   |
        |      |            |       +--------+--------+--------+--------------+--------+--------+--------+--------------+
        |      |            |       |   0.42 | -14.01 | -13.52 |    **-4.31** |   7.52 |  -5.25 |  -4.21 |     **3.44** |
        |      |            |       +--------+--------+--------+--------------+--------+--------+--------+--------------+
        |      |            |       |  11.40 |  10.92 |  14.13 |      11.78   |  21.45 |  29.26 |  31.40 |      24.41   |
        +------+------------+-------+--------+--------+--------+--------------+--------+--------+--------+--------------+
        | Y    | N          | Y     |  -4.03 | -30.34 | -28.86 |     -11.83   |   4.04 | -25.63 | -23.85 |      -5.32   |
        |      |            |       +--------+--------+--------+--------------+--------+--------+--------+--------------+
        |      |            |       |   3.62 | -10.76 | -10.11 |    **-1.06** |  11.18 |  -1.41 |  -0.23 |     **7.18** |
        |      |            |       +--------+--------+--------+--------------+--------+--------+--------+--------------+
        |      |            |       |  11.25 |  12.12 |  14.27 |      11.90   |  21.56 |  30.82 |  32.98 |      25.01   |
        +------+------------+-------+--------+--------+--------+--------------+--------+--------+--------+--------------+
        | Y    | Y          | N     |  -1.23 | -33.15 | -32.39 |     -11.32   |   1.86 | -28.91 | -28.00 |     -7.94    |
        |      |            |       +--------+--------+--------+--------------+--------+--------+--------+--------------+
        |      |            |       |   4.74 | -11.29 | -10.40 |    **-0.45** |  11.86 |  -2.56 |  -1.18 |    **7.28**  |
        |      |            |       +--------+--------+--------+--------------+--------+--------+--------+--------------+
        |      |            |       |  15.72 |  16.28 |  19.24 |      16.40   |  25.88 |  33.34 |  35.66 |     28.75    |
        +------+------------+-------+--------+--------+--------+--------------+--------+--------+--------+--------------+
        | Y    | Y          | Y     |   2.59 | -30.37 | -28.14 |      -7.22   |   7.90 | -25.52 | -24.88 |     -2.79    |
        |      |            |       +--------+--------+--------+--------------+--------+--------+--------+--------------+
        |      |            |       |   8.89 |  -8.21 |  -7.50 |     **3.31** |  16.36 |   0.90 |  2.12  |   **11.41**  |
        |      |            |       +--------+--------+--------+--------------+--------+--------+--------+--------------+
        |      |            |       |  16.06 |  17.31 |  20.00 |      16.92   |  26.51 |  34.77 |  37.25 |     29.67    |
        +------+------------+-------+--------+--------+--------+--------------+--------+--------+--------+--------------+

    |   Anchor is X265 with LCU size **32 or 64**, **with or without** IinP, Merge&Skip and 2Nx1N
    |   Tester is F265 (best performance version) with LCU size **32**, **without** IinP, Merge&Skip and 2Nx1N

    .. table:: **Intra B-D Rate of F265 vs Chips&Media**
        :align: left
        :widths: auto

        ============================== ========= ========= ========= ========== ======== ========= ========= ============ ======== ========= ========= ==========
         Version                        min(Y)    min(U)    min(V)    min(YUV)   ave(Y)   ave(U)    ave(V)    ave(YUV)     max(Y)   max(U)    max(V)    max(YUV)
        ============================== ========= ========= ========= ========== ======== ========= ========= ============ ======== ========= ========= ==========
         ckp/bestPerformance/20200923   -5.851    -10.750   -11.636   -6.881     -3.750   -8.003    -8.391    **-5.232**   0.260    -5.184    -4.702    -1.474
        ============================== ========= ========= ========= ========== ======== ========= ========= ============ ======== ========= ========= ==========

    \

    .. table:: **Inter B-D Rate of F265 vs Chips&Media**
        :align: left
        :widths: auto

        ============================== ========= ========= ========= ========== ======== ========= ========= ============ ======== ========= ========= ==========
         Version                        min(Y)    min(U)    min(V)    min(YUV)   ave(Y)   ave(U)    ave(V)    ave(YUV)     max(Y)   max(U)    max(V)    max(YUV)
        ============================== ========= ========= ========= ========== ======== ========= ========= ============ ======== ========= ========= ==========
         ckp/bestPerformance/20200923   -21.170   -20.172   -15.505   -12.761    2.242    -1.675    -2.504    **0.798**    17.624   13.639    10.475    11.909
        ============================== ========= ========= ========= ========== ======== ========= ========= ============ ======== ========= ========= ==========

    |   Anchor is Chips&Media with LCU size **64**, **with** IinP, Merge&Skip and 2Nx1N
    |   Tester is F265 (best performance) with LCU size **32**, **without** IinP, Merge&Skip and 2Nx1N

Performance Reference
.....................

    .. table:: **Inter B-D Rate of X265 vs X265**
        :align: left
        :widths: auto

        +-----------------------------------------+--------------------------------------+--------------------------------------+-----------------------------------+--------------------------------------+
        | feature                                 | with LCU Size 64                     |     with IinP                        | with Merge&Skip                   | with 2NxN                            |
        +========+========+========+==============+========+========+========+===========+========+========+========+===========+=======+=======+=======+===========+========+========+========+===========+
        | min(Y) | min(U) | min(V) |   min(YUV)   | -15.41 | -21.65 | -25.34 |  -18.10   | -18.89 | -27.21 | -29.70 |  -22.08   | -8.42 | -8.90 | -9.12 |   -8.33   | -10.04 | -9.71  | -10.53 |  -10.07   |
        +--------+--------+--------+--------------+--------+--------+--------+-----------+--------+--------+--------+-----------+-------+-------+-------+-----------+--------+--------+--------+-----------+
        | ave(Y) | ave(U) | ave(V) | **ave(YUV)** |  -6.46 |  -9.92 | -10.53 | **-7.72** |  -4.78 |  -7.13 |  -7.31 | **-5.60** | -5.09 | -4.45 | -4.78 | **-4.93** |  -3.88 | -5.16  |  -5.24 | **-4.32** |
        +--------+--------+--------+--------------+--------+--------+--------+-----------+--------+--------+--------+-----------+-------+-------+-------+-----------+--------+--------+--------+-----------+
        | max(Y) | max(U) | max(V) |   max(YUV)   |  -1.93 |  -3.37 |  -3.67 |   -2.69   |  -0.08 |   0.10 |  -0.25 |   -0.08   | -2.39 | -1.30 | -1.49 |   -2.33   |   1.91 | -1.48  |  -1.02 |    0.68   |
        +--------+--------+--------+--------------+--------+--------+--------+-----------+--------+--------+--------+-----------+-------+-------+-------+-----------+--------+--------+--------+-----------+


    |   Anchor is X265 with LCU Size **32**, **without** IinP, Merge&Skip and 2Nx1N
    |   Tester is X265 Anchor + feature
