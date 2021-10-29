<a href=" https://github.com/moshix/mvs/blob/master/codenotary.com"><img src="https://raw.githubusercontent.com/moshix/mvs/master/secured-by-immudb.svg" width="109px;"/></a>
<br>
# XEDITcommandsfull
Userful Xedit commands


<H3>Contents</H3>

<UL>
<LI><A HREF="#subcommands" >Subcommands &amp; Supplied Macros</A>
<LI><A HREF="#syntax"      >Syntax &amp; Options</A>
<LI><A HREF="#prefix"      >Prefix Subcommands &amp; Supplied Macros</A>
<LI><A HREF="#set"         >SET Options</A>
<LI><A HREF="#query"       >QUERY Options</A>
<LI><A HREF="#extract"     >EXTRACT Operands</A>
<LI><A HREF="#read"        >READ Subcommand</A>
<LI><A HREF="#sos"         >SOS Operands</A>
<LI><A HREF="#targets"     >Targets</A>
<LI><A HREF="#defaults"    >Defaults by Filetype</A>
</UL>

<H3>Utilities</H3>

<UL>
<LI><A HREF="parset.exec">PARSET.EXEC</A>:
Parses an XEDIT target from the beginning of a string
</UL>

<H3>See Also</H3>
<UL>
<LI>IBM
<A HREF="http://publibfp.dhe.ibm.com/cgi-bin/bookmgr/FINDBOOK?filter=xedit&SUBMIT=Find">XEDIT Manuals</A>
on-line
<P>
<LI><A HREF="rexx.html">REXX Summary</A><BR>
Summary of REXX functions, operators, and instructions
<P>
<LI>Mansfield Software's KEDIT:
<A HREF="http://www.kedit.com">http://www.kedit.com</A><BR>
A very nice XEDIT-like editor that uses REXX as a macro language
<P>
<LI>This summary is also available as a Microsoft Word for Windows 95 (version 7.0)
document <A HREF="xedit.doc">xedit.doc</A>,
which will look better when printed. It's formatted for a LaserJet printer,
19 8&#189;&#215;11" pages.
</UL>

<HR SIZE=4 NOSHADE>

<A NAME=subcommands><H2>Subcommands &amp; Supplied Macros</H2></A>
<PRE>
<B>/</B>str[/]            Special case of LOCATE when delimiter is slash
<B>&amp;</B>cmd               Execute cmd, then redisplay it; Enter to repeat
<B>?</B>                  Display last command (PF6); ?? for 2 cmds ago, etc.
<B>=</B>                  Re-execute previous command (PF9); == to do twice
<B>=</B>cmd               Execute cmd, then execute previous command
<B>Add</B> [n]            Add n lines below current line; default=1
<B>ALL</B> [t]            Display all lines matching target; omit t to restore [M]
<B>ALter</B> h1 h2 t n p  Change one character to another; see CHANGE syntax   [M]
<B>BAckward</B> [n|*]     Scroll up n screens; default=1 (PF7)
<B>Bottom</B>             Make last line the current line
<B>CANCEL</B>             Like QUIT for all files in ring                      [M]
<B>CAppend</B> txt        Append txt to end of current line                    [M]
<B>CDelete</B> ct         Delete columns from colptr thru ct; default ct=1
<B>CFirst</B>             Move column pointer to beginning of zone
<B>Change/s1/s2/t</B> n p Change string1 to string2 from curline thru target
<B>CInsert</B> txt        Insert text in current line starting at column pointer
<B>CLast</B>              Move column pointer to end of zone
<B>CLocate</B> ct         Locate column target; moves column pointer
<B>CMS</B> [cmscmd]       Execute CMS command; default=CMS subset mode, RETURN
<B>CMSG</B> [txt]         Place text on command line; default=clear command line
<B>COMMAND</B> cmd        Execute command without checking for synonym/macro
<B>COMPress</B> t         Prepare lines for new tab column settings from SET TABS
<B>COpy</B> t1 t2         Copy lines from curline thru target1 to follow target2
<B>COUnt</B> /str/ t      Count number of times string occurs in lines thru target
<B>COVerlay</B> txt       Overlay text in curline at colptr; blanks do not replace
<B>CP</B> [cpcmd]         Execute CP command; default=enter CP READ mode
<B>CReplace</B> txt       Replace text in curline at colptr; blanks do replace
<B>CURsor</B> CMdline c   Place cursor on command line at column c; default=1
<B>CURsor</B> Column      Place cursor on current line at current column
<B>CURsor</B> Home        Toggle cursor from command line to current line (PF12)
<B>CURsor</B> File l c    Place cursor at line/column in file; default c=1
<B>CURsor</B> Screen l c  Place cursor at line/column on screen; default c=1
<B>DELete</B> t           Delete lines from current line thru target; default=1
<B>Down</B> n|*           Advance current line; default=1; same as NEXT
<B>DUPlicat</B> n t       Make n copies of lines from curline thru target; def=1 1
<B>EMSG</B> [[mno]txt]    Alarm and display error message; optional system msg no
<B>EXPand</B> t           Reposition data in lines with tab (x'05') chars
<B>EXTract</B> /o1/o2/... Extract internal XEDIT info; see <A HREF="#extract">EXTRACT Operands</A>
<B>FFile</B> [fn ft fm]   Unprotected file and quit (synonym for COMMAND FILE) [S]
<B>FILE</B>               Save file and quit
<B>FILE</B> [fn ft fm]    Save with new name and quit; typically syn for PFILE [S]
<B>Find</B> txt           Search forward for first line starting with text
<B>FINDUp</B> txt         Search backward for first line starting with text
<B>FOward</B> [n|*]       Scroll down n screens; default=1 (PF8)
<B>FUp</B> txt            Alternate name for FINDUP
<B>GET</B>                Insert lines from prior PUT command below current line
<B>GET</B> fn ft fm f n   Insert lines from file; first,numrec; default: = = = 1 *
<B>Help</B> [topic]       Get help: MENU, TASK, commandname, msgno (PF1)       [M]
<B>HEXType</B> t          Display lines in both hex and EBCDIC; default=1      [M]
<B>Input</B>              Leave edit more and enter input mode
<B>Input</B> txt          Insert line of text into file, below current line
<B>Join</B> [ALigned]     Join current line and next line into one line        [M]
<B>Join</B> " Column      Overlay next line starting at column pointer         [M]
<B>Join</B> " CURSOR      Overlay next line starting at cursor position        [M]
<B>Join</B> " c [c ...]   Overlay next line at column c [, and next at ...]    [M]
<B>Join</B> " /str[/...]  Join current line, string, then next line [,...]     [M]
<B>LEft</B> [n]           Move view of columns to left; default=1; 0 to restore
<B>LOAD</B> fn ft fm      Load file into storage; use in PROFILE XEDIT only
<B>Locate</B> t [cmd]     Locate target, then do optional command
<B>LOWercas</B> t         Change uppercase letters to lowercase; default=1
<B>LPrefix</B> [txt]      Simulate writing txt in prefix area of current line
<B>MACRO</B> name         Execute macro (not command); or name w/nonalpha chars
<B>MErge</B> t1 t2 [c]    Combine two sets of lines, overlay 2nd on 1st at colno
<B>MODify</B> keyword     Display SET command key and current value on cmdline [M]
<B>MOve</B> t1 t2         Move lines from curline thru t1 to follow t2
<B>MSG</B> txt            Display a message in the message area
<B>Next</B> [n|*]         Scroll down n lines; default n=1; same as DOWN
<B>NFind</B> txt          Search forward for first line not starting with text
<B>NFINDUp</B> txt        Search backward for first line not starting with text
<B>NFUp</B> txt           Alternate name for NFINDUP
<B>Overlay</B> txt        Replace chars in curline with non-blank chars in text
<B>PARSE</B> c [ADLNSTW]  Parse stacked line for number/string/target etc.     [M]
<B>POWerimp</B>           Enter input mode, type as if screen were one long line
<B>PQUIT</B>              Quit file being edited, but prompt if modified (PF3)
<B>PREServe</B>           Save XEDIT settings until RESTORE
<B>PSAVE</B> fn ft fm     Protected save with new name; prompt if already exists
<B>PURge</B> macro        Purge copy of macro from virtual storage
<B>PUT</B> [t]            Put lines thru target into temp file; def=1; see GET
<B>PUT</B> t fn ft fm     Put lines thru target into file (create or append)
<B>PUTD</B> t [fn ft fm]  Like PUT but also deletes from the file being edited
<B>QQuit</B>              Unprotected (quick) quit of file being edited
<B>Query</B> op           Query option setting; see <A HREF="#query">QUERY Options</A>
<B>QUIT</B>               Quit file being edited; typical syn for PQUIT (PF3)  [S]
<B>QUIT</B> rc            Quit file being edited and return rc (from macros only)
<B>READ</B>               Place info from terminal into console stack; see <A HREF="#read">READ Subcommand</A>
<B>RECover</B> [n|*]      Recover n lines deleted by DELETE, MERGE, PUTD; def=1
<B>REFRESH</B>            Update screen without waiting for input
<B>RENum</B> [start inc]  Renumber line numbers of VSBASIC or FREEFORT file
<B>REPEat</B> t           Advance line &amp; do last command, for each line thru targ
<B>Replace</B>            Replace current line with line(s) entered in input mode
<B>Replace</B> txt        Replace current line with text
<B>RESet</B>              Cancel all pending prefix commands and macros
<B>RESTore</B>            Restore all XEDIT settings saved by PRESERVE
<B>RGTLEFT</B> [n]        Toggle columns viewed right/left (PF10)              [M]
<B>RIght</B> [n]          Move view of columns to right; default=1; 0 to restore
<B>SAVE</B>               Save file being edited
<B>SAVE</B> fn ft fm      Save with new name; typically synonym for PSAVE      [S]
<B>SCHANGE</B> [pfkeyno]  Make CHANGE confirm each occurrence; def=6 (PF5)     [M]
<B>SET</B> option value   Change various XEDIT options; see <A HREF="#set">SET Options</A>
<B>SHift</B> L|R c t      Shift data left/right c columns thru targ; can lose data
<B>SI</B>                 Structured input: adds new lines, indent as previous [M]
<B>SORT</B> t A|D c1 c2   Sort lines thru target asc/descending by column range
<B>SOS</B> opt            Screen operation simulation, for macros; see <A HREF="#sos">SOS Operands</A>
<B>SPlit</B> [ALigned]    Split current line into two lines                    [M]
<B>SPlit</B> " Column     Split current line at current column pointer         [M]
<B>SPlit</B> " CURSOR     Split current line at cursor position                [M]
<B>SPlit</B> " c1 c2 ...  Split curline at column c1 [, and at column c2...]   [M]
<B>SPlit</B> " B|A /str1/ Split curline before/after string [, and...]         [M]
<B>SPLTJOIN</B>           Split or join depending on position of cursor (PF11) [M]
<B>STAck</B> t c n        Stack FIFO lines thru target, starting col, number cols
<B>STATus</B> [macro]     Display SET settings [or create macro with them]
<B>SSave</B> fn ft fm     Unprotected save (synonym for COMMAND SAVE)          [S]
<B>TOP</B>                Make "* * * Top of File * * *" line the current line
<B>TRAnsfer</B> opt       Like EXTRACT but stacks responses for EXEC2 &amp;READ
<B>Type</B> t             Display lines thru target; default=1
<B>Up</B> [n|*]           Move current line up n lines; default=1
<B>UPPercas</B> t         Change lowercase letters to uppercase; default=1
<B>VMFDEOPT</B>           Undo changes made by VMFOPT                          [M]
<B>VMFOPT</B>             Optimize EXEC2 &amp;GOTO label statements in a macro     [M]
<B>Xedit</B>              Move to next file in ring
<B>Xedit</B> fn ft fm     Add another file to XEDIT ring, or move to the file
<HR SIZE=1>t                  An XEDIT target (see <A HREF="#targets">Targets</A>)
ct                 An XEDIT column target
cmd                An XEDIT subcommand
/                  String delimiter (need not be the slash character)
n                  Number of lines (a non-negative integer); * means all
p                  Starting occurrence
h                  A single character or a two-digit hexadecimal number
fn ft fm           File name/type/mode; use = for same as current file
colptr             Column pointer
curline            Current line
<HR SIZE=1>(PFn)              By default, command is assigned to this PF key
[M]                This is actually a macro, not a subcommand
[S]                By default, this is actually a synonym, not a subcommand
<HR SIZE=1></PRE>

<A NAME=syntax><H2>Syntax &amp; Options</H2></A>

<PRE>
<B>XEDIT</B> fn ft [fm|*] [( option1 option2 ... [)[myopts]]]
<HR SIZE=1><B>WINdow</B> XEDIT|name   Name of virtual screen and window
<B>Width</B> w             Lrecl for XEDIT to use
<B>NOSCreen</B>            Force 3270 into typewriter (line) mode
<B>PROFile</B> PROFILE|fn  Macro to run before user starts editing; ft=XEDIT
<B>NOPROFil</B>            Don't execute any profile
<B>NOCLear</B>             Do not clear screen; place screen in MORE... state
<B>NOMsg</B>               Start with SET MSGMODE OFF
<B>MEMber</B> memname      Name of member when ft=MACLIB
<B>LOCk</B>                Lock file (when in SFS directory)
<B>NOLOCk</B>              Don't lock file (when in SFS directory)
<B>NOUpdate</B>            Don't apply UPDATE stmts (even if LOAD says UPDATE)
<B>Update</B>              Look for fn=fn and ft=UPDATE, apply update statements
<HR SIZE=1><B>Seq8</B>                Last 8 cols contain 8-digit sequence numbers
<B>NOSeq8</B>              Last 8 cols contain 3-char label and 5-digit seq no
<B>Ctl</B> fn              File named fn CNTRL is multiple update control file
<B>NOCtl</B>               Don't use control file (even if specified in LOAD)
<B>Merge</B>               All updates and editing changes written to UPDATE file
<B>UNtil</B> ft            Specify ft of last update applied to the file
<B>Incr</B> 1|incr         Specify minimum increment for serialization
<B>SIDcode</B> str         Write string in cols lrecl-16 thru lrecl-9
<HR SIZE=1></PRE>

<A NAME=prefix><H2>Prefix Subcommands &amp; Supplied Macros</H2></A>

<PRE>
<B>.....</B>    Synonym for SI (see below)                                     [S]
<B>A</B>n       Add n new lines below this line; default=1; same as I command
n<B>A</B>       Add n new lines below this line; default=1; same as I command
<B>C</B>n       Copy n lines; default=1; use F or P for destination; * means rest
n<B>C</B>       Copy n lines; default=1; use F or P for destination
<B>CC</B>       Copy block of lines; use F or P for destination
<B>D</B>n       Delete n lines; default=1; * means rest of file
n<B>D</B>       Delete n lines; default=1
<B>DD</B>       Delete block of lines
<B>E</B>        Extend logical line by one more virtual screen line
<B>F</B>        Follow: target for C and M commands
<B>I</B>n       Insert n new lines below this line; default=1; same as A command
n<B>I</B>       Insert n new lines below this line; default=1; same as A command
<B>M</B>n       Move n lines; default=1; use F or P for destination; * means rest
n<B>M</B>       Move n lines; default=1; use F or P for destination
<B>MM</B>       Move block of lines; use F or P for destination
<B>P</B>        Preceding: target for C and M commands
<B>S</B>[+|-]n  Show: in shadow line, show first/last n lines excluded        [SM]
<B>S</B>*       Show: in shadow line, show all lines excluded by X or ALL     [SM]
n<B>S</B>       Show: in shadow line, show first n lines excluded by X or ALL [SM]
<B>SCALE</B>    Display scale line here (like SET SCALE ON n)
<B>SI</B>       Structured input starting on this line (same as SI macro)
<B>TABL</B>     Display tab line here (like SET TABLINE ON n)
<B>X</B>n       Exclude n lines from display; default=1; * means rest
n<B>X</B>       Exclude n lines from display; default=1
<B>XX</B>       Exclude block of lines from display
<B>"</B>n       Duplicate this line n times; default=1
n<B>"</B>       Duplicate this line n times; default=1
<B>""</B>n      Duplicate block of lines n times; default=1
n<B>""</B>      Duplicate block of lines n times; default=1
<B>/</B>[c]     Make this line the current line; optionally set column pointer
[c]<B>/</B>     Make this line the current line; optionally set column pointer
<B>.</B>name    Assign symbolic name to this line (like SET POINT)
<B>&lt;</B>c       Shift left by c columns on this line; default=1               [SM]
c<B>&lt;</B>       Shift left by c columns on this line; default=1               [SM]
<B>&lt;&lt;</B>c      Shift left by c columns on block of lines; default=1          [SM]
c<B>&lt;&lt;</B>      Shift left by c columns on block of lines; default=1          [SM]
<B>&gt;</B>c       Shift right by c columns on this line; default=1              [SM]
<B>&gt;&gt;</B>c      Shift right by c columns on block of lines; default=1         [SM]
c<B>&gt;&gt;</B>      Shift right by c columns on block of lines; default=1         [SM]
<HR SIZE=1>[S]      By default, this is actually a synonym, not a subcommand
[SM]     This is actually a supplied macro, not a subcommand
<HR SIZE=1></PRE>

<A NAME=set><H2>SET Options</H2></A>

<PRE>
 SET  <B>=</B> str               Put string in the = buffer
 SET  <B>ALT</B> n [p]           Change number of AUTOSAVE/SAVE alterations
[SET] <B>APL</B> ON|OFF          Tell editor and CMS if APL keys are available
[SET] <B>ARBchar</B> OFF|ON [c]  Turn on arbitrary character; define it; default=$
[SET] <B>AUtosave</B> OFF|n [fm] Autosave every n alterations; filemode
[SET] <B>BRKkey</B> OFF|ON key   Set CP BRKKEY key (usually ON PA1)
[SET] <B>CASE</B> Uppercase|Mixed [Respect|Ignore]
                          U/M: do/don't translate all chars to uppercase;
                          R/I: respect/ignore case in target strings
[SET] <B>CMDline</B> On|OFf|Top|Bottom
                          Last two lines, off, second line, last line
[SET] <B>COLOR</B> field|* [color] [exthi] [High|Nohigh] [pss]
                          Define color/highlighting for an area of screen
[SET] <B>COLPtr</B> ON|OFF       Column pointer (typewriter terminals only)
 SET  <B>CTLchar</B> OFF         No control character for reserved lines
 SET  <B>CTLchar</B> c OFF       Reset a specified control character
 SET  <B>CTLchar</B> c Escape    Define escape character (next is a control char)
 SET  <B>CTLchar</B> c Protect|Noprotect [clr] [xhi] [High|Nohigh|Invisible] [pss]
                          Define field type created by char
[SET] <B>CURLine</B> ON|OFF M[+n|-n]
                          Place/remove current line
[SET] <B>DISPlay</B> n1 [n2|*]   Display scope (see SET SELECT); default=0 0
[SET] <B>ENTer</B> [BEFORE|AFTER|ONLY|IGNORE] [cmd|NULLKEY|COPYKEY|TABKEY]
[SET] <B>ESCape</B> ON|OFF [c]   Escape char for cmds (typewriter terminals only)
[SET] <B>ETARBCH</B> ON|OFF [c]  Extended arbitrary char for DBCS strings
[SET] <B>ETMODE</B> ON|OFF       Extended mode: recognize DBCS strings?
[SET] <B>FILler</B> [c]          Filler char, when tabs expanded; default=space
[SET] <B>FMode</B> fm            Change filemode (A-Z, and optional 0-6)
[SET] <B>FName</B> fn            Change filename (1-8 chars)
[SET] <B>FType</B> fn            Change filetype (1-8 chars)
[SET] <B>FULLread</B> ON|OFF     Sense null chars in lines; like CMS SET FULLREAD
[SET] <B>HEX</B> ON|OFF          Allow hex in strings and targets (LOCATE/x'FF'/)
[SET] <B>IMage</B> ON|OFF|Canon  Handling of tab and backspace chars during input
[SET] <B>IMPcmscp</B> ON|OFF     Implicit CMS/CP cmd if not recognized by XEDIT
[SET] <B>LASTLorc</B> [str]      Put string in last-locate-or-change buffer
[SET] <B>LINENd</B> ON|OFF [c]   Recognize/specify line-end char (default=#)
[SET] <B>LRecl</B> n|*           Set new logical record length when file saved
[SET] <B>MACRO</B> ON|OFF        On means look for macros before subcommands
[SET] <B>MASK</B> Immed [txt]    Define mask used when new lines are inserted
[SET] <B>MASK</B> Define         Show scale on cmdline, you type new mask over it
[SET] <B>MASK</B> Modify         Show current mask on cmdline, type over to modify
[SET] <B>MSGLine</B> OFF         Message line off; pass msgs to CMS for display
[SET] <B>MSGLine</B> ON M[+n|-n] [p] [Overlay]
                          Specify location of message line; allow up to p
                          lines for messages; optionally overlay file line
                          (use line only if msg to show); default=ON 2 2
[SET] <B>MSGMode</B> ON|OFF [Short|Long]
                          Show messages? (when off, use EXTRACT/LASTMSG/)
[SET] <B>NONDisp</B> [c]         Nondisplayable character surrogate (usually=")
[SET] <B>NULls</B> ON|OFF        Replace trailing blanks with nulls (use 3270 Ins)
[SET] <B>NUMber</B> ON|OFF       Number file lines in prefix area (else "=====")
[SET] <B>PAn</B> [BEFORE|AFTER|ONLY|IGNORE] [cmd|NULLKEY|COPYKEY|TABKEY]
[SET] <B>PACK</B> ON|OFF Compress file records when file is saved
[SET] <B>PENDing</B> OFF         Remove pending cmd from prefix area of curline
[SET] <B>PENDing</B> ERROR str   Write "?str" in prefix area of curline
[SET] <B>PENDing</B> ON str      Write "str" in prefix area of curline
[SET] <B>PENDing</B> BLOCK str   Write "str" (block cmd) in prefix area of curline
[SET] <B>PFn</B> [BEFORE|AFTER|ONLY|IGNORE] [cmd|NULLKEY|COPYKEY|TABKEY]
[SET] <B>Point</B> .str [OFF]    Define or delete symbolic name for current line
[SET] <B>PREfix</B> OFF          Remove prefix area from screen
[SET] <B>PREfix</B> ON|Nulls [Left|Right]
                          Enable prefix area; Nulls allows insert
[SET] <B>PREfix</B> Synonym syn cmd
                          Define a prefix synonym for prefix area
[SET] <B>RANge</B> t1 t2         Set line range; all cmds operate just w/in range
[SET] <B>RECFm</B> F|V|FP|VP     Change record format (fixed/variable; packed)
[SET] <B>REMOte</B> ON|OFF       Compress data transmission; see CMS SET REMOTE
[SET] <B>RESERved</B> M[+n|-n] [color] [exthi] [pss] High|Nohigh [text]
                          Reserve n lines (not used for file display)
[SET] <B>RESERved</B> M[+n|-n] Off
                          Un-reserve n lines
[SET] <B>SCALe</B> ON|OFF M[+n|-n]
                          Place/remove scale line; default=ON M+1
[SET] <B>SCOPE</B> Display|All   Act on lines within SET DISPLAY scope; or all
[SET] <B>SCReen</B> n [Horizontal|Vertical]
                          Split screen evenly into n logical screens
[SET] <B>SCReen</B> Size s1 s2 ... sn
                          Split screen horizontally; minimum 5 lines each
[SET] <B>SCReen</B> Width w1 w2 ... wn
                          Split screen vertically; minimum 20 columns each
[SET] <B>SCReen</B> Define s1 w1 h1 v1 ... sn wn hn vn
                          S=lines, W=width, H/V=line/column of upper-left
[SET] <B>SELect</B> [+|-]n [t|1] Assign selection level n to curline thru target
[SET] <B>SERial</B> OFF          Don't update serial area when file saved
[SET] <B>SERial</B> ON|ALL|str [inc [start]]
                          Add serial id to last 8 columns of each file line
[SET] <B>SHADow</B> ON|OFF       Show shadow lines when excluded by SELECT/DISPLAY
[SET] <B>SIDcode</B> [str]       Insert string in every line of an update file
[SET] <B>SPAN</B> OFF            Strings must be on one line to match target
[SET] <B>SPAN</B> ON [Blank|Noblank [n|*]]
                          Concatenate lines when matching target strings;
                          trailing blanks are ignored; BLANK acts as if one
                          blank between lines; n specifies number of lines
                          string can span; default=OFF BLANK 2
[SET] <B>SPILL</B> OFF|ON|WORD   Truncate or spill lines when too long
[SET] <B>STAY</B> OFF|ON         OFF=go to EOF if target not found; ON=stay put
[SET] <B>STReam</B> ON|OFF       Search OFF=curline or ON=entire file for col targ
[SET] <B>SYNonym</B> ON|OFF      Look for synonyms?
[SET] <B>SYNonym</B> [LINEND c] syn [n] cmd
                          Assign synonym to command; use linend char for
                          multiple commands; n=minimum abbreviation chars
[SET] <B>SYNonym</B> [LINEND c] syn [n [fmt1 ... fmtn]] cmd [&amp;1 ... &amp;n]
                          Assign synonym with different operand order than
                          command; fmtn indicates operand formats (&amp; &amp;/ &amp;.
                          &amp;*); &amp;n indicates relative order
[SET] <B>TABLine</B> ON|OFF M[+n|-n]
                          Place/remove tab line; default=OFF -3
[SET] <B>TABS</B> c1 c2 ... cn   Set logical tabs stops; up to 28
[SET] <B>TERMinal</B> Typewriter|Display
                          Use T to force display terminal into line mode
[SET] <B>TEXT</B> ON|OFF         Tell editor and CMS if text keys are available
[SET] <B>TOFEOF</B> ON|OFF       Show top-of-file and end-of-file notice lines
[SET] <B>TRANSLat</B> OFF|c1 c2 c1 c2...
                          Lower/upper translation for non-US terminals
[SET] <B>TRunc</B> n|*           Define truncation column
[SET] <B>VARblank</B> ON|OFF     Make target like /a b/ match text like "a     b"
[SET] <B>Verify</B> ON|OFF       Display all lines changed by subcommands
[SET] <B>Verify</B> [Hex] s1 e1 [Hex] s2 e2 ...
                          Columns numbers (start/end pairs) to display
[SET] <B>WRap</B> ON|OFF         Wrap around past EOF when LOCATE/FIND/etc.
[SET] <B>Zone</B> zone1 zone2|*  Define columns to search for targets
<HR SIZE=1>M[+n|-n]     n  means nth line from top of screen
            +n  means nth line from top of screen
            -n  means nth line from bottom of screen
           M    means middle line of screen
           M+n  means nth line below middle of screen
           M-n  means nth line above middle of screen
<HR SIZE=1>field      Arrow   Cmdline CUrline Filearea Idline   Msgline
           Pending PRefix  Scale   SHadow   STatarea Tabline
<HR SIZE=1>color      Blue Red Pink Green Turquoise Yellow White Default
<HR SIZE=1>exthi      BLInk REVvideo Underline NONe
<HR SIZE=1>pss        PS0 PSA PSB PSC PSD PSE PSF
<HR SIZE=1></PRE>

<H3>Suggested non-default settings for your PROFILE XEDIT</H3>

<PRE>
COMMAND SET WRAP     ON               /* Wrap from bot to top (LOCATE)   */
COMMAND SET STAY     ON               /* Stay put if LOCATE not found    */
COMMAND SET NULLS    ON               /* Nulls (not spaces) at line ends */
COMMAND SET NUMBER   ON               /* Number lines in prefix area     */
COMMAND SET PREFIX   NULLS            /* Prefix left fill with nulls     */
COMMAND SET SHADOW   OFF              /* Don't display shadow lines      */
COMMAND SET SCALE    OFF              /* Column numbers rarely needed    */
COMMAND SET CASE     MIXED IGNORE     /* Mixed case entry and searching  */
COMMAND SET MSGLINE  ON 2 15 OVERLAY  /* Many lines for messages         */
COMMAND SET AUTOSAVE 20               /* AUTOSAVE every 20 alterations   */
COMMAND SET VERIFY   1 *              /* See entire lrecl                */
COMMAND SET LINEND   OFF #            /* Disable command delimiter       */
</PRE>

<A NAME=query><H2>QUERY Options</H2></A>

<PRE>
<B>=</B>           Display the string in the = buffer (last executed command)
<B>ACTion</B>      ON if any action other than displaying or scrolling; else OFF
<B>ALT</B>         Number of alterations to file since last AUTOSAVE and SAVE
<B>APL</B>         APL setting: ON or OFF
<B>ARBchar</B>     Arbitrary character setting: ON or OFF; and the arbchar
<B>AUtosave</B>    AUTOSAVE count, file id, and number of alterations
<B>BASEft</B>      Base filetype specified by XEDIT command or LOAD subcommand
<B>BRKkey</B>      OFF; or ON and the PF or PA key currently set to be the BRKKEY
<B>CASE</B>        Case setting: U=upper or M=mixed; and R=respect or I=ignore
<B>CMDline</B>     Command line setting: ON, OFF, TOP, or BOTTOM
<B>COLOR</B> *|fld Color settings for all or one field (see SET COLOR for fields)
<B>COLPtr</B>      Column pointer display for typewriter terminals: ON or OFF
<B>COLumn</B>      Column number of the column pointer
<B>CTLchar</B>     Display escape character and all control characters
<B>CTLchar</B> c   Display the attributes of one control character
<B>CURLine</B>     Line number of current line
<B>CURSor</B>      Position of cursor on screen (row,col) and in file (line,col)
<B>DISPLay</B>     Range of selection levels included in display
<B>EDIRName</B>    Name of SFS directory containing file when it was first loaded
<B>EFMode</B>      Two-character filemode of file when it was first loaded
<B>EFName</B>      Eight-character filename of file when it was first loaded
<B>EFType</B>      Eight-character filetype of file when it was first loaded
<B>ENTer</B>       BEFORE, AFTER, ONLY, or IGNORE; and the enter key definition
<B>EOF</B>         End of file: ON if line pointer at EOF (or EORange); else OFF
<B>EOL</B>         End of line: ON if column pointer at zone2+1; else OFF
<B>ESCape</B>      ON or OFF; and the escape character
<B>ETARBCH</B>     ON or OFF; and the extended arbitrary character
<B>ETMODE</B>      Extended mode (DBCS): ON or OFF
<B>FILler</B>      Display the filler character
<B>FMode</B>       Display the two-character filemode
<B>FName</B>       Display the eight-character filename
<B>FType</B>       Display the eight-character filetype
<B>FULLread</B>    Sense null characters: ON or OFF
<B>HEX</B>         Allow hex in strings and targets: ON or OFF
<B>IMage</B>       Tab and backspace handing during input: ON, OFF, or CANON
<B>IMPcmscp</B>    Implicit CMS/CP: ON or OFF
<B>LASTLorc</B>    Display contents of last-locate-or-change buffer
<B>LASTmsg</B>     Display last message issued by editor
<B>LENgth</B>      Length of current line (col 1 thru trunc, excl trail blanks)
<B>LIBName</B>     Display library filename when MEMBER is ON
<B>LIBType</B>     Display library filetype when MEMBER is ON
<B>LIne</B>        Current line number, relative to beginning of file
<B>LINENd</B>      ON or OFF; and the line-end character
<B>LRecl</B>       Logical record length of the file
<B>LScreen</B>     Logical screen info (six integers): number of lines/columns in
              logical screen; line/column numbers of top-left corner of
              logical on virtual; number of lines/columns in virtual screen
<B>MACRO</B>       Look for macros before subcommands: ON or OFF
<B>MASK</B>        Display the mask line
<B>MEMber</B>      ON if editing member of a CMS library; or OFF
<B>MSGLine</B>     ON or OFF; location of message line; number lines [; OVERLAY]
<B>MSGMode</B>     ON, LONG, or SHORT (nothing displayed when MSGMODE OFF)
<B>NBFile</B>      Number of files in ring
<B>NONDisp</B>     Non-displayable character surrogate
<B>NULls</B>       Replace trailing blanks with nulls: ON or OFF
<B>NUMber</B>      Number file lines in prefix area: ON or OFF
<B>PA[n|*]</B>     One or all PA key definitions; BEFORE, AFTER, ONLY, or IGNORE
<B>PACK</B>        Compress file records when file is saved: ON or OFF
<B>PENDing</B> [BLOCK] [OLDNAME] name|*
            First entry in pending list with name, or all entries
            Response: Line n: 'name',Oldname='name',OP1='x',OP2='y',OP3='z'
<B>PF[n|*]</B>     One or all PF key definitions; BEFORE, AFTER, ONLY, or IGNORE
<B>Point</B> [*]   Display names associated with current line; * means all lines
<B>PREfix</B>      Prefix area display state: ON, OFF, or NULLS; LEFT or RIGHT
<B>PREfix</B> Synonym name|*
            Definition of specified synonym; or all synonym definitions
<B>RANge</B>       Line numbers of top and bottom of range
<B>RECFm</B>       Record format: F, V, FP, or VP
<B>REMote</B>      Compress data transmission: ON or OFF
<B>RESERved</B>    Line numbers of reserved screen lines
<B>RING</B>        Number of files being edited; fileid line for each
<B>SCALe</B>       ON or OFF; position of scale line on screen
<B>SCOPE</B>       Act on lines within SET DISPLAY scope: DISPLAY or ALL
<B>SCReen</B>      SIZE, WIDTH, or DEFINE; sizes of screens
<B>SELect</B>      Selection level of current line; maximum level for the file
<B>Seq8</B>        NOSEQ8 option: ON or OFF
<B>SERial</B>      Serial identification; increment value; starting value
<B>SHADow</B>      Show shadow lines: ON or OFF
<B>SIDcode</B>     Eight-character SIDCODE string
<B>SIZe</B>        Number of records in file being edited
<B>SPAN</B>        ON or OFF; B(=blank) or N(=noblank); number of lines
<B>SPILL</B>       Spill or truncate lines when too long: ON, OFF, or WORD
<B>STAY</B>        Stay put if target not found: ON or OFF
<B>STReam</B>      Search entire file for column targets: ON or OFF
<B>SYNonym</B>     Look for synonyms: ON or OFF
<B>SYNonym</B> name|*
            Synonym name, minimum abbreviation, and definition
<B>TABLine</B>     ON or OFF; position of tab line on screen
<B>TABS</B>        Tab column numbers
<B>TARGet</B>      Line/column of first char; line/column of last char
<B>TERMinal</B>    Type of terminal: DISPLAY or TYPEWRITER
<B>TEXT</B>        Text keys available: ON or OFF
<B>TOF</B>         At top-of-file: ON or OFF
<B>TOFEOF</B>      Show TOF and EOF notice lines: ON or OFF
<B>TOL</B>         At top-of-line: ON or OFF
<B>TRANSlat</B>    Lower/upper translation for non-US terminals: ON or OFF
<B>TRunc</B>       Truncation column number
<B>UNIQueid</B>    Unique identifier associated with file (see AUTOSAVE)
<B>UNTil</B>       File type up through which file updates were applied
<B>UPDate</B>      UPDATE option: ON or OFF
<B>VARblank</B>    Make target like /a b/ match text like "a     b": ON of OFF
<B>Verify</B>      ON or OFF; verification column numbers
<B>VERShift</B>    n or -n: relative position of screen over file (see LEFT/RIGHT)
<B>WIDTH</B>       WIDTH option value from XEDIT command or LOAD subcommand
<B>WRap</B>        Wrap around past EOF when LOCATE/FIND/etc.: ON or OFF
<B>Zone</B>        Left and right zone column numbers
</PRE>

<A NAME=extract><H2>EXTRACT Operands</H2></A>

<PRE>
<B>=</B>        What's in the equal (=) buffer (last executed command or macro)
         EQUALSIGN.1 = string in the equal buffer
<B>ACTion</B>   Have any changes been made to file (other than display/scroll)
         ACTION.1 = ON if any change made, else OFF
<B>ALT</B>      Number of alterations to file since last AUTOSAVE and SAVE
         ALT.1 = number of changes since last AUTOSAVE
         ALT.2 = number of changes since last SAVE
<B>APL</B>      Is APL on?
         APL.1 = ON|OFF
<B>ARBchar</B>  Status of arbitrary character
         ARBCHAR.1 = ON|OFF
         ARBCHAR.2 = the arbitrary character
<B>AUtosave</B> Is file being automatically saved?  If so, where?
         AUTOSAVE.1 = OFF or autosave count
         AUTOSAVE.2 = autosave filename
         AUTOSAVE.3 = number of alterations since last autosave
         AUTOSAVE.4 = autosave filemode (one character)
<B>BASEft</B>   Filetype originally specified in XEDIT command or LOAD subcommand
         BASEFT.1 = filetype
<B>BRKkey</B>   CP terminal break key setting
         BRKKEY.1 = ON|OFF
         BRKKEY.2 = PAn|PFn
<B>CASE</B>     Treatment of upper/lower case letters
         CASE.1 = MIXED|UPPER
         CASE.2 = RESPECT|IGNORE
<B>CMDline</B>  Where is command line
         CMDLINE.1 = ON|OFF|TOP|BOTTOM
         CMDLINE.2 = line number on screen
<B>COLOR</B> Arrow|Cmdline|CUrline|Filearea|Idline|Msgline|Pending|PRefix|Scale
           |SHadow|STatarea|Tabline|TOfeof
         What color/highlight/pss is specified area of screen
         COLOR.1 = color
         COLOR.2 = extended highlighting
         COLOR.3 = HIGH|NOHIGH
         COLOR.4 = programmed symbol set
<B>COLOR</B> *  All areas of screen and their color/highlighting/pss
         COLOR.1  = ARROW    color exthi HIGH|NOHIGH PSs
         COLOR.2  = CMDLINE  color exthi HIGH|NOHIGH PSs
         COLOR.3  = CURLINE  color exthi HIGH|NOHIGH PSs
         COLOR.4  = FILEAREA color exthi HIGH|NOHIGH PSs
         COLOR.5  = IDLINE   color exthi HIGH|NOHIGH PSs
         COLOR.6  = MSGLINE  color exthi HIGH|NOHIGH PSs
         COLOR.7  = PENDING  color exthi HIGH|NOHIGH PSs
         COLOR.8  = PREFIX   color exthi HIGH|NOHIGH PSs
         COLOR.9  = SCALE    color exthi HIGH|NOHIGH PSs
         COLOR.10 = SHADOW   color exthi HIGH|NOHIGH PSs
         COLOR.11 = STATAREA color exthi HIGH|NOHIGH PSs
         COLOR.12 = TABLINE  color exthi HIGH|NOHIGH PSs
         COLOR.13 = TOFEOF   color exthi HIGH|NOHIGH PSs
<B>COLPtr</B>   Column pointer display (for typewriter terminals)
         COLPTR.1 = ON|OFF
<B>COLumn</B>   Column number of the column pointer
         COLUMN.1 = current column number
<B>CTLchar</B>  Escape character and all control characters
         CTLCHAR.0 = 1 if SET CTLCHAR OFF; else 3
         CTLCHAR.1 = ON|OFF
         CTLCHAR.2 = escape character
         CTLCHAR.3 = list of control characters (if any)
<B>CTLchar</B> c
         Is character c in a protected status
         CTLCHAR.0 = 1 if SET CTLCHAR OFF;
                     0 if SET CTLCHAR not OFF but this char not defined;
                     else 3
         CTLCHAR.1 = PROTECT|NOPROTECT|OFF
         CTLCHAR.2 = color
         CTLCHAR.3 = extended highlighting
         CTLCHAR.4 = HIGH|NOHIGH|INVISIBLE
         CTLCHAR.5 = programmed symbol set
<B>CURLine</B>  Information about the current line
         CURLINE.1 = M[+|-]n | [-]n (position; M=middle of screen)
         CURLINE.2 = actual line number on screen
         CURLINE.3 = contents of line in file (null if at TOF or EOF)
         CURLINE.4 = ON if line changed or inserted in session; else OFF
         CURLINE.5 = OLD if line not inserted this session;
                     OLD CHANGED if not inserted and changed
                     NEW if inserted in this session;
                     NEW CHANGED if inserted and changed
           If using a typewriter terminal, then same results except:
         CURLINE.1 = -1
         CURLINE.2 = -1
<B>CURSor</B>   Where is the cursor
           Current info is where cursor would be if screen displayed now;
           original info is where cursor was when screen was read
         CURSOR.1 = current line number on screen
         CURSOR.2 = current column number on screen
         CURSOR.3 = current line number in file; or -1 if not in file
         CURSOR.4 = current column number in file; or -1 if not in file
         CURSOR.5 = original line number on screen
         CURSOR.6 = original column number on screen
         CURSOR.7 = original line number in file; or -1 if not in file
         CURSOR.8 = original column number in file; or -1 if not in file
         CURSOR.9 = highest priority (or zero)
           If screen not yet displayed, then CURSOR.8=0 and CURSOR.9=0
<B>DISPlay</B>  Range of selection levels included in display
         DISPLAY.1 = start of display range
         DISPLAY.2 = end of display range
<B>EDIRName</B> Entry (SFS) directory name containing file when first loaded
         EDIRNAME.1 = entry directory name; or null for a minidisk file
<B>EFMode</B>   Entry filemode (when file was first loaded)
         EFMODE.1 = filemode (two characters)
<B>EFName</B>   Entry filename (when file was first loaded)
         EFNAME.1 = filename (eight characters)
<B>EFType</B>   Entry filetype (when file was first loaded)
         EFTYPE.1 = filetype (eight characters)
<B>ENTer</B>    Enter key definition
         ENTER.1 = BEFORE|AFTER|ONLY|IGNORE
         ENTER.2 = enter key definition
<B>EOF</B>      Is line pointer at end-of-file (or end-of-range) line?
         EOF.1 = ON if at EOF; else OFF
<B>EOL</B>      Is column pointer at end-of-line column (zone2+1)?
         EOL.1 = ON if at EOL; else OFF
<B>ESCape</B>   Escape character definition
         ESCAPE.1 = ON|OFF
         ESCAPE.2 = escape character
<B>ETARBCH</B>  Extended arbitrary character definition
         ETARBCH.1 = ON|OFF
         ETARBCH.2 = extended arbitrary character, enclosed by SO/SI chars
<B>ETMODE</B>   Extended (DBCS) mode
         ETMODE.1 = ON|OFF
<B>FILler</B>   Definition of the filler character
         FILLER.1 = filler character
<B>FLscreen</B> File lines on screen
         FLSCREEN.1 = line number of first line of file displayed on screen
         FLSCREEN.2 = line number of last line of file displayed on screen
<B>FMode</B>    Current filemode
         FMODE.1 = filemode (two characters)
<B>FName</B>    Current filename
         FNAME.1 = filename (eight characters)
<B>FType</B>    Current filetype
         FTYPE.1 = filetype (eight characters)
<B>FULLread</B> Sense null characters in lines (like CMS SET FULLREAD)
         FULLREAD.1 = ON|OFF
<B>HEX</B>      Allow hexadecimal in strings and targets (LOCATE/x'FF'/)
         HEX.1 = ON|OFF
<B>IMage</B>    Handling of tab and backspace characters during input
         IMAGE.1 = ON|OFF|CANON
<B>IMPcmscp</B> Implicit CMS/CP mode
         IMPCMSCP.1 = ON|OFF
<B>INPmode</B>  In input mode?
         INPMODE.1 = ON|OFF
<B>LASTLorc</B> Contents of last-locate-or-change buffer
         LASTLORC.1 = contents of last-locate-or-change buffer; or null
<B>LASTmsg</B>  Last message issued by editor (message is recorded even when
         SET MSGMODE OFF, but not when CP SET EMSG OFF is in effect)
         LASTMSG.1 = last message issued; or null
<B>LENgth</B>   Length of current line, from column 1 through truncation column
         LENGTH.1 = length, excluding trailing blanks; 0 if TOF or EOF
<B>LIBName</B>  Library filename while editing a member of a CMS library
         LIBNAME.1 = filename; blanks if not editing a member of a library
<B>LIBType</B>  Library filetype while editing a member of a CMS library
         LIBTYPE.1 = filetype; blanks if not editing a member of a library
<B>LIne</B>     Line number in file of current line
         LINE.1 = line number in file; 0 if at TOF; 1+lines if at EOF
<B>LINENd</B>   Line end character status
         LINEND.1 = ON|OFF
         LINEND.2 = linend character
<B>LOCk</B>     Was file locked when first loaded (even if lock since dropped)
         LOCK.1 = ON|OFF
<B>LRecl</B>    Logical record length of file being edited
         LRECL.1 = lrecl
<B>LScreen</B>  Logical screen size and location
         LSCREEN.1 = number of lines on logical screen
         LSCREEN.2 = number of columns on logical screen
         LSCREEN.3 = line number of top-left corner of logical on virtual
         LSCREEN.4 = column number of top-left corner of logical on virtual
         LSCREEN.5 = number of lines in virtual screen
         LSCREEN.6 = number of columns in virtual screen
<B>MACRO</B>    Prefer like-named macros to subcommands
         MACRO.1 = ON|OFF
<B>MASK</B>     Current mask line
         MASK.1 = mask definition
<B>MEMber</B>   Editing a member of a CMS library? (MEMBER option was specified?)
         MEMBER.1 = ON if editing member of a CMS library; or OFF
<B>MSGLine</B>  Message line status and location
         MSGLINE.1 = ON|OFF
         MSGLINE.2 = M[+|-]n | [-]n (position; M=middle of screen)
         MSGLINE.3 = maximum number of lines that msgline can expand to
         MSGLINE.4 = OVERLAY; or null
<B>MSGMode</B>  Message mode status
         MSGMODE.1 = ON|OFF
         MSGMODE.2 = LONG|SHORT
<B>NBFile</B>   Number of files currently being edited
         NBFILE.1 = number of files in ring
<B>NBScope</B>  Number of lines in file within current scope
         NBSCOPE.1 = number of lines within the current scope
         NBSCOPE.2 = position of the current line within the scope
<B>NONDisp</B>  Nondisp character
         NONDISP.1 = nondisp character
<B>NULls</B>    Replace trailing blanks with nulls (easier to use 3270 Ins mode)
         NULLS.1 = ON|OFF
<B>NUMber</B>   Number file lines in prefix area
         NUMBER.1 = ON|OFF
<B>PA[*]</B>    Definitions of all PA keys
         PA1.1 = BEFORE|AFTER|ONLY|IGNORE
         PA1.2 = PA1 key definition
         PA2.1 = BEFORE|AFTER|ONLY|IGNORE
         PA2.2 = PA2 key definition
         PA3.1 = BEFORE|AFTER|ONLY|IGNORE
         PA3.2 = PA3 key definition
<B>PAn</B>      Definition of one PA key (where n from 1 to 3)
         PAn.1 = BEFORE|AFTER|ONLY|IGNORE
         PAn.2 = key definition
<B>PACK</B>     Compress file records when file is saved
         PACK.1 = ON|OFF
<B>PENDing</B> [BLOCK] [OLDNAME] name|* [t1[t2]]
         Information from the pending list
           BLOCK option means check list for block entries only
           OLDNAME option means name specified is original name (see .3)
           Specify either a name or asterisk meaning first entry in list
           If targets are omitted, entire file is searched
           Target1 specifies starting line for search (relative to TOF)
           Target2 specifies last line for search (relative to target1)
           If target specified but not found, EXTRACT return code = 2
         PENDING.0 = 0 if no pending entry found; else 7
         PENDING.1 = line number in the file
         PENDING.2 = name entered in the prefix area
         PENDING.3 = original name of cmd/macro after synonym resolution
         PENDING.4 = BLOCK if prefix block entry in pending list; else null
         PENDING.5 = first operand accompanying prefix; or null
         PENDING.6 = second operand accompanying prefix; or null
         PENDING.7 = third operand accompanying prefix; or null
<B>PF[*]</B>    Definitions of all PF keys
         PF1.1 = BEFORE|AFTER|ONLY|IGNORE
         PF1.2 = PF1 key definition
         PF2.1 = BEFORE|AFTER|ONLY|IGNORE
         PF2.2 = PF2 key definition
         ...
         PF24.1 = BEFORE|AFTER|ONLY|IGNORE
         PF24.2 = PF24 key definition
<B>PFn</B>      Definition of one PF key (when n from 1 to 24)
         PFn.1 = BEFORE|AFTER|ONLY|IGNORE
         PFn.2 = key definition
<B>Point</B>    Symbolic name(s) assigned to the current line
         POINT.0 = 1; or 0 if no names assigned
         POINT.1 = line number and up to last 100 names assigned to it
<B>Point</B> *  All lines with symbolic names defined, starting at top of file
         POINT.0 = number of lines with names; or 0 if none
         POINT.1 = first named line number and all names assigned to it
         POINT.n = last named line number and all names assigned to it
<B>PREfix</B>   State of prefix area
         PREFIX.1 = ON|OFF|NULLS
         PREFIX.2 = RIGHT|LEFT
<B>PREfix</B> Synonym name
         Original name associated with specified prefix subcommand or macro
         PREFIX.1 = oldname (before synonym resolution)
<B>PREfix</B> Synonym *
         Both old and new names of all synonyms for prefix cmds/macros
         PREFIX.n = newname oldname
<B>RANge</B>    Line numbers of the top and bottom of the range
         RANGE.1 = line number of the first line in range
         RANGE.2 = line number of the last line in range
<B>RECFm</B>    What is record format of current file
         RECFM.1 = F|V|FP|VP
<B>REMOte</B>   Is a remote terminal being used
         REMOTE.1 = ON|OFF
<B>RESERved</B> Line numbers of screen lines currently reserved
         RESERVED.0 = 1 (except RESERVED.0 = 0 when no lines are reserved)
         RESERVED.1 = list of reserved line numbers (RESERVED.0=0 if none)
<B>RING</B>     Number of files you are editing and file identification of each
         RING.1 = number of distinct files in ring (maybe not RING.0-1)
         RING.2 = file identification line of the first file
         RING.n = file identification line of the nth-1 file
<B>SCALe</B>    State of scale display and position of scale line on screen
         SCALE.0 = 3 (except SCALE.0 = 2 when SET SCALE OFF)
         SCALE.1 = ON|OFF (state)
         SCALE.2 = M[+|-]n | [-]n (position; M=middle of screen)
         SCALE.3 = line number on screen
<B>SCOPE</B>    Display scope (see SET SCOPE and SET DISPLAY)
         SCOPE.1 = ALL|DISPLAY
<B>SCReen</B>   Attributes of screen(s) defined by SET SCREEN
         SCREEN.n = SIZE ...|WIDTH ...|DEFINE ... attributes
<B>SELect</B>   Selection level of current line and max level for file
         SELECT.1 = selection level of current line
         SELECT.2 = maximum selection level in the file
<B>Seq8</B>     Was NOSEQ8 option issued by XEDIT command or LOAD subcommand
         SEQ8.1 = OFF if NOSEQ8 option, else ON
<B>SERial</B>   Information from SET SERIAL
         SERIAL.1 = serial prefix or OFF
         SERIAL.2 = increment
         SERIAL.3 = start
<B>SHADow</B>   Are shadow lines displayed
         SHADOW.1 = ON|OFF
<B>SIDcode</B>  String from SIDCODE option of XEDIT command or LOAD subcommand
         SIDCODE.1 = Eight-character sidcode string (or eight blanks)
<B>SIZe</B>     Size of file being edited
         SIZE.1 = number of records in file being edited
<B>SPAN</B>     Concatenate lines when matching string targets?
         SPAN.1 = ON|OFF
         SPAN.2 = BLANK|NOBLANK
         SPAN.3 = number of consecutive file lines that string can span
<B>SPILL</B>    Spill (as opposed to truncate) lines when too long
         SPILL.1 = ON|OFF|WORD
<B>STAY</B>     Stay put (as opposed to EOF) if target not found
         STAY.1 = ON|OFF
<B>STReam</B>   Search entire file for column target (as opposed to just curline)
         STREAM.1 = ON|OFF
<B>SYNonym</B> name
         Definition of specified synonym
         SYNONYM.1 = synonym name
         SYNONYM.2 = length of minimum abbreviation
         SYNONYM.3 = definition
         SYNONYM.4 = linend character (if specified); or null
           If synonym not defined, then
         SYNONYM.1 = name
         SYNONYM.2 = length of name
         SYNONYM.3 = name
         SYNONYM.4 = null
<B>SYNonym</B> *
         Definitions of all defined synonyms
         SYNONYM.n = name abbreviation [LINEND char] definition
<B>TABLine</B>  Status of tab line
         TABLINE.0 = 3 (except TABLINE.0 = 1 when SET TABLINE OFF)
         TABLINE.1 = ON|OFF (state)
         TABLINE.2 = M[+|-]n | [-]n (position; M=middle of screen)
         TABLINE.3 = line number on screen
<B>TABS</B>     Tab column numbers
         TABS.1 = tab column numbers
<B>TARGet</B>   Position of last string that matched last LOCATE or CLOCATE target
         TARGET.1 = line number of first character
         TARGET.2 = column number of first character
         TARGET.3 = line number of last character
         TARGET.4 = column number of last character
<B>TERMinal</B> Terminal type
         TERMINAL.1 = DISPLAY|TYPEWRITER
<B>TEXT</B>     Text state
         TEXT.1 = ON|OFF
<B>TOF</B>      Is line pointer at top-of-file (or top-of-range) line?
         TOF.1 = ON if at TOF; else OFF
<B>TOFEOF</B>   Are TOF and EOF pseudo-lines being displayed?
         TOFEOF.1 = ON|OFF
<B>TOL</B>      Is column pointer at top-of-line (reached zone1-1)?
         TOFEOF.1 = ON|OFF
<B>TRANSLat</B> Has user defined pairs of uppercase translate characters
         TRANSLAT.1 = ON|OFF
<B>TRunc</B>    Truncation column number
         TRUNC.1 = truncation column number
<B>UNIQueid</B> Unique identifier associated with this file (AUTOSAVE filename)
         UNIQUEID.1 = rrrnnnnn (r=recursion level, n=autosave number)
<B>UNTil</B>    Filetype up thru which updates were applied
         UNTIL.1 = filetype (if option was specified), or blanks
<B>UPDate</B>   Was UPDATE option specified by XEDIT command or LOAD subcommand
         UPDATE.1 = ON|OFF
<B>VARblank</B> Will target like /a b/ match text like "a     b"?
         VARBLANK.1 = ON|OFF
<B>Verify</B>   Information about verification columns
         VERIFY.1 = ON|OFF
         VERIFY.2 = column number pairs (possibly including H prefix)
<B>VERShift</B> Relative position of screen over file (see LEFT and RIGHT)
         VERSHIFT.1 = [-]n
<B>Width</B>    Value of WIDTH option to XEDIT command or LOAD subcommand
         WIDTH.1 = width of file
<B>WINdow</B>   Name of virtual screen and window that XEDIT will use
         WINDOW.1 = window name or blanks (for non-display terminals)
<B>WRap</B>     Will LOCATE wrap around from end of file
         WRAP.1 = ON|OFF
<B>Zone</B>     Left and right zone column numbers
         ZONE.1 = left zone column number
         ZONE.2 = right zone column number
<HR SIZE=1>Most operands are related to the corresponding SET OPERAND subcommand
<HR SIZE=1>In all cases, variable OPERAND.0 is set to number of variables returned
<HR SIZE=1>On a typewriter terminal, OPERAND.0=0 for the following operands:
   CMDLINE CURSOR FLSCREEN LSCREEN MSGLINE SCALE SCREEN TABLINE
<HR SIZE=1></PRE>

<A NAME=read><H2>READ Subcommand</H2></A>

<PRE>
Causes "Macro-read n File(s)" to be displayed in the XEDIT status area
Command terminates when an interrupt (Enter/PA/PF) key is pressed
READ is a no-op if anything is already in the console stack
From a typewriter terminal, READ stacks just the command line
<HR SIZE=1><B>READ</B> [Cmdline] [Tag|Notag]
          Stack just the command line (and interrupt key)
<B>READ</B> All [Number] [Tag|Notag]
          Stack all lines changed plus the command line (and interrupt key)
<B>READ</B> Nochange [Number] [Tag|Notag]
          Like ALL but changes are not made to file, just stacked
<HR SIZE=1>Options:  Number    Prefix file lines with their line numbers
          Notag     This is the default
          Tag       Add origin of line to beginning of each line stacked
<HR SIZE=1>Tags:     CMD  CommandLineString
          ETK  EnterKeyDefinition
          FIL  LineNumber ColumnNumber [FileLineNumber] FileLineString
          PAK  PaKeyNumber PaKeyDefinition
          PFK  PfKeyNumber PfKeyDefinition
          PRF  LineNumber ColumnNumber [FileLineNumber] PrefixAreaString
          RES  LineNumber ColumnNumber ReservedFieldString
<HR SIZE=1></PRE>

<A NAME=sos><H2>SOS Operands</H2></A>

<PRE>
<B>ALarm</B>          Ring terminal alarm next time display is refreshed
<B>CLEAR</B>          Clear the screen
<B>LINEAdd</B>        Add blank line after line pointed to by cursor (PF2)
<B>LINEDel</B>        Delete line pointed to by cursor
<B>NUlls</B>          Toggle setting of nulls option on line pointed to by cursor
<B>NUlls</B> ON       Change trailing blanks to nulls on line pointed to by cursor
<B>NUlls</B> OFF      Change trailing nulls to blanks on line pointed to by cursor
<B>PFn</B>            Depress PF key n; data assigned to key stacked LIFO
<B>POP</B>            Remove top position in cursor stack and place cursor there
<B>PUsh</B>           Save current cursor position in LIFO cursor stack (5 deep)
<B>TABB</B> [1|n]     Move cursor back n tab positions (see SET TABS)
<B>TABCmd</B>         Move cursor to command line for logical screen now in
<B>TABCMDB</B> [1|n]  Move cursor backward to command line of prev logical screen
<B>TABCMDF</B> [1|n]  Move cursor forward to command line of next logical screen
<B>TABF</B> [1|n]     Move cursor forward n tab positions (see SET TABS)
</PRE>

<A NAME=targets><H2>Targets</H2></A>

<PRE>
<B>:</B>n          Absolute file line number
<B>.</B>name       Absolute file line name (see SET POINT and prefix command .)
n           Relative displacement from current line (down)
<B>+</B>n          Relative displacement from current line (down)
<B>-</B>n          Relative displacement from current line (up)
<B>*</B>           End of file
<B>+*</B>          End of file
<B>-*</B>          Top of file
<B>//</B>          Advance line pointer by one line
<B>/</B>str[/]     Next line containing occurrence of string
<B>+/</B>str[/]    Next line containing occurrence of string
<B>-/</B>str[/]    Previous line containing occurrence of string
<B>&#172;/</B>str[/]    Next line not containing occurrence of string
<B>+&#172;/</B>str[/]   Next line not containing occurrence of string
<B>-&#172;/</B>str[/]   Previous line not containing occurrence of string
/s1/<B>&amp;</B>/s2/   Next line containing occurrences of both strings
/s1/<B>|</B>/s2/   Next line containing occurrence of either string
<B>-/</B>x'cc'/    Previous line containing hex character (only if SET HEX ON)
<HR SIZE=1>Column targets are similar except:
            No named (.) columns
            + means right, - means left
            * means EOL, -* means TOL
<HR SIZE=1>SET operands affecting targets:
            ARBCHAR, CASE, ETARBCH, HEX, SPAN, STAY, VARBLANK, WRAP
<HR SIZE=1>Precedence: (first) &#172; &amp; | (last)
<HR SIZE=1></PRE>

<A NAME=defaults><H2>Defaults by Filetype</H2></A>

<TABLE BORDER=4>
<TR><TH ALIGN=left>Filetype</TH><TH>SERIAL</TH><TH>TRUNC</TH><TH>LRECL</TH><TH>RECFM</TH><TH>VERIFY</TH><TH>ESCAPE</TH><TH>CASE</TH><TH>SPILL</TH><TH>IMAGE</TH></TR>
<TR><TD>$EXEC</TD><TD>ON</TD><TD>72</TD><TD>80</TD><TD>F</TD><TD>72</TD><TD>/</TD><TD>M</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>$XEDIT</TD><TD>ON</TD><TD>72</TD><TD>80</TD><TD>F</TD><TD>72</TD><TD>/</TD><TD>M</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>AMSERV</TD><TD>ON</TD><TD>72</TD><TD>80</TD><TD>F</TD><TD>T</TD><TD>/</TD><TD>U</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>ASM3705</TD><TD>ON</TD><TD>71</TD><TD>80</TD><TD>F</TD><TD>T</TD><TD>/</TD><TD>U</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>ASSEMBLE</TD><TD>ON</TD><TD>71</TD><TD>80</TD><TD>F</TD><TD>72</TD><TD>/</TD><TD>U</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>BASDATA</TD><TD>OFF</TD><TD>255</TD><TD>255</TD><TD>V</TD><TD>T</TD><TD>/</TD><TD>M</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>BASIC</TD><TD>OFF</TD><TD>156</TD><TD>156</TD><TD>V</TD><TD>T</TD><TD>/</TD><TD>M</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>CNTRL</TD><TD>OFF</TD><TD>80</TD><TD>80</TD><TD>F</TD><TD>T</TD><TD>/</TD><TD>U</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>COBOL</TD><TD>ON</TD><TD>72</TD><TD>80</TD><TD>F</TD><TD>T</TD><TD>/</TD><TD>U</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>COPY</TD><TD>ON</TD><TD>71</TD><TD>80</TD><TD>F</TD><TD>T</TD><TD>/</TD><TD>U</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>DLCS</TD><TD>ON</TD><TD>72</TD><TD>80</TD><TD>F</TD><TD>72</TD><TD>/</TD><TD>U</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>DIRECT</TD><TD>ON</TD><TD>72</TD><TD>80</TD><TD>F</TD><TD>T</TD><TD>/</TD><TD>U</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>ESERV</TD><TD>ON</TD><TD>71</TD><TD>80</TD><TD>F</TD><TD>T</TD><TD>/</TD><TD>U</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>EXEC</TD><TD>OFF</TD><TD>130</TD><TD>130</TD><TD>V</TD><TD>T</TD><TD>/</TD><TD>U</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>FORTRAN</TD><TD>ON</TD><TD>72</TD><TD>80</TD><TD>F</TD><TD>T</TD><TD>/</TD><TD>U</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>FREEFORT</TD><TD>OFF</TD><TD>81</TD><TD>81</TD><TD>V</TD><TD>T</TD><TD>/</TD><TD>U</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>GCS</TD><TD>OFF</TD><TD>130</TD><TD>130</TD><TD>V</TD><TD>T</TD><TD>/</TD><TD>U</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>GROUP</TD><TD>ON</TD><TD>71</TD><TD>80</TD><TD>F</TD><TD>72</TD><TD>/</TD><TD>U</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>JOB</TD><TD>OFF</TD><TD>80</TD><TD>80</TD><TD>F</TD><TD>T</TD><TD>+</TD><TD>U</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>LISTING</TD><TD>OFF</TD><TD>121</TD><TD>121</TD><TD>V</TD><TD>T</TD><TD>/</TD><TD>U</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>MACLIB</TD><TD>OFF</TD><TD>71</TD><TD>80</TD><TD>F</TD><TD>72</TD><TD>/</TD><TD>U</TD><TD>OFF</TD><TD>OFF</TD></TR>
<TR><TD>MACRO</TD><TD>ON</TD><TD>71</TD><TD>80</TD><TD>F</TD><TD>72</TD><TD>/</TD><TD>U</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>MEMBER</TD><TD>ON</TD><TD>71</TD><TD>80</TD><TD>F</TD><TD>72</TD><TD>/</TD><TD>U</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>MEMO</TD><TD>OFF</TD><TD>80</TD><TD>80</TD><TD>V</TD><TD>T</TD><TD>/</TD><TD>M</TD><TD>WORD</TD><TD>ON</TD></TR>
<TR><TD>MODULE</TD><TD>OFF</TD><TD>80</TD><TD>80</TD><TD>V</TD><TD>72</TD><TD>/</TD><TD>M</TD><TD>OFF</TD><TD>OFF</TD></TR>
<TR><TD>NAMES</TD><TD>OFF</TD><TD>255</TD><TD>255</TD><TD>V</TD><TD>T</TD><TD>/</TD><TD>M</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>NETLOG</TD><TD>OFF</TD><TD>255</TD><TD>255</TD><TD>V</TD><TD>T</TD><TD>/</TD><TD>M</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>NOTE</TD><TD>OFF</TD><TD>132</TD><TD>132</TD><TD>V</TD><TD>T</TD><TD>/</TD><TD>M</TD><TD>WORD</TD><TD>ON</TD></TR>
<TR><TD>NOTEBOOK</TD><TD>OFF</TD><TD>132</TD><TD>132</TD><TD>V</TD><TD>T</TD><TD>/</TD><TD>M</TD><TD>WORD</TD><TD>ON</TD></TR>
<TR><TD>PASCAL</TD><TD>OFF</TD><TD>72</TD><TD>72</TD><TD>V</TD><TD>T</TD><TD>/</TD><TD>M</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>PLI</TD><TD>ON</TD><TD>72</TD><TD>80</TD><TD>F</TD><TD>T</TD><TD>/</TD><TD>U</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>PLIOPT</TD><TD>ON</TD><TD>72</TD><TD>80</TD><TD>F</TD><TD>T</TD><TD>/</TD><TD>U</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>SCRIPT</TD><TD>OFF</TD><TD>132</TD><TD>132</TD><TD>V</TD><TD>T</TD><TD>/</TD><TD>M</TD><TD>WORD</TD><TD>CANON</TD></TR>
<TR><TD>TEXT</TD><TD>OFF</TD><TD>80</TD><TD>80</TD><TD>F</TD><TD>72</TD><TD>/</TD><TD>M</TD><TD>OFF</TD><TD>OFF</TD></TR>
<TR><TD>UPDATE</TD><TD>ON</TD><TD>71</TD><TD>80</TD><TD>F</TD><TD>72</TD><TD>/</TD><TD>U</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>UPDT</TD><TD>ON</TD><TD>71</TD><TD>80</TD><TD>F</TD><TD>72</TD><TD>/</TD><TD>U</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>VSBASIC</TD><TD>OFF</TD><TD>80</TD><TD>80</TD><TD>F</TD><TD>T</TD><TD>/</TD><TD>U</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>VSBDATA</TD><TD>OFF</TD><TD>132</TD><TD>132</TD><TD>V</TD><TD>T</TD><TD>/</TD><TD>U</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>XEDIT</TD><TD>OFF</TD><TD>255</TD><TD>255</TD><TD>V</TD><TD>T</TD><TD>/</TD><TD>U</TD><TD>OFF</TD><TD>ON</TD></TR>
<TR><TD>Other</TD><TD>OFF</TD><TD>80</TD><TD>80</TD><TD>F</TD><TD>**</TD><TD>/</TD><TD>U</TD><TD>OFF</TD><TD>ON</TD></TR>
<CAPTION ALIGN=bottom>VERIFY: T means trunc column; ** means screen size</CAPTION>
</TABLE>
<P>

<P><HR SIZE=4 NOSHADE></P>

<CENTER>
