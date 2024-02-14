# **Lab 3** 
## **Part 1 - Bugs**

![Image](faulty.png)
This is the `ArrayExamples.java` class that we were provided during the lab which contains three buggy methods that produces the wrong output given certain inputs. The bug that I will be focusing on in this lab report is the `averageWithoutLowest()` method.

**Faliure inducing input:** 
  `double[] input3 = {1,1,2,4};
  double average3 = ArrayExamples.averageWithoutLowest(input3);
  assertEquals(3.0, average3, 0);`

  This input produces a faulty output because when diving to get the average of the numbers, the program does not account for multiple "lowest" being   removed, only one of them.

**Non-Faliure inducing input:**
  `double[] input1 = {1,2,4};
  double average1 = ArrayExamples.averageWithoutLowest(input1);
  assertEquals(3.0, average1, 0);`

  This input does not produce a faulty output because since there is only one "lowest", the program accounts for that and divides the remaning numbers by the length of the array minus one, which makes sense since there is only one number being removed.

![Image](junittest.png)
-This is the symptom/output of junit running the faliure and non faliure inducing inputs.

**Before code of buggy method**
 `double sum = 0;
    for(double num: arr) {
      if(num != lowest) { sum += num; }
    }
    return sum / (arr.length - 1);`

  **Code after fixing bug**
  `double sum = 0;
    double numDivideby=0;
    for(double num: arr) {
      if(num != lowest) { 
        sum += num; 
        numDivideby+=1;
      }
    }
    return sum / (numDivideby);`

## **Part 2- Researching Commands**
-The command that I am researching is `grep`.
**First command option (-i)**
- Command: ` grep -i  Hani chapter-1.txt`
- Output: ` Washington Dulles: American 77. Hundreds of miles southwest of Boston, at Dulles International Airport in the Virginia suburbs of Washington, D.C., five more men were preparing to take their early morning flight. At 7:15, a pair of them, Khalid al Mihdhar and Majed Moqed, checked in at the American Airlines ticket counter for Flight 77, bound for Los Angeles. Within the next 20 minutes, they would be followed by Hani Hanjour and two brothers, Nawaf al Hazmi and Salem al Hazmi.
    Hani Hanjour, Khalid al Mihdhar, and Majed Moqed were flagged by CAPPS. The Hazmi brothers were also selected for extra scrutiny by the airline's customer service representative at the check-in counter. He did so because one of the brothers did not have photo identification nor could he understand English, and because the agent found both of the passengers to be suspicious. The only consequence of their selection was that their checked bags were held off the plane until it was confirmed that they had boarded the aircraft.
    About 20 minutes later, at 7:35, another passenger for Flight 77, Hani Hanjour, placed two carry-on bags on the X-ray belt in the Main Terminal's west checkpoint, and proceeded, without alarm, through the metal detector. A short time later, Nawaf and Salem al Hazmi entered the same checkpoint. Salem al Hazmi cleared the metal detector and was permitted through; Nawaf al Hazmi set off the alarms for both the first and second metal detectors and was then hand-wanded before being passed. In addition, his over-the-shoulder carry-on bag was swiped by an explosive trace detector and then passed. The video footage indicates that he was carrying an unidentified item in his back pocket, clipped to its rim.
    At 7:50, Majed Moqed and Khalid al Mihdhar boarded the flight and were seated in 12A and 12B in coach. Hani Hanjour, assigned to seat 1B (first class), soon followed. The Hazmi brothers, sitting in 5E and 5F, joined Hanjour in the first-class cabin.
    The controller tracking American 77 told us he noticed the aircraft turning to the southwest, and then saw the data disappear. The controller looked for primary radar returns. He searched along the plane's projected flight path and the airspace to the southwest where it had started to turn. No primary targets appeared. He tried the radios, first calling the aircraft directly, then the airline. Again there was nothing. At this point, the Indianapolis controller had no knowledge of the situation in New York. He did not know that other aircraft had been hijacked. He believed American 77 had experienced serious electrical or mechanical failure, or both, and was gone.`
