.. -----------------------------------------------------------------------------
  ..
  ..  Filename       : main.rst
  ..  Author         : Huang Leilei
  ..  Created        : 2020-07-12
  ..  Description    : template related documents
  ..
.. -----------------------------------------------------------------------------

Template
========

Header
------

::

    //------------------------------------------------------------------------------
      //
      //  The confidential and proprietary information contained in this file may
      //  only be used by a person authorised under and to the extent permitted
      //  by a subsisting licensing agreement from XK Silicon.
      //
      //                   (C) COPYRIGHT 2020 XK Silicon.
      //                       ALL RIGHTS RESERVED
      //
      //  This entire notice must be reproduced on all copies of this file
      //  and copies of this file may only be made by a person if such person is
      //  permitted to do so under the terms of a subsisting license agreement
      //  from XK Silicon.
      //
      //  Revision       : 112933
      //  Release        : XK265
      //
    //------------------------------------------------------------------------------
      //
      //  Filename       : ???.h
      //  Author         : ???
      //  Created        : ????-??-??
      //  Description    : header file for ???
      //
    //------------------------------------------------------------------------------
      //
      //  Modified       : ????-??-?? by ???
      //  Description    : ???
      //
    //------------------------------------------------------------------------------

    #ifndef __XK265_???_HPP_
    #define __XK265_???_HPP_

    //=== INCLUDE ==================================================================
        #include "???.h"


    //=== DEFINE ===================================================================
        #define ???    ?


    //=== CLASS ====================================================================
    class ???
    {
    private:
    //--- ENUM -----------------------------
        enum class ???_t = {
            ???
        };


    //--- TABLE ----------------------------
        const int s_???[?] = {
            ???
        };


    //--- VARIABLE -------------------------
        // ???
        int m_x;
        ??? ???;


    //--- FUNCTION -------------------------
        // ???
        void init();
        ??? ???(??? ???);


    public:
    //--- FUNCTION -------------------------
        void fmeProc(???);
    };


    //=== DEBUG CODE ===============================================================
    //--- KNOB -----------------------------
        #define DUMP_???    ???


    //--- DUMP_??? -------------------------
        #define DUMP_???                                                      \
            if (m_prm.dump???) {                                              \
                /* variables */                                               \
                static FILE* dumpFpt[?];                                      \
                static bool dumpFlg = 1;                                      \
                /* initial procedure */                                       \
                if (dumpFlg) {                                                \
                    string dumpStr[?] = {???, ...};                           \
                    for (int dumpIdx = 0; dumpIdx < ?; ++dumpIdx ) {          \
                        string dumpFileName = m_prm.dump_prefix               \
                            + "???_"                                          \
                            + dumpStr[dumpIdx]                                \
                            + "_S?I?F?.dat"                                   \
                        ;                                                     \
                        char *dumpFileNameChar;                               \
                        uint32_t dumpFileNameLeng = dumpFileName.length();    \
                        dumpFileNameChar = new char[dumpFileNameLeng + 1];    \
                        strcpy(dumpFileNameChar, dumpFileName.c_str());       \
                        dumpFpt[dumpIdx] = fopen(dumpFileNameChar, "w");      \
                        delete[] dumpFileNameChar;                            \
                    }                                                         \
                    dumpFlg = 0;                                              \
                }                                                             \
                /* main procedure */                                          \
                if (???) {                                                    \
                    statements                                                \
                }                                                             \
            }

    #endif /* __XK265_???_HPP_ */

Source
------

::

    //------------------------------------------------------------------------------
      //
      //  The confidential and proprietary information contained in this file may
      //  only be used by a person authorised under and to the extent permitted
      //  by a subsisting licensing agreement from XK Silicon.
      //
      //                   (C) COPYRIGHT 2020 XK Silicon.
      //                       ALL RIGHTS RESERVED
      //
      //  This entire notice must be reproduced on all copies of this file
      //  and copies of this file may only be made by a person if such person is
      //  permitted to do so under the terms of a subsisting license agreement
      //  from XK Silicon.
      //
      //  Revision       : 112933
      //  Release        : XK265
      //
    //------------------------------------------------------------------------------
      //
      //  Filename       : ???.cpp
      //  Author         : ???
      //  Created        : ????-??-??
      //  Description    : source file for ???
      //
    //------------------------------------------------------------------------------
      //
      //  Modified       : ????-??-?? by ???
      //  Description    : ???
      //
    //------------------------------------------------------------------------------
      //
      //  === commonly used abbreviation ===
      //  === ???    ???                 ===
      //
    //------------------------------------------------------------------------------

    #include "???.h"

    // ???
    ??? ???::???(??? ???)
    {   ???
    }


    // ???
    ??? ???::???(??? ???)
    {
    //=== VARIABLES ================================================================
        ???

    //=== TEST CURRENT PU ==========================================================
        ???

    //=== TEST SUB PU ==============================================================
        ???

    //=== DO PARTITION DECISION ====================================================
        ???

    //=== RETURN ===================================================================
        ???
    }
