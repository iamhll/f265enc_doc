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