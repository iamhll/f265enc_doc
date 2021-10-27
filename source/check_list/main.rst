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

(20211026) Major Developments
-----------------------------

    .. table::
        :align: left
        :widths: auto

        +---------+-----------+---------------------------------------------+-----------------------------------------------------------------------------------------------------------+
        | Subject | Main Step | Sub Step                                    | Check List                                                                                                |
        +=========+===========+=============================================+===========================================================================================================+
        | manager | assign    | define tasks                                | manager must make tasks clear and as individual as possible                                               |
        |         |           +---------------------------------------------+-----------------------------------------------------------------------------------------------------------+
        |         |           | define start points                         | manager should create start points and push them to the remote                                            |
        |         |           +---------------------------------------------+-----------------------------------------------------------------------------------------------------------+
        |         |           | define target modules, due dates and owners | manager must make target modules, due dates and owners as clear as possible                               |
        +---------+-----------+---------------------------------------------+-----------------------------------------------------------------------------------------------------------+
        | owner   | execute   | create branch                               | | if multiple owners or modules are involved,                                                             |
        |         |           |                                             | |   owner should create a sub-branch named with start_point/owner/module                                  |
        |         |           |                                             | |   (for example, undergoing/update/src/000/cleanWarnings/HLL/RMD)                                        |
        |         |           |                                             | | else                                                                                                    |
        |         |           |                                             | |   owner could directly works on the start point                                                         |
        |         |           |                                             | |   (for example, undergoing/update/src/enc_core/enc_ime/000/addRc/master)                                |
        |         |           +---------------------------------------------+-----------------------------------------------------------------------------------------------------------+
        |         |           | edit                                        | | owner should divide his edits into atomic ones                                                          |
        |         |           |                                             | | owner should code according to the coding style and template                                            |
        |         |           +---------------------------------------------+-----------------------------------------------------------------------------------------------------------+
        |         |           | commit                                      | | **owner must avoid dos-format files**                                                                   |
        |         |           |                                             | |   **perform dos2unix to newly added files**                                                             |
        |         |           |                                             | | **owner must avoid compilation warnings**                                                               |
        |         |           |                                             | |   **cd ref/linux; ./run.sh**                                                                            |
        |         |           |                                             | | **owner must make sure the results have no changes, if the decision logic has not been changed:**       |
        |         |           |                                             | |   **cd ref/linux; ./run.sh**                                                                            |
        |         |           +---------------------------------------------+-----------------------------------------------------------------------------------------------------------+
        |         |           | push                                        | | **owner must make sure the results have no changes, if the decision logic has not been changed:**       |
        |         |           |                                             | |   **cd script/run; make run**                                                                           |
        |         |           |                                             | | **owner should note down the B-D rate log, if decision logic is optimized:**                            |
        |         |           |                                             | |   **modify script/run/xkcdc.sh and script/run/xkcdc.cfg according to your target settings**             |
        |         |           |                                             | |   **cd script/run; make run**                                                                           |
        |         |           +---------------------------------------------+-----------------------------------------------------------------------------------------------------------+
        |         |           | feedback                                    | | if one task is finished,                                                                                |
        |         |           |                                             | |   owner should notify the corresponding manager as quick as possible                                    |
        |         |           |                                             | | else                                                                                                    |
        |         |           |                                             | |   owner should report the percentage of completeness on daily meetings                                  |
        +---------+-----------+---------------------------------------------+-----------------------------------------------------------------------------------------------------------+
        | manager | verify    | check                                       | manager must rerun the generation of runs.log, results.log and bdRate.log                                 |
        |         |           +---------------------------------------------+-----------------------------------------------------------------------------------------------------------+
        |         |           | review                                      | | manager must check the differences with master and point out any violation noticed                      |
        |         |           |                                             | | violations include but not limited to                                                                   |
        |         |           |                                             | |   dos-format files and trailing blanks                                                                  |
        |         |           |                                             | |   improper logic like listing all situations instead of using for-loop                                  |
        |         |           |                                             | |   improper coding styles like improper naming, magic numbers                                            |
        |         |           +---------------------------------------------+-----------------------------------------------------------------------------------------------------------+
        |         |           | feedback                                    | | if another iteration is needed                                                                          |
        |         |           |                                             | |   manager must note down TODOs, push them to the remote and notify corresponding owners                 |
        |         |           |                                             | | else                                                                                                    |
        |         |           |                                             | |   manager must merge the branch to master by                                                            |
        |         |           |                                             | |     checking modifications including coding styles, function and performance                            |
        |         |           |                                             | |     checking file formats and trailing blanks                                                           |
        |         |           |                                             | |     minimizing differences with master                                                                  |
        |         |           |                                             | |     adding changing histories to the header of related files                                            |
        |         |           |                                             | |     checking single run results under linux env (warnings cleaned, log matched or b-d rate optimized)   |
        |         |           |                                             | |     checking single run results under windows env (log matched or b-d rate optimized)                   |
        |         |           |                                             | |     checking regression run results under linux env (log matched or b-d rate optimized)                 |
        |         |           |                                             | |     updating the version number and descriptions in enc_top.cpp                                         |
        |         |           |                                             | |     changing branch prefix from undergoing to merged                                                    |
        |         |           |                                             | |     making a "shortcut" commit on master, which involves all the changes                                |
        |         |           |                                             | |         md5sum of bin and yuv files should be added to the log if they are changed                      |
        |         |           |                                             | |     creating a tag if necessary                                                                         |
        |         |           |                                             | |     pushing master(, the newly-add tag) and the newly-merged branch                                     |
        |         |           |                                             | |     protecting the merged branch on git@code.aliyun.com:llhuang/f265enc_global.git                      |
        |         |           |                                             | |     rebasing and checking function patches                                                              |
        |         |           |                                             | |     fixing or asking related owners to fix any issues encountered                                       |
        |         |           |                                             | |     making a "patch" commmit on master, which involves all the fixes                                    |
        +---------+-----------+---------------------------------------------+-----------------------------------------------------------------------------------------------------------+
