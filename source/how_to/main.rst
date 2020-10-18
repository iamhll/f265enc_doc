.. -----------------------------------------------------------------------------
    ..
    ..  Filename       : main.rst
    ..  Author         : Huang Leilei
    ..  Created        : 2020-09-11
    ..  Description    : how-to related documents
    ..
.. -----------------------------------------------------------------------------

How-To
======

(20200922) How to Diff with an Arbitary Commitment
--------------------------------------------------

    #.  use diff

        ::

            git diff "SHA1 ID of the commitment you want to diff with"

        \

    #.  use reset

        ::

            "commit your changes if necessary"
            git reset "SHA1 ID of the commitment you want to diff with"
            "make some edit"
            git reset "SHA1 ID of the commitment you were working with"

        \


(20200924) How to Get a Simple History
--------------------------------------

    #.  |   press F4 after "gitk --all" is executed
        |   (or click "View" and choose "Edit wiew..." after gitk --all is executed)
        |   click "Simple history"

        .. image:: howToGetASimpleHistory_edit.png

        \

    #.  click "ok"

        .. image:: howToGetASimpleHistory_okay.png

        \

    #.  "gitk --all --simplify-by-decoration" works as well


(20200917) How to Rename
------------------------

    #.  |   put cursor on the variable or function to be renamed and press F2
        |   (or right click the variable or function to be renamed and choose rename)
        |   enter a new name and press "enter"

        .. image:: howToRenameVariables_F2.png

        \

    #.  confirm the list and apply

        .. image:: howToRenameVariables_apply.png

        \

    #.  do not forget to save changes

        .. image:: howToRenameVariables_save.png

        \


(20200917) How to Revert Partially
----------------------------------

    #.  open the "diff"

        .. image:: howToRevertChangePartially_openDiff.png

        \

    #.  right click the changes to be revereted and choose "revert the selected changes"

        .. image:: howToRevertChangePartially_revert.png

        \

    #.  do not forget to save changes

        .. image:: howToRevertChangePartially_save.png

        \


(20200923) How to Synchronize with the Remote
---------------------------------------------

    #.  fetch and prune

        ::

            git fetch --all
            git remote prune origin

        \

    #.  checkout

        ::

            git checkout "the branch you want to synchronize"

        \

    #.  if the remote is right

        ::

            git reset --hard origin/"the branch you want to synchronize"

        \

    #.  if your local is right

        ::

            git push -f [origin "the branch you want to synchronize"]

        \

    #.  if both the remote and your local are right

        ::

            git pull --rebase [origin "the branch you want to synchronize"]
            git push [origin "the branch you want to synchronize"]

        \


(20200929) How to Work on the Same Branch
-----------------------------------------

Flow
....

    #.  edit and commit until satisfied

        ::

            "edit"
            git add
            git commit

        \

    #.  synchronize with the remote

        ::

            git pull --rebase

        \

    #.  fix conflict until cleared

        ::

            "edit"
            git add
            git rebase --continue

        \

    #.  push

        ::

            git push

        \

Example
.......

    #.  as shown, two local depositories "a" and "b" are pointed to the same remote

        .. image:: howToWorkOnTheSameBranch_twoLocal.png

        \

    #.  then depository "a" edited, added and committed

        .. image:: howToWorkOnTheSameBranch_commitByA.png

        \

    #.  then depository "a" edited, added and committed more files

        .. image:: howToWorkOnTheSameBranch_moreCommitsByA.png

        \

    #.  then depository "a" pushed.
        fortunately, no one pushed before "a", so it works.

        .. image:: howToWorkOnTheSameBranch_pushByA.png 

        \

    #.  meanwhile, depository "b" edited, added and committed many times.
        and the commits are about the same file changed by "a".

        .. image:: howToWorkOnTheSameBranch_manyCommitsByB.png

        \

    #.  as a wiser commiter, depository "b" pulled with rebase before pushing.
        as expected, conflicts are reported

        .. image:: howToWorkOnTheSameBranch_pullByB.png

        \

    #.  for the first commitment, depository "b" chose to use both of them and go on with "git rebase --continue"

        .. image:: howToWorkOnTheSameBranch_rebaseContinueByB.png

        \

    #.  for the second commitment, depository "b" chose to use his one and go on with "git rebase --continue"
        for the first commitment, depository "b" chose to use their one and go on with "git rebase --ski["

        .. image:: howToWorkOnTheSameBranch_rebaseSkipByB.png

        \

    #.  after all conflicts are resolved, depository "b" pushed

        .. image:: howToWorkOnTheSameBranch_pushByB.png

        \

    #.  now depository "a" could pull

        .. image:: howToWorkOnTheSameBranch_pullByA.png

        \
