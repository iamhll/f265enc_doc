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

    #.  use reset

        ::

            "commit your changes if necessary"
            git reset "SHA1 ID of the commitment you want to diff with"
            "make some edit"
            git reset "SHA1 ID of the commitment you were working with"


(20200917) How to Get a Simply History
--------------------------------------

    #.  |   press F4 after gitk --all is executed
        |   (or click "View" and choose "Edit wiew..." after gitk --all is executed)
        |   click "Simple history"

        .. image:: howToGetASimpleHistory_edit.png

        \

    #.  click "ok"

        .. image:: howToGetASimpleHistory_okay.png

        \

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

(20200923) How to Synchronize with Remote
-----------------------------------------

    #.  fetch and prune

        ::

            git fetch --all
            git remote prune origin

    #.  checkout

        ::

            git checkout "the branch you want to synchronize"

    #.  if the remote is right

        ::

            git reset --hard origin/"the branch you want to synchronize"

    #.  if your local is right

        ::

            git push -f [origin "the branch you want to synchronize"]

    #.  if both the remote and your local are right

        ::

            git pull --rebase [origin "the branch you want to synchronize"]
            git push [origin "the branch you want to synchronize"]
