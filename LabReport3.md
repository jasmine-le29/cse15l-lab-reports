## Lab Report 3

# Part 1 - Bugs: ArrayTests - testReverseInPlace method

## A failure-inducing input
```
@Test 
public void testReverseInPlace_Failure() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
}
```

## An input that doesn't induce a failure
```
@Test 
public void testReverseInPlace() {
    int[] input2 = { 1, 2, 3 };
    assertArrayEquals(new int[]{ 3, 2, 1 },
    ArrayExamples.reversed(input2));
}
```
## The symptom, as the output of running the tests

- Error
<img width="906" alt="Screenshot 2023-11-03 at 4 51 19 PM" src="https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/72b68e63-6176-492c-81b6-3e247a2c1028">

- No Error
<img width="905" alt="Screenshot 2023-11-04 at 11 27 02 AM" src="https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/b80d2360-06ff-47dc-8eb3-857e152b7b22">


## The bug before and after code change required to fix

Before:
```
// Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1] ;
    }
    return arr;
  }
```

After:
```
// Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2 ; i += 1) {
      int temp = arr[arr.length - i - 1];
      arr[i] = temp;
    }
  }
```
```
 static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1] ;
    }
    return newArray;
  }
```

- For the method reverseInPlace, before fixing the code, it loops through the entire array from index 1 to arr.length - 1. It reassigns the element many times resulting in overwritting the original files. The fix of adding arr.length/2, this loops through half of the array starting from index 0. In order to correctly reverse the array, a temp variable is added to store the element at the end of the array and assign it to the correct first position. For the reversed method, before fixing the code, since the code is returning arr, it was returning the original modified version which is not the same for reversing the array. The fix of creating a new array which is used to store the reversed values. This newArray variable is then returned, which reverses the correct output we want.

# Part 2 - Researching Commands(grep): 

# -i (ignore case aka, grep -i):
- Example 1:
```
jasminele@Jasmines-MacBook biomed % grep -i "older" 1468-6708-3-1.txt
```
Output:
```
Older adults are frequently counseled to lose weight,
non-smoking older adults have investigated the association
in certain small subsets. A review of 13 studies of older
Many healthy older adults report gradual weight gain
number of studies of older persons is fairly small, and
In older adults, risk factors may have a greater effect
years of being healthy, in a cohort of older adults for
modification interventions in older adults.
65 and older at baseline [ 11 ] . Subjects were recruited
older men and 30-35 for older women. In Figure 1, the
categories could be combined for older adults. Since
older women could be efficient if YHL (but not YOL) was
interventions for older adults who were merely overweight
evaluations should be considered critically when older
33 34 ] . For older adults, the risks associated with
outcome for a trial of weight loss in older adults
found for underweight older adults. Clinical trials whose
average older adult; however, adjustment for detailed
older adults, especially for women. Future efforts to
no excess risk for older adults who would be classified as
obese or underweight older adults, and discouraging trials
that address older adults who are merely overweight.
```

- Example 2:
```
jasminele@Jasmines-MacBook biomed % grep -i "Experiment" 1471-213X-1-12.txt
```
Output:
```
are no reports that experimentally tested this hypothesis
Experiments were repeated 3 times and the data are
experiment using M II oocytes. It is possible that
experiment using confluent cells. Therefore, it is expected
were selected. In our preliminary experiment, such a
Experimental Studies
In Experiment 1, the cell cycle stages of confluent
In Experiment 2, we examined the behavior before
In Experiment 3, the behavior of nuclei of confluent
Experiment 4 was undertaken to compare in vitro
values were analyzed using one-way (Experiment 2) or
two-way (Experiments 3 and 4) ANOVA followed by
```
- The command grep -i is an ignore case used to perform a case-insensitive search within a file you are searching for along with the word you are searching for. To use this command, you say grep -i "the word you want" theFileYouWant.txt. This command is useful when you want to search for and print out lines matching whatever you put in quotation marks to help minimize your search.
Sources:
https://www.codingninjas.com/studio/library/grep-command-in-linux
https://geekflare.com/grep-command-examples/
https://docs.rackspace.com/docs/use-the-linux-grep-command#:~:text=%2Di%3A%20Prints%20lines%20with%20matching,of%20lines%20with%20matching%20criteria.

# -r (recursive search aka grep -r):
- Example 1:
```
jasminele@Jasmines-MacBook 911report % grep -r "In addition to"
```
Output:
```
./chapter-13.5.txt:                September 13, 2001. In addition to the usual members of President Bush's war
./chapter-13.3.txt:                such as race, creed, color, or national origin. In addition to those chosen by the
./chapter-3.txt:                the United States. In addition to requiring court review of proposed surveillance
./chapter-3.txt:            In addition to those from the Department of Defense, other elements in the
./chapter-2.txt:            In addition to training fighters and special operators, this larger network of
./chapter-1.txt:Military Notification and Response. Boston Center did not follow the protocol in seeking military assistance through the prescribed chain of command. In addition to notifications within the FAA, Boston Center took the initiative, at 8:34, to contact the military through the FAA's Cape Cod facility. The center also tried to contact a former alert site in Atlantic City, unaware it had been phased out. At 8:37:52, Boston Center reached NEADS. This was the first notification received by the military-at any level-that American 11 had been hijacked:
./chapter-5.txt:                directly with al Qaeda. In addition to supervising the planning and preparations for
./chapter-5.txt:                Afghanistan at al Qaeda's camps. In addition to his close working relationship with
./chapter-5.txt:            In addition to staging actual terrorist attacks in partnership with al Qaeda, Hambali
./chapter-5.txt:                repeat the first semester of his studies. In addition to having academic
./chapter-5.txt:            In addition to Atta, Binalshibh, Shehhi, and Jarrah, the group included other
./chapter-7.txt:                throughout his time in the United States. In addition to his trips, Jarrah made
./chapter-7.txt:            In addition to the operatives who eventually participated in the 9/11 attacks as
./chapter-9.txt:                attack. In addition to county fire, police, and sheriff 's departments, the response
./chapter-8.txt:                the summer. In addition to his daily meetings with President Bush, and weekly
```

- Example 2:
```
jasminele@Jasmines-MacBook docsearch % grep -r "not available" ./technical
```
Output:
```
./technical/government/About_LSC/commission_report.txt:the LSCfunded program were not available in these co-counseled
./technical/government/About_LSC/commission_report.txt:Carolina). Statutory fees are not available for wrongful discharge,
./technical/government/Env_Prot_Agen/section-by-section_summary.txt:approved alternative monitoring system are not available during any
./technical/government/Env_Prot_Agen/ctf1-6.txt:tests were not available (USEPA, 1980a).
./technical/government/Env_Prot_Agen/1-3_meth_901.txt:from full life-cycle tests were not available (USEPA,
./technical/government/Env_Prot_Agen/bill.txt:under subsection (a) is not available for any affected unit during
./technical/government/Env_Prot_Agen/bill.txt:not available and shall, by regulation , prescribe means to
./technical/government/Env_Prot_Agen/bill.txt:1987, or if such data is not available, the Administrator may
./technical/government/Env_Prot_Agen/tech_adden.txt:appropriate concentration-response functions are not available or
./technical/government/Env_Prot_Agen/tech_adden.txt:PM), locationspecific C-R functions are generally not available. A
./technical/government/Alcohol_Problems/DraftRecom-PDF.txt:counseling is not available, screening and interventions are less
./technical/government/Gen_Account_Office/d0269g.txt:where in-house expertise is not available, investigate
./technical/government/Gen_Account_Office/og97032.txt:the public interest." Thus it is not available when notice and
./technical/government/Gen_Account_Office/Statements_Feb28-1997_volume.txt:expense data are not available. At the end of 5 years, entities
./technical/government/Gen_Account_Office/Statements_Feb28-1997_volume.txt:and for which expense data are not available. If neither historical
./technical/government/Gen_Account_Office/Statements_Feb28-1997_volume.txt:reported. If outcome data are not available (for example, the
./technical/government/Gen_Account_Office/Statements_Feb28-1997_volume.txt:and for which expense data are not available. If neither historical
./technical/government/Gen_Account_Office/Statements_Feb28-1997_volume.txt:the investments are reported.38 If outcome data are not available
./technical/government/Gen_Account_Office/Statements_Feb28-1997_volume.txt:reporting is required and for which expense data are not available.
./technical/government/Gen_Account_Office/pe1019.txt:most diligent search for information, more is not available to
./technical/government/Gen_Account_Office/ffm.txt:to travel when funds for air travel were not available or were in
./technical/government/Gen_Account_Office/og97050.txt:found at section 808(2) is not available when notice and comment
./technical/government/Gen_Account_Office/d03273g.txt:Several options exist if source documents are not available. For
./technical/government/Gen_Account_Office/June30-2000_gg00135r.txt:recently proposed rules available for comment were not available
./technical/government/Gen_Account_Office/June30-2000_gg00135r.txt:sites-features that are currently not available in the DOT docket
./technical/government/Gen_Account_Office/og96027.txt:sufficient data was not available to quantify the benefits.
./technical/government/Gen_Account_Office/im814.txt:if one is not available.
./technical/government/Gen_Account_Office/ai9868.txt:not available.
./technical/government/Gen_Account_Office/May1998_ai98068.txt:not available.
./technical/government/Post_Rate_Comm/Cohenetal_CreamSkimming.txt:The 1997 CCS data were not available when the analysis for this
./technical/government/Post_Rate_Comm/Mitchell_RMVancouver.txt:not available, senders would be required to pay air rates, and
./technical/government/Post_Rate_Comm/Mitchell_RMVancouver.txt:At the present time, costs by customer are not available and the
./technical/government/Post_Rate_Comm/Cohenetal_Cost_Function.txt:these adjustments were not available, except for Italy. The
./technical/government/Post_Rate_Comm/Redacted_Study.txt:to the remaining 5 ICs whose rates were not available. Similarly,
./technical/government/Post_Rate_Comm/Mitchell_6-17-Mit.txt:information of this kind was not available. A natural question
./technical/government/Post_Rate_Comm/Cohenetal_Scale.txt:and point of delivery data are not available. We use volume per
./technical/government/Post_Rate_Comm/Cohenetal_Scale.txt:delivery cost and point of delivery data are not available. We use
./technical/plos/pmed.0020059.txt:        unavailable, unreliable, or not available at the fine geographical resolution needed. The
./technical/plos/journal.pbio.0020241.txt:        Unfortunately, spontaneous models are not available for all human autoimmune diseases.
./technical/plos/pmed.0010058.txt:        and mortality. Although precise figures are not available, over 1 million United States
./technical/plos/pmed.0020015.txt:          not available on the timing of anticapsular antibody acquisition in these same
./technical/plos/journal.pbio.0020307.txt:        adaptive immunity is not available to most organisms, having probably evolved along with
./technical/plos/pmed.0020246.txt:          Of the 1,103 professionals sampled, 23 were not eligible, five were not available
./technical/plos/pmed.0020050.txt:        people. Data are not available on the number of individuals with HIV in each specific
./technical/plos/pmed.0020123.txt:        adequate information is not available to differentiate varying levels of absolute risk
./technical/biomed/1472-6807-2-2.txt:        binding data is not available for many alleles. Protein
./technical/biomed/1471-2466-1-1.txt:        tissues were not available for examination. Because the PIP
./technical/biomed/1471-213X-2-1.txt:          Antibodies that recognize chick PN-1 are not available
./technical/biomed/1471-213X-2-1.txt:        tissue is not available, thus we were unable to follow its
./technical/biomed/1471-213X-2-1.txt:            chick are not available, we examined its localization
./technical/biomed/gb-2003-4-5-r34.txt:          not hierarchical, its results are not available (NA)
./technical/biomed/1471-2156-3-10.txt:        inbred lines are not available, genes also display
./technical/biomed/1471-2121-3-13.txt:          to human MMP-1 (this reagent is not available for the
./technical/biomed/gb-2001-2-7-research0025.txt:          indicators were not available, information from the
./technical/biomed/ar130.txt:        bone marrow MSCs [ 1, 3], was not available when these
./technical/biomed/gb-2001-2-4-research0012.txt:          cell-cycle progression'), a capability not available in
./technical/biomed/gb-2001-2-7-research0024.txt:          was a myosin not available in the NCBI (National Center
./technical/biomed/1471-2288-2-4.txt:        extract potentially valuable information not available by
./technical/biomed/1471-2288-2-4.txt:        potentially valuable information not available when
./technical/biomed/cc367.txt:        institutions is not available in the surgical literature;
./technical/biomed/gb-2001-2-4-research0014.txt:          are not available through IMAGE.
./technical/biomed/1471-2148-2-17.txt:        latter model is not available in MrBayes). Four MCMC chains
./technical/biomed/1472-6904-2-5.txt:        information for the different organs is not available in
./technical/biomed/1472-6823-3-1.txt:          radiologic procedures was not available. Dialysis
./technical/biomed/1472-6823-3-1.txt:        patients with diabetes were not available). [ 17 ] Although
./technical/biomed/cc2190.txt:          deviations were not available, we computed them from the
./technical/biomed/cc2190.txt:          test statistics were not available, given a 
./technical/biomed/1471-2288-3-4.txt:          not available.
./technical/biomed/1475-925X-2-11.txt:        were not available to perform similar tests. The assumption
./technical/biomed/1471-2369-3-10.txt:          of prednisone was not available in the USRDS. Both the
./technical/biomed/1471-2369-3-10.txt:          was not available.
./technical/biomed/1471-2377-1-2.txt:        information was not available, which limited our ability to
./technical/biomed/gb-2002-3-12-research0078.txt:        not available from Celera. Third, by in-house sequencing of
./technical/biomed/cc1538.txt:          was not available, it would be difficult to monitor vital
./technical/biomed/cc1538.txt:          even though hand ventilation was not available during
./technical/biomed/ar387.txt:        data were not available. The single hospital population
./technical/biomed/ar750.txt:        variables were not available), a review of the literature
./technical/biomed/1472-6785-2-6.txt:          are not available, we do not claim to have identified all
./technical/biomed/1471-2105-3-14.txt:        alignments are not available (to our knowledge). However,
./technical/biomed/1471-2458-2-3.txt:            AIDSS were not available. In the FSU centrally planned
./technical/biomed/1472-6963-1-8.txt:        a rapid clinic-based diagnostic test was not available.
./technical/biomed/gb-2003-4-9-r60.txt:          offered by DAVID are not available from FatiGO.
./technical/biomed/gb-2003-4-9-r60.txt:          parsed from LocusLink. These features are not available
./technical/biomed/1471-2164-4-15.txt:        2 was not available, and the comparison was made for the
./technical/biomed/1471-2164-4-15.txt:        of exon 3 is not available. VISTA comparison of human and
./technical/biomed/1471-2369-4-5.txt:        plasma viral load in patients with HIVAN was not available
./technical/biomed/1471-2121-3-4.txt:        step when surface traction is not available [ 8 ] . Other
./technical/biomed/1476-4598-2-2.txt:        clinical information was not available at the time of the
./technical/biomed/1472-6963-3-7.txt:          2000 values were not available, older estimates were
./technical/biomed/1472-6963-3-7.txt:        relevant cost components were not available. The degree of
./technical/biomed/cc2167.txt:          duration of administration were not available for
./technical/biomed/cc2167.txt:          in commercial use is not available. For the
./technical/biomed/cc2167.txt:          (activated) in commercial use is not available.
./technical/biomed/cc2167.txt:          Platelet counts were not available for three of these 12
./technical/biomed/gb-2003-4-6-r39.txt:          sequences not available when our analyses were first
./technical/biomed/1472-6947-2-7.txt:        information is often not available to those who need it
./technical/biomed/rr37.txt:          n = 669) are not available.
./technical/biomed/1471-2458-2-18.txt:        for aspirin use were not available. Exposure
./technical/biomed/1471-2288-2-10.txt:          publication and is not available from the investigator it
./technical/biomed/1471-2288-2-10.txt:          subject groups is not available, the response to the
./technical/biomed/1471-2164-3-4.txt:          were not available through SEALS package were programmed
./technical/biomed/gb-2002-3-12-research0075.txt:        If CGH data are not available for a particular cancer
./technical/biomed/1471-2350-2-11.txt:        parents of Case 1 were not available for study, the
./technical/biomed/ar799.txt:        is not available from any tissue and fluid bank. However,
./technical/biomed/1471-2369-4-1.txt:        although population based comparisons are not available. [
./technical/biomed/1471-2180-1-34.txt:        this mechanism is not available to RNA viruses that are
./technical/biomed/1471-2180-1-34.txt:        earlier, conditional lethal mutations are not available for
./technical/biomed/1468-6708-3-7.txt:          when such data are not available. Peripheral alpha-1
./technical/biomed/1471-2105-1-1.txt:          was not available in the medium, the transport flux was
./technical/biomed/gb-2003-4-2-r9.txt:          accompanying hybridization data are not available [ 25,
./technical/biomed/bcr602.txt:          BP1; matched samples were not available.
./technical/biomed/1471-2105-3-2.txt:            specific RDBMS results are not available.
./technical/biomed/1471-2105-3-2.txt:            Determined). When a sequence is known but not available
./technical/biomed/bcr571.txt:          equipment was initially not available.
./technical/biomed/1471-2407-3-14.txt:        Data are not available to identify whether TURP rates
./technical/biomed/1471-2210-3-1.txt:        for these types of modelling. Such tools were not available
./technical/biomed/1476-9433-1-3.txt:          Trough levels of TAC and SRL were not available as they
./technical/biomed/1476-9433-1-3.txt:          The exact SRL levels were not available as they were
./technical/biomed/1471-2121-3-21.txt:          activity in live cells were not available before the
./technical/911report/chapter-3.txt:                exercised immigration enforcement authority. Terrorist watchlists were not available
./technical/911report/chapter-5.txt:                in part because Atef himself is not available to describe it. He was killed in
./technical/911report/chapter-6.txt:                not available and, even if the U.S. forces were sent in, it was not clear where they
./technical/911report/chapter-9.txt:                at 2 World Financial Center and were not available to influence FDNY operations for
./technical/911report/chapter-8.txt:                extensive record, including documents that were not available to the CIA personnel
```

- The command grep -r is a command that recursively searches all the files in the directory you are currently present in and matches the desired string you put in quotation marks. It outputs the file in which the word you want is contained and to the left, it outputs the text. To use this command, you say grep -r "the word you want". This command is useful when you want to search for the string within a directory/large directory and it shows which txt file your string is contained in.
Sources:
https://www.codingninjas.com/studio/library/grep-command-in-linux
https://geekflare.com/grep-command-examples/
https://docs.rackspace.com/docs/use-the-linux-grep-command#:~:text=%2Di%3A%20Prints%20lines%20with%20matching,of%20lines%20with%20matching%20criteria.

# -l (list matching files aka grep -l):
- Example 1:
```
jasminele@Jasmines-MacBook biomed % grep -l "biology" ./*
```
Output:
```
./1471-2105-1-1.txt
./1471-2105-3-12.txt
./1471-2105-3-18.txt
./1471-2105-3-26.txt
./1471-2105-3-30.txt
./1471-2105-3-34.txt
./1471-2105-3-4.txt
./1471-2105-4-31.txt
./1471-2121-3-4.txt
./1471-2121-4-5.txt
./1471-213X-1-2.txt
./1471-213X-2-7.txt
./1471-2148-1-1.txt
./1471-2148-1-6.txt
./1471-2148-2-15.txt
./1471-2148-2-7.txt
./1471-2148-3-4.txt
./1471-2164-3-16.txt
./1471-2164-3-26.txt
./1471-2164-3-28.txt
./1471-2164-3-32.txt
./1471-2164-3-9.txt
./1471-2164-4-19.txt
./1471-2164-4-22.txt
./1471-2164-4-23.txt
./1471-2172-3-4.txt
./1471-2180-2-2.txt
./1471-2180-2-22.txt
./1471-2180-2-38.txt
./1471-2180-3-11.txt
./1471-2180-3-4.txt
./1471-2199-3-7.txt
./1471-2202-2-16.txt
./1471-2202-3-1.txt
./1471-2202-3-11.txt
./1471-2202-4-5.txt
./1471-2261-3-4.txt
./1471-2350-3-7.txt
./1471-2350-4-2.txt
./1471-2407-1-19.txt
./1471-2407-2-11.txt
./1471-2407-3-16.txt
./1471-2407-3-18.txt
./1471-2407-3-5.txt
./1472-6750-1-11.txt
./1472-6750-1-13.txt
./1472-6750-2-14.txt
./1472-6750-2-21.txt
./1472-6750-3-11.txt
./1472-6769-1-3.txt
./1472-6785-1-3.txt
./1472-6793-1-2.txt
./1472-6807-2-3.txt
./1472-6963-3-14.txt
./1475-2875-1-5.txt
./1475-2875-2-4.txt
./1475-4924-1-10.txt
./1475-925X-2-10.txt
./1475-9268-1-1.txt
./1476-0711-2-3.txt
./1476-4598-1-8.txt
./1477-7827-1-9.txt
./ar118.txt
./ar331.txt
./ar409.txt
./ar612.txt
./cc1498.txt
./gb-2001-2-12-research0051.txt
./gb-2001-2-2-research0004.txt
./gb-2001-2-4-research0012.txt
./gb-2002-3-10-research0052.txt
./gb-2002-3-10-research0055.txt
./gb-2002-3-12-research0081.txt
./gb-2002-3-12-research0082.txt
./gb-2002-3-12-research0086.txt
./gb-2002-3-12-research0087.txt
./gb-2002-3-3-research0011.txt
./gb-2002-3-7-research0037.txt
./gb-2002-3-8-research0039.txt
./gb-2002-3-8-research0040.txt
./gb-2002-4-1-r2.txt
./gb-2003-4-1-r7.txt
./gb-2003-4-2-r8.txt
./gb-2003-4-4-r26.txt
./gb-2003-4-4-r28.txt
./gb-2003-4-5-r32.txt
./gb-2003-4-6-r39.txt
./gb-2003-4-7-r46.txt
./gb-2003-4-9-r58.txt
./gb-2003-4-9-r60.txt
./rr167.txt
```
- Example 2:
```
jasminele@Jasmines-MacBook docsearch % grep -rl "alert" ./technical/   
```
Output:
```
./technical//government/Gen_Account_Office/d0269g.txt
./technical//government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt
./technical//government/Gen_Account_Office/Sept27-2002_d02966.txt
./technical//government/Gen_Account_Office/Statements_Feb28-1997_volume.txt
./technical//government/Gen_Account_Office/pe1019.txt
./technical//government/Gen_Account_Office/gg96118.txt
./technical//government/Gen_Account_Office/d03419sp.txt
./technical//government/Gen_Account_Office/d03273g.txt
./technical//government/Gen_Account_Office/June30-2000_gg00135r.txt
./technical//government/Gen_Account_Office/Oct15-2001_d0224.txt
./technical//government/Gen_Account_Office/im814.txt
./technical//government/Gen_Account_Office/ai9868.txt
./technical//government/Gen_Account_Office/May1998_ai98068.txt
./technical//government/Gen_Account_Office/d02701.txt
./technical//government/Media/Lockyer_Warns.txt
./technical//plos/pmed.0020062.txt
./technical//plos/journal.pbio.0030051.txt
./technical//plos/pmed.0020239.txt
./technical//plos/journal.pbio.0030056.txt
./technical//plos/pmed.0010050.txt
./technical//plos/pmed.0020140.txt
./technical//plos/pmed.0020208.txt
./technical//plos/pmed.0020209.txt
./technical//plos/journal.pbio.0020404.txt
./technical//biomed/1471-2369-3-9.txt
./technical//biomed/1471-2148-1-8.txt
./technical//biomed/cc367.txt
./technical//biomed/1471-2431-2-4.txt
./technical//biomed/cc1856.txt
./technical//biomed/gb-2001-2-6-research0021.txt
./technical//biomed/cc1529.txt
./technical//biomed/1471-2202-2-14.txt
./technical//biomed/1477-7525-1-10.txt
./technical//biomed/1471-2458-2-25.txt
./technical//biomed/1472-6947-2-7.txt
./technical//biomed/1471-230X-1-8.txt
./technical//biomed/1472-6882-1-10.txt
./technical//biomed/1471-2202-3-14.txt
./technical//biomed/1471-2199-2-6.txt
./technical//biomed/1472-684X-1-5.txt
./technical//911report/chapter-13.4.txt
./technical//911report/chapter-13.5.txt
./technical//911report/chapter-13.2.txt
./technical//911report/chapter-13.3.txt
./technical//911report/chapter-3.txt
./technical//911report/chapter-1.txt
./technical//911report/chapter-5.txt
./technical//911report/chapter-6.txt
./technical//911report/chapter-7.txt
./technical//911report/chapter-8.txt
./technical//911report/chapter-11.txt
```
- The command -l displays the names of the file that is contained in the search text you put in quotations. Doing -l in the current directory with "./*" displays the file within the current directory you are in. Doing grep -rl to a "./technical" at the end displays the recursive list files with the words you placed to search along with the paths it took previously to get there. We use rl instead of -l since we are just in the main directory "dosearch". Without the r, it will result in an error. This command is useful for identifying the files that match with the input you gave it in " " without showing the actual content contained inside.
Sources:
(https://geekflare.com/grep-command-examples/)
(https://docs.rackspace.com/docs/use-the-linux-grep-command#:~:text=%2Di%3A%20Prints%20lines%20with%20matching,of%20lines%20with%20matching%20criteria.)

# -v (invert match aka grep -v):
- Example 1:
```
jasminele@Jasmines-MacBook media % grep -v "the" 5_Legal_Groups.txt 
```
Output:
```
Vulnerable
Salt Lake City Tribune

BY EDWARD MCDONOUGH
Five independent Salt Lake organizations that provide legal
Legal Center at 205 N. 400 West is a project of "And Justice for
All," which, until this venture, has been a joint fund-raising
services. "And Justice for All," which solicits donations primarily
service law groups.
parking, something that's hard to find downtown and which has been
agencies about $375,000 each year. My assistant, Charity
efficient for those needing legal services. No longer will a woman
desperate for a protective order, for example, have to run all over
brick and stone interior walls were all hidden behind coverings and
Sweet Candy Company building for Tomax. The Olafsons are delighted
cost received so far. There still needed to be furnishings and
```
- Example 2:
```
jasminele@Jasmines-MacBook media % grep -v "a" Legal_Aid_Society.txt 
```
Output:
```
Arthur J. Siegel
serves income- eligible clients in eight counties throughout the
do not receive it.
promote throughout the world.
```
- The command -v "inverts" the math of the string you put in " " when using grep -v " ". In other words, if you don't want a certain word to appear, this is the command for it. As shown in example 2, I didn't want any words that contained the letter "a". When I can the grep -v command, it only displays the contents without the word "A". This command is useful when you want to filter out the lines that you stated in the command in between the quotation marks to help focus on information that is not related to whatever you stated in " ".
Sources:
(https://www.codingninjas.com/studio/library/grep-command-in-linux)
(https://geekflare.com/grep-command-examples/)
(https://docs.rackspace.com/docs/use-the-linux-grep-command#:~:text=%2Di%3A%20Prints%20lines%20with%20matching,of%20lines%20with%20matching%20criteria.)
