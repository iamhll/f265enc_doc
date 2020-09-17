.. -----------------------------------------------------------------------------
    ..
    ..  Filename       : main.rst
    ..  Author         : Huang Leilei
    ..  Created        : 2020-09-11
    ..  Description    : structure related documents
    ..
.. -----------------------------------------------------------------------------

Structure
=========

    To maximize the reuse of codes and minimize the efforts to develop,
    I created an inheritance-based structure, where LCU acts as the base class, and other classes simply inherit from it.

(20200917) Class LCU
--------------------

    The following figure shows the contents of class LCU,
    which is made up of four groups:

    *   protected types
    *   protected variables
    *   protected functions
    *   public functions

        .. image:: classLcu.png

        \

    *   In the protected types,
        enums like

        ::

            enum class srcPrt_t{
                ALL = 0,
                RGH
            };
            enum class typPrt_t{
                SPLIT = 0,
                UNKNOWN,
                NON_SPLIT
            };

        typedefs like

        ::

            typedef int16_t    coe_t;
            typedef int8_t     mod_t;

        are contained.

        \

    *   In the protected variables,

        identification variables, like

        ::

            string m_name;

        connection variables, like

        ::

            cfg_t *m_cfg;
            FTH   *m_fth;

        pixel variables, like

        ::

            pxl_t (*m_oriLcu)[NUMB_CHN][SIZE_LCU      ][SIZE_LCU      ];
            pxl_t (*m_refSch)[NUMB_CHN][SIZE_SCH_Y_MAX][SIZE_SCH_X_MAX];

        information variables, like

        ::

            typPrt_t (*m_datPrtLcuFul)[LOG2_SIZE_LCU - 1][SIZE_LCU / 4][SIZE_LCU / 4];
            mod_t    (*m_datModLcuFul)[LOG2_SIZE_LCU - 1][SIZE_LCU / 4][SIZE_LCU / 4][NUMB_MOD];

        cost variables, like

        ::

            CTUINFO   m_infoCur;
            CTUINFO   m_infoBst;

        are contained

        \

    *   In the protected functions

        load functions, like

        ::

            void load();
            virtual void loadPipe();
            virtual void loadFile();
            virtual void loadRand();

        process functions, like

        ::

            void proc();
            virtual void procMain();
            virtual void procPrev();
            virtual void procPost();

        dump functions, like

        ::

            void dump();
            virtual void dumpFile();

        information tool functions, like

        ::

            void clrFlgFmvLcuExt();
            void updateFmvList(int x, int y, int w, int h);

        prediction tool functions, like

        ::

            void fltRefLu(pxl_t refAftFlt[SIZE_REF_EXT_MAX][SIZE_REF_EXT_MAX], int siz, int mod, pxl_t refBfrFlt[SIZE_REF_EXT_MAX][SIZE_REF_EXT_MAX]);
            void getPre(pxl_t preTmp[SIZE_LCU][SIZE_LCU], int x, int y, int siz, pxl_t refAftFlt[SIZE_REF_EXT_MAX][SIZE_REF_EXT_MAX], int mod, bool flgLu);

        transform tool functions, like

        ::

            void (*doTsfmFrwd[4])(int x, int y, int shf, int16_t res[SIZE_LCU][SIZE_LCU], int16_t coe[SIZE_LCU][SIZE_LCU]);
            void (*doTsfmBkwd[4])(int x, int y, int shf, int16_t res[SIZE_LCU][SIZE_LCU], int16_t coe[SIZE_LCU][SIZE_LCU]);

        cost tool functions, like

        ::

            uint32_t pixelSad4x4(const pxl_t *pix1, const int iStridePix1, const pxl_t *pix2, const int iStridePix2);
            void updateInfo(CTUINFO &dst, int x, int y, int siz, CTUINFO src, int idxLaC = 2);

        are contained

        \

    *   In the public functions

        constructor and destructor functions

        ::

            LCU();
            ~LCU();

        connection function

        ::

            virtual void connect(cfg_t &cfg, FTH &fth);

        process function

        ::

            void oneShot();

        copy functions, like

        ::

            void getDatPrtLcuFul(void *dst);
            void getDatModLcuFul(void *dst);

        are contained

(20200917) Work Flow
--------------------

    .. image:: workFlow.png

    *   in "new" phase,

        *   current module would call function LCU to allocate space and assign initial value to related variables

        \

    *   in "connect" phase,

        *   current module would call function connect to assign previous modules' addess to connection variables

        \

    *   in "run" phase,

        *   current module would call function load to copy results from its previous modules
        *   current module would call function proc to process those results

        \

    *   in "delete" phase,

        *   current module would call function ~LCU to release spaces


(20200917) Inheritance Consideration
------------------------------------

    Inheritance is performed according to one basic rule:

        common items are put in class LCU while individual ones are put in inherited classes

    A detailed inheritance list is shown as below:

    .. table::
        :align: left
        :widths: auto

        +---------------------+----------------+-----------+-----------------+------------------+-------------------------------------+
        | Type                | Sub-type       | Exists in | Exists in the   | Example          | Why exists or why not               |
        |                     |                | Class LCU | Inherited Class |                  |                                     |
        +=====================+================+===========+=================+==================+=====================================+
        | protected types     | enum           | Y         | N               | srcPrt_t         | always the same                     |
        |                     |                +-----------+-----------------+------------------+-------------------------------------+
        |                     |                | N         | Y               | typCst_t         | different in each module            |
        |                     +----------------+-----------+-----------------+------------------+-------------------------------------+
        |                     | typedef        | Y         | N               | datCoe_t         | always the same                     |
        |                     |                +-----------+-----------------+------------------+-------------------------------------+
        |                     |                | N         | Y               | datCst_t         | different in each module            |
        +---------------------+----------------+-----------+-----------------+------------------+-------------------------------------+
        | protected variables | identification | Y         | N               | m_name           | always the same                     |
        |                     +----------------+-----------+-----------------+------------------+-------------------------------------+
        |                     | connection     | Y         | N               | \*m_cfg          | always the same                     |
        |                     |                +-----------+-----------------+------------------+-------------------------------------+
        |                     |                | N         | Y               | \*m_rmd          | avoid loop call                     |
        |                     +----------------+-----------+-----------------+------------------+-------------------------------------+
        |                     | pixel          | Y         | N               | \*m_oriLcu       | always the same                     |
        |                     +----------------+-----------+-----------------+------------------+-------------------------------------+
        |                     | information    | Y         | N               | \*m_datPrtLcuFul | always the same                     |
        |                     +----------------+-----------+-----------------+------------------+-------------------------------------+
        |                     | cost           | Y         | N               | \*m_infoCur      | always the same                     |
        +---------------------+----------------+-----------+-----------------+------------------+-------------------------------------+
        | protected functions | load           | Y         | N               | load()           | always the same                     |
        |                     |                +-----------+-----------------+------------------+-------------------------------------+
        |                     |                | Y         | Y               | loadPipe()       | different in each module,           |
        |                     |                |           |                 |                  | but some could be reused            |
        |                     +----------------+-----------+-----------------+------------------+-------------------------------------+
        |                     | process        | Y         | N               | proc()           | always the same                     |
        |                     |                +-----------+-----------------+------------------+-------------------------------------+
        |                     |                | N         | Y               | procMain()       | different in each module            |
        |                     |                +-----------+-----------------+------------------+-------------------------------------+
        |                     |                | Y         | Y               | procPrev()       | different in each module,           |
        |                     |                |           |                 |                  | but some could be reused            |
        |                     +----------------+-----------+-----------------+------------------+-------------------------------------+
        |                     | dump           | Y         | N               | dump()           | always the same                     |
        |                     |                +-----------+-----------------+------------------+-------------------------------------+
        |                     |                | Y         | Y               | dumpFile()       | different in each module,           |
        |                     |                |           |                 |                  | but some could be reused            |
        |                     +----------------+-----------+-----------------+------------------+-------------------------------------+
        |                     | tool           | Y         | N               | getPre()         | always the same                     |
        +---------------------+----------------+-----------+-----------------+------------------+-------------------------------------+
        | public functions    | connection     | Y         | Y               | connect()        | different in each module,           |
        |                     |                |           |                 |                  | but some could be reused            |
        |                     +----------------+-----------+-----------------+------------------+-------------------------------------+
        |                     | process        | Y         | N               | oneShot()        | always the same                     |
        |                     +----------------+-----------+-----------------+------------------+-------------------------------------+
        |                     | copy           | Y         | N               | getDatPrtLcuFul  | always the same                     |
        +---------------------+----------------+-----------+-----------------+------------------+-------------------------------------+
