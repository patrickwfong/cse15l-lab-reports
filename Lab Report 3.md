## Lab Report 3
Patrick Fong - A14080869
# Part 1 - Bugs

1. A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown):
   ```
    public void testReversed2() {
    int[] input3 = { 1, 2 };
    ArrayExamples.reversed(input3);
    assertArrayEquals(new int[]{ 2, 1 }, input3);
   }
   ```


2. An input that doesn't induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown):

   ```

    public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));

    int[] input2 = { 5, 9, 3, 2, 6 };
    ArrayExamples.reversed(input2);
    assertArrayEquals(new int[]{ 6, 2, 3, 9, 5 }, ArrayExamples.reversed(input2));
   }
   ```
  
3. The symptom, as the output of running the two tests above (provide it as a screenshot -- one test should pass, one test should fail).
 ```
user@users-Air-2 lab3 % java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ArrayTests
JUnit version 4.13.2
..E
Time: 0.006
There was 1 failure:
1) testReversed2(ArrayTests)
arrays first differed at element [0]; expected:<2> but was:<1>
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:78)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:28)
        at org.junit.Assert.internalArrayEquals(Assert.java:534)
        at org.junit.Assert.assertArrayEquals(Assert.java:418)
        at org.junit.Assert.assertArrayEquals(Assert.java:429)
        at ArrayTests.testReversed2(ArrayTests.java:21)
        ... 30 trimmed
Caused by: java.lang.AssertionError: expected:<2> but was:<1>
        at org.junit.Assert.fail(Assert.java:89)
        at org.junit.Assert.failNotEquals(Assert.java:835)
        at org.junit.Assert.assertEquals(Assert.java:120)
        at org.junit.Assert.assertEquals(Assert.java:146)
        at org.junit.internal.ExactComparisonCriteria.assertElementsEqual(ExactComparisonCriteria.java:8)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:76)
        ... 36 more

FAILURES!!!
Tests run: 2,  Failures: 1
```
4. The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown).
Before
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```
After:
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[arr.length - i - 1] = arr[i];
    }
    return newArray;
  }
```
5. Briefly describe (2-3 sentences) why the fix addresses the issue.\
  Previously, line 4 of the original code is written using the wrong indices. The fix swaps the two indices, solving the issue.

# Part 2 - Researching Commands
Command and option: ``find . -amin 1 ``\
Source: [https://man7.org/linux/man-pages/man1/less.1.html](https://man7.org/linux/man-pages/man1/find.1.html)\
Finds all files accessed in the past 1 minute.\
Example 1.1:
```
user@users-Air-2 technical % find . -amin 1
./government
./government/About_LSC
./government/Env_Prot_Agen
./government/Alcohol_Problems
./government/Gen_Account_Office
./government/Post_Rate_Comm
./government/Media
./plos
./911report
```
Example 1.2:
```
Running the same command after opening some more files:
user@users-Air-2 technical % find . -amin 1
./government
./government/About_LSC
./government/Env_Prot_Agen
./government/Alcohol_Problems
./government/Gen_Account_Office
./government/Post_Rate_Comm
./government/Media
./biomed/1472-6807-2-9
./biomed/1472-6807-3-1
./biomed/1472-6874-2-13
./plos
./911report
```

Command and option: ``grep -w "Keyword" file``\
Finds all matches for the specified word.\
Source: https://www.geeksforgeeks.org/grep-command-in-unixlinux/\
Example 2.1:
```
user@users-Air-2 biomed % grep -w 212 *.txt
1471-2164-3-1.txt:          212-1661, GenBank accession number J03250), BTBD1
1471-230X-1-10.txt:        (n = 6) (212 ± 32 pmol/mm 2; p < 0.05 vs. wild-type).
1471-244X-2-9.txt:        significant difference in age (F = 0.52, df = 2, 212, p =
1471-244X-2-9.txt:        means (F = 5.86, df = 2,212, p = 0.003), with AD having a
1471-244X-2-9.txt:        2,212, p = 0.002). NAD was distinct from AD and ADSx
1471-244X-2-9.txt:        df = 2,212, p =< 0.01), with NAD being significantly
1471-244X-2-9.txt:        visits was greater in AD (F = 3.69, df = 2,212, p = 0.027)
1471-244X-2-9.txt:        the patient groups (F = 2.03, df = 2,212, p = 0.13), though
gb-2002-3-12-research0072.txt:          28- and 39-bp segments in a 212,128-bp fragment of mouse
gb-2002-3-12-research0072.txt:          12 . Of 212,101 (0.00414) 28-bp
gb-2002-3-12-research0072.txt:          212,101 (0.01118) 28-bp segments in AC084823 have 
gb-2002-3-12-research0072.txt:          12 < -38.81, and just 54 of 212,101
gb-2002-3-12-research0072.txt:          10 -5(21/212,102). Similarly, of the 155 physiologic
gb-2002-3-12-research0072.txt:          212,090 (4.7 × 10 -4) 39-bp segments from sequence
gb-2002-3-12-research0072.txt:          AC084823 and only 58 of the 212,091 segments from the PRS
gb-2003-4-3-r17.txt:          hypothalamus = 55,212, adult retina = 54,009; Figures 2,
gb-2003-4-3-r17.txt:          55,212, E12.5 = 53,267, E14.5 = 54,884, E16.5 = 55,213,
gb-2003-4-4-r24.txt:          in 212 Gambian and 84 Malawian adults with no missing
gb-2003-4-4-r24.txt:        genotyped in 212 Gambian and 84 Malawian adults. Gametic
gb-2003-4-4-r24.txt:          Gambian sample (a total of 212 adults), and 70
gb-2003-4-4-r24.txt:          LT α, in a sample of 212 Gambian
gb-2003-4-4-r26.txt:          total and 212 unique mappings). Out of 82 possible
gb-2003-4-4-r26.txt:          7,212 
gb-2003-4-4-r26.txt:          using RNAi, a list of all 7,212 available 
gb-2003-4-9-r57.txt:          r 2= 0.212). The most recent LTGs
```
Example 2.2:
```
user@users-Air-2 biomed % grep -w J03250 *.txt
1471-2164-3-1.txt:          212-1661, GenBank accession number J03250), BTBD1
```

Command and option:``grep -n "Keyword" file``\
Like -w, but also displays the line number of the occurence.\
Source: https://www.geeksforgeeks.org/grep-command-in-unixlinux/\
Example 3.1:
```
user@users-Air-2 biomed % grep -n 212 *.txt   
1471-2105-3-16.txt:530:          programmed cell death in C. elegans" (PMID: 10882128), a
1471-213X-1-9.txt:659:          5'-GTTTGGAAGAGGCTTCAAC-3' (bp 2128-2147, reverse); for
1471-2164-3-1.txt:462:          212-1661, GenBank accession number J03250), BTBD1
1471-2164-3-9.txt:196:          "hit" in the rice BAC H0212B02 of chromosome 4 (GenBank
1471-2164-3-9.txt:198:          annotated open reading frames H0212B02.17 and H0212B02.18
1471-2164-3-9.txt:204:          H0212B02 DNA sequence, ends at position 107,317, and
1471-2164-4-23.txt:135:          [Amersham Pharmacia cat. No. 93-77212], 88 μl Pfx DNA
1471-2180-1-7.txt:215:          characterized in other studies. G105S (FtsZ84) and D212G
1471-2180-1-7.txt:237:          A cluster of mutations (N207, D209, D212) strongly
1471-2180-1-7.txt:256:          D212A was also tested in 2 mM GMPCPP, where it made
1471-2180-1-7.txt:261:          D212A could not. Both mutants assembled bundles of
1471-2180-1-7.txt:332:          [ 22]. FtsZ2 (D212G) has 200-fold lower GTPase than wild
1471-2180-1-7.txt:376:          other three GTP-contact mutants (D45A, D209A, D212A)
1471-2180-1-7.txt:388:          D212 are less certain, but they are likely close to or in
1471-2180-1-7.txt:577:          A70T, D86K, D158A, D212A, E238A, E250A, D269A, E274A, and
1471-2229-1-2.txt:312:        a 3) or His212 ( 
1471-2229-1-2.txt:330:        in vivo [ 34 ] , His212 may serve as
1471-230X-1-10.txt:251:        (n = 6) (212 ± 32 pmol/mm 2; p < 0.05 vs. wild-type).
1471-2334-3-11.txt:389:        medicine, St. Agnes Hospital, Baltimore, MD 21229. An
1471-244X-2-9.txt:191:        significant difference in age (F = 0.52, df = 2, 212, p =
1471-244X-2-9.txt:227:        means (F = 5.86, df = 2,212, p = 0.003), with AD having a
1471-244X-2-9.txt:236:        2,212, p = 0.002). NAD was distinct from AD and ADSx
1471-244X-2-9.txt:240:        df = 2,212, p =< 0.01), with NAD being significantly
1471-244X-2-9.txt:258:        visits was greater in AD (F = 3.69, df = 2,212, p = 0.027)
1471-244X-2-9.txt:265:        the patient groups (F = 2.03, df = 2,212, p = 0.13), though
1476-9433-1-3.txt:185:          2449 vs 12124 ± 2946 p < 0.006; and anti-CD3: 27089 ±
1478-1336-1-4.txt:220:          N-CoR (2033-2123; 2123-2230), one of which (2033-2123)
bcr607.txt:41:        1212) through a peptide bond. Collagen and CTX fragments
gb-2002-3-12-research0072.txt:526:          28- and 39-bp segments in a 212,128-bp fragment of mouse
gb-2002-3-12-research0072.txt:564:          12 . Of 212,101 (0.00414) 28-bp
gb-2002-3-12-research0072.txt:571:          212,101 (0.01118) 28-bp segments in AC084823 have 
gb-2002-3-12-research0072.txt:607:          12 < -38.81, and just 54 of 212,101
gb-2002-3-12-research0072.txt:614:          10 -5(21/212,102). Similarly, of the 155 physiologic
gb-2002-3-12-research0072.txt:618:          212,090 (4.7 × 10 -4) 39-bp segments from sequence
gb-2002-3-12-research0072.txt:619:          AC084823 and only 58 of the 212,091 segments from the PRS
gb-2002-3-12-research0083.txt:1388:            FBrf0132129, FBrf0126925; D.R. Nelson, personal
gb-2002-3-12-research0086.txt:277:          BcDNA:LD21213, Gr59a, Gr59b, CG9895,
gb-2002-3-9-research0049.txt:127:          region (AT2g21200 to AT2g21220), which made continued
gb-2002-3-9-research0051.txt:513:          N61, G211 → R211, F/L212 → R212, and G234 → K234. In
gb-2003-4-2-r11.txt:125:          E. coli (gi: 15802120, residues
gb-2003-4-3-r17.txt:803:          hypothalamus = 55,212, adult retina = 54,009; Figures 2,
gb-2003-4-3-r17.txt:805:          55,212, E12.5 = 53,267, E14.5 = 54,884, E16.5 = 55,213,
gb-2003-4-4-r24.txt:61:          in 212 Gambian and 84 Malawian adults with no missing
gb-2003-4-4-r24.txt:303:        genotyped in 212 Gambian and 84 Malawian adults. Gametic
gb-2003-4-4-r24.txt:533:          Gambian sample (a total of 212 adults), and 70
gb-2003-4-4-r24.txt:551:          LT α, in a sample of 212 Gambian
gb-2003-4-4-r26.txt:257:          total and 212 unique mappings). Out of 82 possible
gb-2003-4-4-r26.txt:524:          7,212 
gb-2003-4-4-r26.txt:1098:          using RNAi, a list of all 7,212 available 
gb-2003-4-9-r57.txt:263:          r 2= 0.212). The most recent LTGs
```
Example 3.2:
```
user@users-Air-2 biomed % grep -n J03250 *.txt 
1471-2164-3-1.txt:462:          212-1661, GenBank accession number J03250), BTBD1
```

Command and option:``grep -l "Keyword" file``\
Like -w and -n, but only displays file names.\
Source: https://www.geeksforgeeks.org/grep-command-in-unixlinux/\
Example 4.1:
```
user@users-Air-2 biomed % grep -l "212" *.txt
1471-2105-3-16.txt
1471-213X-1-9.txt
1471-2164-3-1.txt
1471-2164-3-9.txt
1471-2164-4-23.txt
1471-2180-1-7.txt
1471-2229-1-2.txt
1471-230X-1-10.txt
1471-2334-3-11.txt
1471-244X-2-9.txt
1476-9433-1-3.txt
1478-1336-1-4.txt
bcr607.txt
gb-2002-3-12-research0072.txt
gb-2002-3-12-research0083.txt
gb-2002-3-12-research0086.txt
gb-2002-3-9-research0049.txt
gb-2002-3-9-research0051.txt
gb-2003-4-2-r11.txt
gb-2003-4-3-r17.txt
gb-2003-4-4-r24.txt
gb-2003-4-4-r26.txt
gb-2003-4-9-r57.txt
```
Example 4.2:
```
user@users-Air-2 biomed % grep -l "J03250" *.txt
1471-2164-3-1.txt
```

