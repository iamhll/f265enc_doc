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


(20200923) Performance Status
-----------------------------

    |   anchor is Chips&Media with default settings: LCU size 64, with IinP, with Skip&Merge, with Nx2N partition
    |   dut is f265 with current settings: LCU size 32, without IinP, without Skip&Merge, without Nx2N parition
    |   distance between LCU size 32 and 64 is about 10%
    |   distance between with and without IinP is about 5%
    |   distance between with and without Skip&Merge is about 5%
    |   distance between with and without Nx2N parition is about 5%

    |   x265 environment: http://www.openasic.org:8080/svn/f265enc/x265/reference/x265_3.0
    |   chips&media environment: http://viplab.fudan.edu.cn/vip/boards/1/topics/35464
    |   verisilicon environment: http://viplab.fudan.edu.cn/vip/boards/1/topics/35463
    |   i will move them to git depository in 10.1~10.7

Hardware Synchronized
.....................

    .. table:: **B-D Rate of Intra**
        :align: left
        :widths: auto

        ================== ========= ========= ========= ========== ======== ========= ========= ============ ======== ========= ========= ==========
         Version            min(Y)    min(U)    min(V)    min(YUV)   ave(Y)   ave(U)    ave(V)    ave(YUV)     max(Y)   max(U)    max(V)    max(YUV)
        ================== ========= ========= ========= ========== ======== ========= ========= ============ ======== ========= ========= ==========
         syn/20200918 + 2   -3.286    -13.064   -13.169   -5.301     -0.646   -8.855    -9.330    **-3.462**   1.650    -5.895    -5.322    -0.841
        ================== ========= ========= ========= ========== ======== ========= ========= ============ ======== ========= ========= ==========

    \

    .. table:: **B-D Rate of Inter**
        :align: left
        :widths: auto

        ================== ========= ========= ========= ========== ======== ========= ========= ============ ======== ========= ========= ==========
         Version            min(Y)    min(U)    min(V)    min(YUV)   ave(Y)   ave(U)    ave(V)    ave(YUV)     max(Y)   max(U)    max(V)    max(YUV)
        ================== ========= ========= ========= ========== ======== ========= ========= ============ ======== ========= ========= ==========
         syn/20200918 + 2   -12.729   -0.013    -5.517    0.358      6.632    100.576   106.665   **38.962**   27.441   638.160   641.332   148.273
         syn/20200923       -8.530    -18.849   -20.409   -4.447     11.589   0.894     0.657     **7.985**    31.068   33.130    35.797    26.054
        ================== ========= ========= ========= ========== ======== ========= ========= ============ ======== ========= ========= ==========

    \

Best Performance
................

    .. table:: **B-D Rate of Intra**
        :align: left
        :widths: auto

        ===================== ========= ========= ========= ========== ======== ========= ========= ============ ======== ========= ========= ==========
         Version               min(Y)    min(U)    min(V)    min(YUV)   ave(Y)   ave(U)    ave(V)    ave(YUV)     max(Y)   max(U)    max(V)    max(YUV)
        ===================== ========= ========= ========= ========== ======== ========= ========= ============ ======== ========= ========= ==========
         ckp/bestPerformance   -5.851    -10.750   -11.636   -6.881     -3.750   -8.003    -8.391    **-5.232**   0.260    -5.184    -4.702    -1.474
        ===================== ========= ========= ========= ========== ======== ========= ========= ============ ======== ========= ========= ==========

    \

    .. table:: **B-D Rate of Inter**
        :align: left
        :widths: auto

        ===================== ========= ========= ========= ========== ======== ========= ========= ============ ======== ========= ========= ==========
         Version               min(Y)    min(U)    min(V)    min(YUV)   ave(Y)   ave(U)    ave(V)    ave(YUV)     max(Y)   max(U)    max(V)    max(YUV)
        ===================== ========= ========= ========= ========== ======== ========= ========= ============ ======== ========= ========= ==========
         ckp/bestPerformance   -21.170   -20.172   -15.505   -12.761    2.242    -1.675    -2.504    **0.798**    17.624   13.639    10.475    11.909
        ===================== ========= ========= ========= ========== ======== ========= ========= ============ ======== ========= ========= ==========
