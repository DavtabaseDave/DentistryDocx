Data Tables
===========

t\_Dntl\_Applicants
-------------------

The main applicants table containing Banner derived data and mutable
local data

  Attribute                              DataType        Allow Nulls?   PKey?   FKey?   Notes
  -------------------------------------- --------------- -------------- ------- ------- -------------------------
  spriden\_pidm                          int                            Yes             
  skrsain\_applicant\_no                 varchar                                        
  spriden\_id                            varchar                                        
  skrsain\_personalid                    varchar                                        
  spriden\_last\_name                    nvarchar                                       
  spriden\_first\_name                   nvarchar                                       
  spriden\_mi                            nvarchar                                       
  student\_initials                      nvarchar                                       
  spbpers\_name\_prefix                  nvarchar                                       
  spbpers\_birth\_date                   datetime                                       
  current\_age                           tinyint                                        
  age\_at\_entry                         tinyint                                        
  spbpers\_sex                           char                                           
  eth\_code                              varchar                                Yes     l\_stvethn
  sprmedi\_disa\_code                    varchar                                Yes     l\_stvdisa
  skrsain\_criminal\_conv                bit                                            
  skruccr\_ssdt\_code\_home              bit                                            
  STREET\_ADDRESS\_PH\_LINE1             nvarchar                                       
  STREET\_ADDRESS\_PH\_LINE2             nvarchar                                       
  STREET\_ADDRESS\_PH\_LINE3             nvarchar                                       
  spraddr\_city                          nvarchar                                       
  nation\_description\_ph                nvarchar                                       
  spraddr\_zip                           nvarchar                                       
  telephone\_number\_ph                  nvarchar                                       
  skbspin\_natn\_code\_legal             varchar                                Yes     l\_stvnatn
  saradap\_resd\_code                    char                                           
  skrsain\_appl\_date                    datetime                                       
  email\_address                         varchar                                        
  skbuarf\_predictedgrades               varchar                                        
  sorhsch\_sbgi\_code                    int                                    Yes     l\_stvsbgi
  skrsain\_ssdt\_code\_pared             char                                           
  skrsain\_care                          char                                           
  isActive                               bit                                            
  Query\_Sent                            bit                                            
  Query\_Deadline                        datetime        Yes                            
  extension\_deadline                    datetime        Yes                            
  isExtension                            bit                                            
  Attending\_Open\_Day                   bit                                            
  Offer\_Holder\_Visit\_Date             datetime        Yes                            
  Attended\_Pre\_Offer\_Day              bit                                            
  Attended\_Offer\_Holder\_Day           bit                                            
  Attended\_Offer\_Holder\_Visit\_Date   datetime        Yes                            
  Notes                                  varchar                                        
  Form\_Received                         bit                                            
  Email\_Ack                             bit                                            
  Entry\_Req                             bit                                            
  A2L                                    bit                                            
  International\_agent                   tinyint                                Yes     l\_International\_Agent
  isSports                               bit                                            
  isDisability                           bit                                            
  isFeesAssess                           bit                                            
  isMature                               bit                                            
  underYes8                              bit                                            
  hasDeferred                            bit                                            
  data\_source                           tinyint                                Yes     l\_data\_source
  VS                                     timestamp                                      
  CreatedDate                            smalldatetime                                  
  LastUser                               varchar                                        

Decisions
---------

Contains mostly Banner derived decision data plus some local management
data

  Attribute                       DataType        Allow Nulls?   PKey?   FKey?   Notes
  ------------------------------- --------------- -------------- ------- ------- ---------------------
  skruccr\_pidm                   int                            Yes     Yes     t\_Dntl\_Applicants
  skruccr\_choice\_type\_no       varchar                        Yes             
  skruccr\_ssdt\_code\_crse       varchar                                        
  DEGC\_CODE                      varchar                                        
  skrutop\_program                varchar                                Yes     l\_smrprle
  skruccr\_ssdt\_code\_decn       varchar                                        
  skruccr\_decision\_date         datetime        Yes                            
  skruccr\_ssdt\_code\_reply      varchar         Yes                            
  skruccr\_ssdt\_code\_cf\_decn   varchar         Yes                            
  skruccr\_ssdt\_code\_ap\_resp   varchar         Yes                            
  skruccr\_prop\_entry\_yr        smallint                       Yes             
  skruccr\_prop\_entry\_mth       smallint                                       
  skruccr\_conditions             varchar         Yes                            
  skruccr\_ssdt\_code\_entry      varchar                                        
  date\_off\_let\_sent            datetime        Yes                            
  gurmail\_code                   varchar                                        
  predicted\_grade                tinyint                                Yes     l\_Predicted\_Grade
  achieved\_grade                 tinyint                                Yes     l\_Achieved\_Grade
  reason\_for\_rejection          tinyint                                Yes     l\_Reason\_Rej
  Reason\_For\_Rej\_Notes         varchar                                        
  VS                              timestamp                                      
  CreatedDate                     smalldatetime                                  
  LastUser                        varchar                                        

t\_Dntl\_A2L\_RR
----------------

Only other Banner derived data - Access to Leeds Running Record

  Attribute                       DataType   Allow Nulls?   PKey?   FKey?   Notes
  ------------------------------- ---------- -------------- ------- ------- ---------------------
  sarchrt\_pidm                   int                       Yes     Yes     t\_Dntl\_Applicants
  spriden\_id                     varchar                                   
  skrsain\_personalid             varchar                                   
  spriden\_first\_name            nvarchar                                  
  spriden\_last\_name             nvarchar                                  
  skruccr\_ssdt\_code\_crse       varchar                   Yes             
  Programme                       varchar                                   
  A2L\_Eligibility\_Decision      varchar                                   
  saradap\_term\_code\_entry      varchar                                   
  Number\_Courses\_Applied\_For   tinyint                                   
  A2L\_Route                      varchar                                   
  A2L\_Application\_Received      datetime   Yes                            
  A2L\_Decision\_Date             datetime   Yes                            

t\_Dntl\_Academic\_Scores
-------------------------

Data imported for the different GCSE scores

  Attribute                                  DataType   Allow Nulls?   PKey?   FKey?   Notes
  ------------------------------------------ ---------- -------------- ------- ------- ---------------------
  PIDM                                       int                       Yes     Yes     t\_Dntl\_Applicants
  Scorer initials                            varchar                                   
  Std\_entry\_GCSE\_English                  char                                      
  Std\_entry\_GCSE\_Maths                    char                                      
  Std\_entry\_GCSE\_Biology\_or\_Science     char                                      
  Std\_entry\_GCSE\_Chemistry\_or\_Science   char                                      
  Std\_entry\_GCSE\_other\_1                 char                                      
  Std\_entry\_GCSE\_other\_2                 char                                      
  Std\_entry\_GCSE\_other\_3                 char                                      
  Std\_entry\_GCSE\_other\_4                 char                                      
  Std\_entry\_GCSE\_other\_5                 char                                      
  Std\_entry\_A2                             tinyint                                   
  Grad\_English\_GCSE                        char                                      
  Grad\_Maths\_GCSE                          char                                      
  Grad\_Biology\_GCSE                        char                                      
  Grad\_Chemistry\_GCSE                      char                                      
  Grad\_GCSE\_any\_1                         char                                      
  Grad\_GCSE\_Any\_2                         char                                      
  Grad\_GCSE\_total                          varchar                                   
  Grad\_Degree\_name                         char                                      
  Grad\_Degree\_classification\_Degree       char                                      
  total\_GCSE                                tinyint                                   
  Reference\_statement?                      varchar                                   
  Notes                                      varchar                                   
  Total                                      tinyint                                   

t\_Dntl\_All\_MMI\_Rankings
---------------------------

Data imported for the different MMI rankings

  Attribute                            DataType   Allow Nulls?   PKey?   FKey?   Notes
  ------------------------------------ ---------- -------------- ------- ------- ---------------------
  pidm                                 int                       Yes     Yes     t\_Dntl\_Applicants
  prog\_code                           varchar                   Yes             
  Mean\_Rank\_Task                     float                                     
  Offer\_Cutoff                        float                                     
  Station\_1\_Mean\_Percentile\_Rank   tinyint                                   
  Station\_1\_Quartile\_Rank           tinyint                           Yes     l\_Quartile\_Rank
  Station\_2\_Mean\_Percentile\_Rank   tinyint                                   
  Station\_2\_Quartile\_Rank           tinyint                           Yes     l\_Quartile\_Rank
  Station\_3\_Mean\_Percentile\_Rank   tinyint                                   
  Station\_3\_Quartile\_Rank           tinyint                           Yes     l\_Quartile\_Rank
  Station\_4\_Mean\_Percentile\_Rank   tinyint                                   
  Station\_4\_Quartile\_Rank           tinyint                           Yes     l\_Quartile\_Rank
  Station\_5\_Mean\_Percentile\_Rank   tinyint                                   
  Station\_5\_Quartile\_Rank           tinyint                           Yes     l\_Quartile\_Rank
  Station\_6\_Mean\_Percentile\_Rank   tinyint                                   
  Station\_6\_Quartile\_Rank           tinyint                           Yes     l\_Quartile\_Rank
  Station\_7\_Mean\_Percentile\_Rank   tinyint                                   
  Station\_7\_Quartile\_Rank           tinyint                           Yes     l\_Quartile\_Rank
  Station\_8\_Mean\_Percentile\_Rank   tinyint                                   
  Station\_8\_Quartile\_Rank           tinyint                           Yes     l\_Quartile\_Rank

t\_Dntl\_BMAT\_Scores
---------------------

BMAT scores after being imported and matched with an applicant record

  Attribute                 DataType   Allow Nulls?   PKey?   FKey?   Notes
  ------------------------- ---------- -------------- ------- ------- ---------------------
  pidm                      int                       Yes     Yes     t\_Dntl\_Applicants
  Section Yes Score         float                                     
  Section 2 Score           float                                     
  Essay Answered            varchar                                   
  Section 3 Content         float                                     
  Section 3 English         varchar                                   
  Section 3 English Score   float                                     
  Overall Rank              float                                     

t\_Dntl\_Definitive\_List\_Prev
-------------------------------

Instead of keeping separate tables for each of the previous year's
applicant data that has been uploaded a single table\
has been put together to store all this data in one location. This
aggregates the different scores etc and as a consequence\
many of the fields are null-able.

As the t\_Dntl\_All\_MMI\_Rankings table may contain multiple entries
for an applicant that has applied for both courses\
a compromise had to be implemented that took only the "minimum" course
code. This is to enable the t\_Dntl\_Definitive\_List\_Prev\
to be directly linked to the Previous Applicant and thus be able to be
displayed properly in the .NET client application.

  Attribute                                  DataType   Allow Nulls?   PKey?   FKey?   Notes
  ------------------------------------------ ---------- -------------- ------- ------- ---------------------------
  spriden\_pidm                              int                       Yes     Yes     t\_Dntl\_Applicants\_Prev
  A2L\_Eligibility\_Decision                 varchar                                   
  A2L\_Mark                                  varchar                                   
  A2L\_Pass                                  varchar                                   
  hasBMAT                                    varchar                                   
  LS\_1stScorer                              tinyint    Yes                            
  LS\_2ndScorer                              tinyint    Yes                            
  LS\_Final                                  tinyint    Yes                            
  MI\_1stScore                               tinyint    Yes                            
  MI\_2ndScorer                              tinyint    Yes                            
  MI\_Final                                  tinyint    Yes                            
  Ref\_1stScorer                             tinyint    Yes                            
  Ref\_2ndScorer                             tinyint    Yes                            
  Ref\_Final                                 tinyint    Yes                            
  IA\_1stScorer                              tinyint    Yes                            
  IA\_2ndScorer                              tinyint    Yes                            
  IA\_Final                                  tinyint    Yes                            
  Section 1 Score                            float      Yes                            
  Section 2 Score                            float      Yes                            
  Essay Answered                             varchar                                   
  Section 3 Content                          float      Yes                            
  Section 3 English                          varchar                                   
  Section 3 English Score                    float      Yes                            
  Overall Rank                               float      Yes                            
  Mean\_Rank\_Task                           float      Yes                            
  Offer\_Cutoff                              float      Yes                            
  Station\_1\_Mean\_Percentile\_Rank         tinyint    Yes                            
  Station\_1\_Quartile\_Rank                 tinyint    Yes                            
  Station\_2\_Mean\_Percentile\_Rank         tinyint    Yes                            
  Station\_2\_Quartile\_Rank                 tinyint    Yes                            
  Station\_3\_Mean\_Percentile\_Rank         tinyint    Yes                            
  Station\_3\_Quartile\_Rank                 tinyint    Yes                            
  Station\_4\_Mean\_Percentile\_Rank         tinyint    Yes                            
  Station\_4\_Quartile\_Rank                 tinyint    Yes                            
  Station\_5\_Mean\_Percentile\_Rank         tinyint    Yes                            
  Station\_5\_Quartile\_Rank                 tinyint    Yes                            
  Station\_6\_Mean\_Percentile\_Rank         tinyint    Yes                            
  Station\_6\_Quartile\_Rank                 tinyint    Yes                            
  Station\_7\_Mean\_Percentile\_Rank         tinyint    Yes                            
  Station\_7\_Quartile\_Rank                 tinyint    Yes                            
  Station\_8\_Mean\_Percentile\_Rank         tinyint    Yes                            
  Station\_8\_Quartile\_Rank                 tinyint    Yes                            
  MMI\_Date                                  datetime   Yes                            
  MMI\_Time                                  time       Yes                            
  MMI\_Colour                                varchar    Yes                            
  MMI\_Number                                tinyint    Yes                            
  Life\_And\_Social                          varchar    Yes                            
  Motivation\_And\_Insight                   varchar    Yes                            
  Reflective\_Skills                         varchar    Yes                            
  Interests\_And\_Achievements               varchar    Yes                            
  GLOBAL                                     varchar    Yes                            
  Overall\_Score                             varchar    Yes                            
  Leeds\_Code                                char       Yes                            
  Scorer\_initials                           varchar    Yes                            
  Std\_entry\_GCSE\_English                  char       Yes                            
  Std\_entry\_GCSE\_Maths                    char       Yes                            
  Std\_entry\_GCSE\_Biology\_or\_Science     char       Yes                            
  Std\_entry\_GCSE\_Chemistry\_or\_Science   char       Yes                            
  Std\_entry\_GCSE\_other\_1                 char       Yes                            
  Std\_entry\_GCSE\_other\_2                 char       Yes                            
  Std\_entry\_GCSE\_other\_3                 char       Yes                            
  Std\_entry\_GCSE\_other\_4                 char       Yes                            
  Std\_entry\_GCSE\_other\_5                 char       Yes                            
  Std\_entry\_A2                             tinyint    Yes                            
  Grad\_English\_GCSE                        char       Yes                            
  Grad\_Maths\_GCSE                          char       Yes                            
  Grad\_Biology\_GCSE                        char       Yes                            
  Grad\_Chemistry\_GCSE                      char       Yes                            
  Grad\_GCSE\_any\_1                         char       Yes                            
  Grad\_GCSE\_Any\_2                         char       Yes                            
  Grad\_GCSE\_total                          varchar    Yes                            
  Grad\_Degree\_name                         char       Yes                            
  Grad\_Degree\_classification\_Degree       char       Yes                            
  total\_GCSE                                tinyint    Yes                            
  Reference\_statement?                      varchar    Yes                            
  Notes                                      varchar    Yes                            
  Total                                      tinyint    Yes                            

t\_Dntl\_MMI\_Schedule
----------------------

MMI Schedule after being imported and matched with an applicant record

  Attribute   DataType   Allow Nulls?   PKey?   FKey?   Notes
  ----------- ---------- -------------- ------- ------- ---------------------
  pidm        int                       Yes     Yes     t\_Dntl\_Applicants
  Date        datetime                                  
  Time        datetime                                  
  Colour      varchar                                   
  Number      tinyint    Yes                            

t\_Dntl\_Reject\_post\_MMI
--------------------------

Rejecttion post MMI after being imported and matched with an applicant
record

  Attribute                        DataType   Allow Nulls?   PKey?   FKey?   Notes
  -------------------------------- ---------- -------------- ------- ------- ---------------------
  pidm                             int                       Yes     Yes     t\_Dntl\_Applicants
  StudentID                        varchar                                   
  Station 1 Mean Percentile Rank   float                                     
  Station 2 Mean Percentile Rank   float                                     
  Station 3 Mean Percentile Rank   float                                     
  Station 4 Mean Percentile Rank   float                                     
  Station 5 Mean Percentile Rank   float                                     
  Station 6 Mean Percentile Rank   float                                     
  Station 7 Mean Percentile Rank   float                                     
  Station 8 Mean Percentile Rank   float                                     
  Overall\_Rank                    float                                     

t\_Dntl\_RejFdbkLetter
----------------------

Data for reject with feedback emails

  Attribute                      DataType   Allow Nulls?   PKey?   FKey?   Notes
  ------------------------------ ---------- -------------- ------- ------- ---------------------
  pidm                           int                       Yes     Yes     t\_Dntl\_Applicants
  Life\_And\_Social              varchar                                   
  Motivation\_And\_Insight       varchar                                   
  Reflective\_Skills             varchar                                   
  Interests\_And\_Achievements   varchar                                   

t\_Dntl\_Results\_Sheet
-----------------------

Results sheet data after being imported and matched with an applicant's
decision record

  Attribute           DataType   Allow Nulls?   PKey?   FKey?   Notes
  ------------------- ---------- -------------- ------- ------- --------------------
  pidm                int                       Yes     Yes     t\_Dntl\_Decisions
  choice\_type\_no    varchar                   Yes     Yes     t\_Dntl\_Decisions
  prop\_entry\_yr     smallint                  Yes     Yes     t\_Dntl\_Decisions
  Full\_Offer\_Text   varchar                                   
  Condition\_Code     varchar                                   
  Late\_App           bit                                       
  IELTS               bit                                       
  RoP                 bit                                       
  Full\_Results       varchar                                   
  Decision            varchar                                   
  Result\_Position    varchar                                   
  Quality             varchar                                   
  Notes               varchar                                   
  Received\_as\_CCO   varchar                                   
  Received\_from      varchar                                   
  Old\_Course\_Code   varchar                                   

t\_Dntl\_UCAS\_Scores
---------------------

UCAS Score data after being imported and matched with an applicant
record

  Attribute                      DataType   Allow Nulls?   PKey?   FKey?   Notes
  ------------------------------ ---------- -------------- ------- ------- ---------------------
  pidm                           int                       Yes     Yes     t\_Dntl\_Applicants
  Life\_And\_Social              varchar                                   
  Motivation\_And\_Insight       varchar                                   
  Reflective\_Skills             varchar                                   
  Interests\_And\_Achievements   varchar                                   
  GLOBAL                         varchar                                   
  Overall\_Score                 varchar                                   
