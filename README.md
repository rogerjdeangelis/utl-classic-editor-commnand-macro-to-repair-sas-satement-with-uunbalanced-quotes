# utl-classic-editor-commnand-macro-to-repair-sas-satement-with-uunbalanced-quotes
classic editor commnand macro to repair sas satements with unbalanced quotes 
    classic editor commnand macro to repair sas satements with unbalanced quotes                                                           
                                                                                                                                           
    Also see my performance package below                                                                                                  
                                                                                                                                           
    github                                                                                                                                 
    https://tinyurl.com/yxcjxwpo                                                                                                           
    https://github.com/rogerjdeangelis/utl-classic-editor-commnand-macro-to-repair-sas-satement-with-uunbalanced-quotes                    
                                                                                                                                           
    FYI: I don't believe you can use bytes 'FE'x and 'FF'x with prxchage within a macro.                                                   
    SAS seems to use these to enable the myriad number of macro quoting functions?                                                         
                                                                                                                                           
    SAS Forum                                                                                                                              
    https://tinyurl.com/yyynkvy3                                                                                                           
    https://communities.sas.com/t5/SAS-Programming/Remove-unbalanced-parentheses-in-a-string/m-p/680071                                    
                                                                                                                                           
    Thanks Freelance Reinhard and Shmuel                                                                                                   
    https://communities.sas.com/t5/user/viewprofilepage/user-id/32733                                                                      
    https://communities.sas.com/t5/user/viewprofilepage/user-id/88384                                                                      
                                                                                                                                           
    macros                                                                                                                                 
    https://tinyurl.com/y9nfugth                                                                                                           
    https://github.com/rogerjdeangelis/utl-macros-used-in-many-of-rogerjdeangelis-repositories                                             
                                                                                                                                           
    Everthing you ever wanted to know about the classic 1980s SAS editor                                                                   
    https://github.com/rogerjdeangelis?tab=repositories&q=classic+editor&type=&language=                                                   
                                                                                                                                           
    /*                   _                                                                                                                 
    (_)_ __  _ __  _   _| |_                                                                                                               
    | | `_ \| `_ \| | | | __|                                                                                                              
    | | | | | |_) | |_| | |_                                                                                                               
    |_|_| |_| .__/ \__,_|\__|                                                                                                              
            |_|                                                                                                                            
    */                                                                                                                                     
                                                                                                                                           
    data class;                                                                                                                            
                                                                                                                                           
      set sashelp.class;                                                                                                                   
         where ( age=14 ) and (sex = "M" ) ) ;                                                                                             
                                                                                                                                           
    run;quit;                                                                                                                              
                                                                                                                                           
    ERROR: Syntax error while parsing WHERE clause.                                                                                        
                                                                                                                                           
    /*           _               _                                                                                                         
      ___  _   _| |_ _ __  _   _| |_                                                                                                       
     / _ \| | | | __| `_ \| | | | __|                                                                                                      
    | (_) | |_| | |_| |_) | |_| | |_                                                                                                       
     \___/ \__,_|\__| .__/ \__,_|\__|                                                                                                      
                    |_|                                                                                                                    
    */                                                                                                                                     
                                                                                                                                           
    Corrected code is in the log. You need to copy and pase into your program                                                              
                                                                                                                                           
    I think we lost the ability to read the 'cursor' position                                                                              
    with the downgrade, accompaning the rewrite of classic editor into C code.                                                             
    Note still do have a dysfunctional script 'cursor' command.                                                                            
    Would be nice to correct the code in place.                                                                                            
                                                                                                                                           
                                                                                                                                           
    CORRECTED                                                                                                                              
    =========                                                                                                                              
                                                                                                                                           
    where ( age=14 ) and (sex = "M" );                                                                                                     
                                                                                                                                           
    data class;                                                                                                                            
                                                                                                                                           
      set sashelp.class;                                                                                                                   
         where ( age=14 ) and (sex = "M" );                                                                                                
                                                                                                                                           
    run;quit;                                                                                                                              
                                                                                                                                           
    OTE: There were 2 observations read from the data set SASHELP.CLASS.                                                                   
         WHERE (age=14) and (sex='M');                                                                                                     
    OTE: The data set WORK.CLASS has 2 observations and 5 variables.                                                                       
                                                                                                                                           
    /*         _       _   _                                                                                                               
     ___  ___ | |_   _| |_(_) ___  _ __                                                                                                    
    / __|/ _ \| | | | | __| |/ _ \| `_ \                                                                                                   
    \__ \ (_) | | |_| | |_| | (_) | | | |                                                                                                  
    |___/\___/|_|\__,_|\__|_|\___/|_| |_|                                                                                                  
                                                                                                                                           
    */                                                                                                                                     
                                                                                                                                           
    /* location in github                                                                                                                  
    utl_perpac.sas                                                                                                                         
    https://tinyurl.com/y4jtq4vv                                                                                                           
    https://raw.githubusercontent.com/rogerjdeangelis/utl-macros-used-in-many-of-rogerjdeangelis-repositories/master/utl_perpac.sas        
    */                                                                                                                                     
                                                                                                                                           
    * If you want to try it without actually saving it in your autocall librar then just run this;                                         
                                                                                                                                           
    filename perpac url "https://tinyurl.com/y4jtq4vv";                                                                                    
    %include perpac;                                                                                                                       
                                                                                                                                           
    FIXING PARENS                                                                                                                          
                                                                                                                                           
    You need to hilite the problematic  where clause '( age=14 ) and (sex = "M" ) )'                                                       
    and type 'par' on the command line (or put it on a mouse action or function key)                                                       
                                                                                                                                           
    You need to place this code in your autocall library or run it interactively..                                                         
                                                                                                                                           
    %macro par / cmd;                                                                                                                      
       store;note;notesubmit '%para;';                                                                                                     
       run;                                                                                                                                
    %mend par;                                                                                                                             
                                                                                                                                           
    %macro para;                                                                                                                           
         filename clp clipbrd ;                                                                                                            
         data _null_;                                                                                                                      
           infile clp end=dne;                                                                                                             
           input;                                                                                                                          
           putlog _infile_;                                                                                                                
           string=_infile_;                                                                                                                
           do until (status=9);                                                                                                            
              link scan;                                                                                                                   
           end;                                                                                                                            
           string = translate(string,'  ()','()'||"FAFB"x);                                                                                
           put string=;                                                                                                                    
    RETURN;                                                                                                                                
    SCAN:                                                                                                                                  
        do i=1 to length(string);                                                                                                          
           status = 9;                                                                                                                     
           if substr(string,i,1) = '(' then p = i;                                                                                         
           if substr(string,i,1) = ')' and p>0                                                                                             
              then do;                                                                                                                     
              substr(string,p,1) = 'FA'x;                                                                                                  
              substr(string,i,1) = 'FB'x;                                                                                                  
              p=0;                                                                                                                         
              status=0;                                                                                                                    
              leave;                                                                                                                       
           end;                                                                                                                            
        end;                                                                                                                               
    RETURN;                                                                                                                                
    RUN;                                                                                                                                   
    %mend para;                                                                                                                            
                                                                                                                                           
                                                                                                                                           
    /*____ _  _                                                   _                                                                        
    |___ /| || |     ___ ___  _ __ ___  _ __ ___   __ _ _ __   __| |___                                                                    
      |_ \| || |_   / __/ _ \| `_ ` _ \| `_ ` _ \ / _` | `_ \ / _` / __|                                                                   
     ___) |__   _| | (_| (_) | | | | | | | | | | | (_| | | | | (_| \__ \                                                                   
    |____/   |_|    \___\___/|_| |_| |_|_| |_| |_|\__,_|_| |_|\__,_|___/                                                                   
                                                                                                                                           
    */                                                                                                                                     
                                                                                                                                           
                                                                                                                                           
    Below are a set of 34 command macros that can greatly increase your programming performance.                                           
                                                                                                                                           
    I have over 20 of these performance command macros mapped to my logitect G203 5 button mouse                                           
    and many more mapped to function keys, and if this in not enough the same                                                              
    command macros can be called with and without arguments from the SAS classic editor command line.                                      
                                                                                                                                           
    All of SAS, R, Python and Perl can executed directly                                                                                   
    on the 1980s classic editor command line or on text the in the SAS classic (1980s) editor.                                             
    Python functions and code can be alsi be executed by mouse keys.                                                                       
                                                                                                                                           
    I don't believe this functionality is available in any of the later SAS editoes including                                              
    the DMS Enhanced Editor.                                                                                                               
                                                                                                                                           
    You may want to remove some of the non-commnbd macros in                                                                               
                                                                                                                                           
    https://tinyurl.com/y6yoba4o                                                                                                           
    https://github.com/rogerjdeangelis/utl-macros-used-in-many-of-rogerjdeangelis-repositories/blob/master/utl_perpac.sas                  
                                                                                                                                           
                                                                                                                                           
    /*               _                                                                                                                     
    | |__   ___  ___| |_                                                                                                                   
    | `_ \ / _ \/ __| __|                                                                                                                  
    | |_) |  __/\__ \ |_                                                                                                                   
    |_.__/ \___||___/\__|                                                                                                                  
                                                                                                                                           
    */                                                                                                                                     
                                                                                                                                           
    %inc "c:/oto/utl_perpac.sas";                                                                                                          
                                                                                                                                           
    %macro xpy     /cmd parmbuff des="type xpy step1 and get python exploded letters";                                                     
    %macro frqh    /cmd parmbuff des="Hilite table type 'frq sex*age' and get proc freq";                                                  
    %macro ls40h   /cmd des="40 obs hilited table";                                                                                        
    %macro cnth    /cmd parmbuff des="Hilite table 'cnth age' and get count distinct age";                                                 
    %macro avgh    /cmd des="Hilite a table and get proc means on all variables";                                                          
    %macro dmph    /cmd des="Hilite table get contents but with sample values for each variable";                                          
    %macro prth    /cmd des="Hilite table and type  prth "age=14" or prth 'name="John"';                                                   
    %macro conh    /cmd des="Highlight dataseta and type conh on command line. Results in output window";                                  
    %macro sumh    /cmd des="Hilite a column of numbers and get the sum min max std q1 media q3";                                          
                                                                                                                                           
    %macro debugh  /cmd des="Debug hilited macro";                                                                                         
    /*   _                          _                                                                                                      
    | |_| |__   ___   _ __ ___  ___| |_                                                                                                    
    | __| `_ \ / _ \ | `__/ _ \/ __| __|                                                                                                   
    | |_| | | |  __/ | | |  __/\__ \ |_                                                                                                    
     \__|_| |_|\___| |_|  \___||___/\__|                                                                                                   
                                                                                                                                           
    */                                                                                                                                     
    %macro cuth    /cmd des= "multiple spaces to one space - useful for aligning input data';                                              
    %macro tail    /cmd des="last 10 obs from last table";                                                                                 
    %macro tailh   /cmd des="last 10 obs hilited dataset and type tailfha for a list of 10 obs";                                           
    %macro ls40    /cmd des="40 obs last table";                                                                                           
    %macro doendh  /cmd des="Find non matching do and ends - high";                                                                        
    %macro sumv    /cmd des="Hilite a row of variable names and get the sum min max std q1 media q3";                                      
    %macro frqv    /cmd des="Hilite a variable get the frequency - works on last created table";                                           
    %macro unv     /cmd des="Hilite table and get univariate output";                                                                      
    %macro cntv    /cmd des="Hilite a variable get count distinct - works on last created table";                                          
    %macro dmp     /cmd des="Get contents like output but with sample values for each variable - last table";                              
    %macro lsal    /cmd des="List all obsevations from last table";                                                                        
    %macro frq     /cmd parmbuff des="Type 'frq sex*age' and get proc freq last tale";                                                     
    %macro cnt     /cmd parmbuff des="'cnth age' and get count distinct age on last table";  ;                                             
    %macro prt     /cmd parmbuff des=" prt sex="M" and get listing from last table";;                                                      
    %macro parh    /cmd des="Matching parentheses and sugestion to fix"                                                                    
    %macro par     /cmd des="Hilite sas statement unmatched quotes and get corrected version in log";                                      
    %macro con     /cmd des="Contets of last created table";                                                                               
    %macro lsalh   /cmd des="Type lsalh on command line. List all obs highlighted dataset";                                                
    %macro vu      /cmd des="Viewtable of last dataset created";                                                                           
    %macro vuh     /cmd des="Viewtable of highlighted dataset";                                                                            
    %macro xlsh    /cmd des="Highlight dataset and type xlsh and the dataset will appear in excel";;                                       
    %macro iota    /cmd des="APL iota function 'iota 5 and 1 2 3 4 5 will appear vertically in editor"                                     
    %macro xplo    /cmd des="type xplo ONEaTWO and exploded letters will be saved in past buffer";                                         
    %macro evlh    /cmd des="Calulator hilite 2*exp(2) and the result will appear in the log"                                              
    %macro cath    /cmd des="applies to sasuser,profile. List catalog entries in the log";                                                 
    %macro sasbat  /cmd des="Run hilited code in SAS batch";                                                                               
                                                                                                                                           
                                                                                                                                           
                                                                                                                                           
    * note yoy have to edit SASBAT;                                                                                                        
                                                                                                                                           
    %macro sasbat /cmd des="highlight code type sas7bat on command line";                                                                  
       store;note;notesubmit '%sasbath;';                                                                                                  
    %mend sasbat;                                                                                                                          
                                                                                                                                           
    %macro sasbath;                                                                                                                        
                                                                                                                                           
         %utlfkil(d:/log/__clp.sas);                                                                                                       
         %utlfkil(d:/log/__clp.log);                                                                                                       
         %utlfkil(d:/log/__clp.lst);                                                                                                       
                                                                                                                                           
      FILENAME clp clipbrd ;                                                                                                               
      DATA _NULL_;                                                                                                                         
        INFILE clp;                                                                                                                        
        INPUT;                                                                                                                             
        file "d:/log/__clp.sas";                                                                                                           
        put _infile_;                                                                                                                      
        putlof _infile_;                                                                                                                   
      RUN;quit;                                                                                                                            
                                                                                                                                           
      filename sin pipe %sysfunc(compbl("c:\PROGRA~1\SASHome\SASFoundation\9.4\sas.exe -sysin d:/log/__clp.sas                             
            -log d:/log/__clp.log -autoexec c:\oto\tut_oto.sas                                                                             
           -print d:/log/__clp.lst -config \cfg\cfgsas94m6.cfg -sasautos c:/oto"));                                                        
                                                                                                                                           
       data _null_;                                                                                                                        
         infile sin;                                                                                                                       
         input;                                                                                                                            
         put _infile_;                                                                                                                     
       run;quit;                                                                                                                           
                                                                                                                                           
       x notepad.exe d:/log/__clp.log;                                                                                                     
                                                                                                                                           
    %mend sasBath;                                                                                                                         
                                                                                                                                           
                                                                                                                                           
