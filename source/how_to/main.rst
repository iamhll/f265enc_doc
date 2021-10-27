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

(20211026) How to Diff with an Arbitary Commit
--------------------------------------------------

    #.  use diff

        ::

            git diff "SHA1 ID of the commit you want to diff with"

        \

    #.  use reset

        ::

            git reset "SHA1 ID of the commit you were working with"

        **do not forget to reset back with git reset ORIGIN**

        \


(20211026) How to Get a Simple History
--------------------------------------

    #.  |   press F4 after "gitk --all" is executed
        |   (or click "View" and choose "Edit view..." after gitk --all is executed)
        |   click "Simple history"

        .. image:: howToGetASimpleHistory_edit.png

        \

    #.  click "ok"

        .. image:: howToGetASimpleHistory_okay.png

        \

    #.  "gitk --all --simplify-by-decoration" works as well


(20211026) How to Rename
------------------------

    #.  |   put cursor on the variable or function you want rename and press F2
        |   (or right click on the variable or function you want rename and choose rename)
        |   enter a new name and press "enter"

        .. image:: howToRenameVariables_F2.png

        \

    #.  confirm the list and apply

        .. image:: howToRenameVariables_apply.png

        \

    #.  do not forget to save those changes

        .. image:: howToRenameVariables_save.png

        \


(20211026) How to Revert Partially
----------------------------------

    #.  open the "diff"

        .. image:: howToRevertChangePartially_openDiff.png

        \

    #.  right click on the changes you want to revert and choose "revert the selected changes"

        .. image:: howToRevertChangePartially_revert.png

        \

    #.  do not forget to save those changes

        .. image:: howToRevertChangePartially_save.png

        \


(20211026) How to Synchronize with the Remote
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

    #.  if you want the remote only

        ::

            git reset --hard origin/"the branch you want to synchronize"

        \

    #.  if you want the local only

        ::

            git push -f [origin "the branch you want to synchronize"]

        \

    #.  if you want both of them

        ::

            git pull --rebase

        you can also

        ::

            git rebase origin/"the branch you want to synchronize"

        then

        ::

            git push [origin "the branch you want to synchronize"]

        \


(20211026) How to Work on the Same Branch
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

    #.  fix any conflict encountered

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

    #.  as shown, two local depositories "a" and "b" point to the same remote.

        .. image:: howToWorkOnTheSameBranch_twoLocal.png

        \

    #.  depository "a" is edited, added and committed.

        .. image:: howToWorkOnTheSameBranch_commitByA.png

        \

    #.  depository "a" is edited, added and committed again.

        .. image:: howToWorkOnTheSameBranch_moreCommitsByA.png

        \

    #.  commits in depository "a" are pushed.
        fortunately, no one has pushed before, so it works.

        .. image:: howToWorkOnTheSameBranch_pushByA.png 

        \

    #.  meanwhile, depository "b" is edited, added and committed.
        and the commits are about the same file changed in depository "a".

        .. image:: howToWorkOnTheSameBranch_manyCommitsByB.png

        \

    #.  since the remote is changed by depository "a", depository "b" pulled with rebase.
        as expected, conflicts are reported

        .. image:: howToWorkOnTheSameBranch_pullByB.png

        \

    #.  for the first commit, depository "b" used both of them and go on with "git rebase --continue"

        .. image:: howToWorkOnTheSameBranch_rebaseContinueByB.png

        \

    #.  for the second commit, depository "b" used his one and go on with "git rebase --continue"
        for the first commit, depository "b" used their one and go on with "git rebase --skip"

        .. image:: howToWorkOnTheSameBranch_rebaseSkipByB.png

        \

    #.  after all conflicts are resolved, commits depository "b" are pushed

        .. image:: howToWorkOnTheSameBranch_pushByB.png

        \

    #.  now depository "a" could pull directly

        .. image:: howToWorkOnTheSameBranch_pullByA.png

        \
