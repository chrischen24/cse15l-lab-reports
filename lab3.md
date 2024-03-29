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
- Command: `grep -i  Hani chapter-1.txt`
- Output: `Washington Dulles: American 77. Hundreds of miles southwest of Boston, at Dulles International Airport in the Virginia suburbs of Washington, D.C., five more men were preparing to take their early morning flight. At 7:15, a pair of them, Khalid al Mihdhar and Majed Moqed, checked in at the American Airlines ticket counter for Flight 77, bound for Los Angeles. Within the next 20 minutes, they would be followed by Hani Hanjour and two brothers, Nawaf al Hazmi and Salem al Hazmi.
    Hani Hanjour, Khalid al Mihdhar, and Majed Moqed were flagged by CAPPS. The Hazmi brothers were also selected for extra scrutiny by the airline's customer service representative at the check-in counter. He did so because one of the brothers did not have photo identification nor could he understand English, and because the agent found both of the passengers to be suspicious. The only consequence of their selection was that their checked bags were held off the plane until it was confirmed that they had boarded the aircraft.
    About 20 minutes later, at 7:35, another passenger for Flight 77, Hani Hanjour, placed two carry-on bags on the X-ray belt in the Main Terminal's west checkpoint, and proceeded, without alarm, through the metal detector. A short time later, Nawaf and Salem al Hazmi entered the same checkpoint. Salem al Hazmi cleared the metal detector and was permitted through; Nawaf al Hazmi set off the alarms for both the first and second metal detectors and was then hand-wanded before being passed. In addition, his over-the-shoulder carry-on bag was swiped by an explosive trace detector and then passed. The video footage indicates that he was carrying an unidentified item in his back pocket, clipped to its rim.
    At 7:50, Majed Moqed and Khalid al Mihdhar boarded the flight and were seated in 12A and 12B in coach. Hani Hanjour, assigned to seat 1B (first class), soon followed. The Hazmi brothers, sitting in 5E and 5F, joined Hanjour in the first-class cabin.
    The controller tracking American 77 told us he noticed the aircraft turning to the southwest, and then saw the data disappear. The controller looked for primary radar returns. He searched along the plane's projected flight path and the airspace to the southwest where it had started to turn. No primary targets appeared. He tried the radios, first calling the aircraft directly, then the airline. Again there was nothing. At this point, the Indianapolis controller had no knowledge of the situation in New York. He did not know that other aircraft had been hijacked. He believed American 77 had experienced serious electrical or mechanical failure, or both, and was gone.`
- Command: `grep -i crash chapter-1.txt`
- Output: `At 8:46:40, American 11 crashed into the North Tower of the World Trade Center in New York City.
    Shortly after the first call, Barbara Olson reached her husband again. She reported that the pilot had announced that the flight had been hijacked, and she asked her husband what she should tell the captain to do. Ted Olson asked for her location and she replied that the aircraft was then flying over houses. Another passenger told her they were traveling northeast. The Solicitor General then informed his wife of the two previous hijackings and crashes. She did not display signs of panic and did not indicate any awareness of an impending crash. At that point, the second call was cut off.
    At 9:37:46, American Airlines Flight 77 crashed into the Pentagon, traveling at approximately 530 miles per hour.
    One of the callers from United 93 also reported that he thought the hijackers might possess a gun. But none of the other callers reported the presence of a firearm. One recipient of a call from the aircraft recounted specifically asking her caller whether the hijackers had guns. The passenger replied that he did not see one. No evidence of firearms or of their identifiable remains was found at the aircraft's crash site, and the cockpit voice recorder gives no indication of a gun being fired or mentioned at any time. We believe that if the hijackers had possessed a gun, they would have used it in the flight's last minutes as the passengers fought back.
    Passengers on three flights reported the hijackers' claim of having a bomb. The FBI told us they found no trace of explosives at the crash sites. One of the passengers who mentioned a bomb expressed his belief that it was not real. Lacking any evidence that the hijackers attempted to smuggle such illegal items past the security screening checkpoints, we believe the bombs were probably fake.
    In response, Jarrah immediately began to roll the airplane to the left and right, attempting to knock the passengers off balance. At 9:58:57, Jarrah told another hijacker in the cockpit to block the door. Jarrah continued to roll the airplane sharply left and right, but the assault continued. At 9:59:52, Jarrah changed tactics and pitched the nose of the airplane up and down to disrupt the assault. The recorder captured the sounds of loud thumps, crashes, shouts, and breaking glasses and plates. At 10:00:03, Jarrah stabilized the airplane.
    Jarrah's objective was to crash his airliner into symbols of the American Republic, the Capitol or the White House. He was defeated by the alerted, unarmed passengers of United 93.
    Before 9/11, it was not unheard of for a commercial aircraft to deviate slightly from its course, or for an FAA controller to lose radio contact with a pilot for a short period of time. A controller could also briefly lose a commercial aircraft's transponder signal, although this happened much less frequently. However, the simultaneous loss of radio and transponder signal would be a rare and alarming occurrence, and would normally indicate a catastrophic system failure or an aircraft crash. In all of these instances, the job of the controller was to reach out to the aircraft, the parent company of the aircraft, and other planes in the vicinity in an attempt to reestablish communications and set the aircraft back on course. Alarm bells would not start ringing until these efforts-which could take five minutes or more-were tried and had failed.
    The New York Center controller and manager were unaware that American 11 had already crashed.
    The "other aircraft" referred to by New York Center was United 175. Evidence indicates that this conversation was the only notice received by either FAA headquarters or the Herndon Command Center prior to the second crash that there had been a second hijacking.
    The controllers observed the plane in a rapid descent; the radar data terminated over Lower Manhattan. At 9:03, United 175 crashed into the South Tower.
    Shortly after 9:00, Indianapolis Center started notifying other agencies that American 77 was missing and had possibly crashed. At 9:08, Indianapolis Center asked Air Force Search and Rescue at Langley Air Force Base to look for a downed aircraft. The center also contacted the West Virginia State Police and asked whether any reports of a downed aircraft had been received. At 9:09, it reported the loss of contact to the FAA regional center, which passed this information to FAA headquarters at 9:24.
    By 9:20, Indianapolis Center learned that there were other hijacked aircraft, and began to doubt its initial assumption that American 77 had crashed. A discussion of this concern between the manager at Indianapolis and the Command Center in Herndon prompted it to notify some FAA field facilities that American 77 was lost. By 9:21, the Command Center, some FAA field facilities, and American Airlines had started to search for American 77. They feared it had been hijacked. At 9:25, the Command Center advised FAA headquarters of the situation.
    In sum, Indianapolis Center never saw Flight 77 turn around. By the time it reappeared in primary radar coverage, controllers had either stopped looking for the aircraft because they thought it had crashed or were looking toward the west. Although the Command Center learned Flight 77 was missing, neither it nor FAA headquarters issued an all points bulletin to surrounding centers to search for primary radar targets. American 77 traveled undetected for 36 minutes on a course heading due east for Washington, D.C.
    By 9:25, FAA's Herndon Command Center and FAA headquarters knew two aircraft had crashed into the World Trade Center. They knew American 77 was lost. At least some FAA officials in Boston Center and the New England Region knew that a hijacker on board American 11 had said "we have some planes." Concerns over the safety of other aircraft began to mount. A manager at the Herndon Command Center asked FAA headquarters if they wanted to order a "nationwide ground stop." While this was being discussed by executives at FAA headquarters, the Command Center ordered one at 9:25.
    Reagan National controllers then vectored an unarmed National Guard C- 130H cargo aircraft, which had just taken off en route to Minnesota, to identify and follow the suspicious aircraft. The C-130H pilot spotted it, identified it as a Boeing 757, attempted to follow its path, and at 9:38, seconds after impact, reported to the control tower:"looks like that aircraft crashed into the Pentagon sir."
    Right after the Pentagon was hit, NEADS learned of another possible hijacked aircraft. It was an aircraft that in fact had not been hijacked at all. After the second World Trade Center crash, Boston Center managers recognized that both aircraft were transcontinental 767 jetliners that had departed Logan Airport. Remembering the "we have some planes" remark, Boston Center guessed that Delta 1989 might also be hijacked. Boston Center called NEADS at 9:41 and identified Delta 1989, a 767 jet that had left Logan Airport for Las Vegas, as a possible hijack. NEADS warned the FAA's Cleveland Center to watch Delta 1989. The Command Center and FAA headquarters watched it too. During the course of the morning, there were multiple erroneous reports of hijacked aircraft. The report of American 11 heading south was the first; Delta 1989 was the second.
    United 93 crashed in Pennsylvania at 10:03:11, 125 miles from Washington, D.C. The precise crash time has been the subject of some dispute. The 10:03:11 impact time is supported by previous National Transportation Safety Board analysis and by evidence from the Commission staff 's analysis of radar, the flight data recorder, the cockpit voice recorder, infrared satellite data, and air traffic control transmissions.
    The aircraft that spotted the "black smoke" was the same unarmed Air National Guard cargo plane that had seen American 77 crash into the Pentagon 27 minutes earlier. It had resumed its flight to Minnesota and saw the smoke from the crash of United 93, less than two minutes after the plane went down. At 10:17, the Command Center advised headquarters of its conclusion that United 93 had indeed crashed.
Military Notification and Response. NEADS first received a call about United 93 from the military liaison at Cleveland Center at 10:07. Unaware that the aircraft had already crashed, Cleveland passed to NEADS the aircraft's last known latitude and longitude. NEADS was never able to locate United 93 on radar because it was already in the ground.
    At the same time, the NEADS mission crew commander was dealing with the arrival of the Langley fighters over Washington, D.C., sorting out what their orders were with respect to potential targets. Shortly after 10:10, and having no knowledge either that United 93 had been heading toward Washington or that it had crashed, he explicitly instructed the Langley fighters: "negative- negative clearance to shoot" aircraft over the nation's capital.
    The time of notification of the crash of United 93 was 10:15. The NEADS air defenders never located the flight or followed it on their radar scopes. The flight had already crashed by the time they learned it was hijacked.
    Nor did the military have 47 minutes to respond to United 93, as would be implied by the account that it received notice of the flight's hijacking at 9:16. By the time the military learned about the flight, it had crashed. We now turn to the role of national leadership in the events that morning.
    Most federal agencies learned about the crash in New York from CNN.
    Within the FAA, the administrator, Jane Garvey, and her acting deputy, Monte Belger, had not been told of a confirmed hijacking before they learned from television that a plane had crashed.
    In Sarasota, Florida, the presidential motorcade was arriving at the Emma E. Booker Elementary School, where President Bush was to read to a class and talk about education. White House Chief of Staff Andrew Card told us he was standing with the President outside the classroom when Senior Advisor to the President Karl Rove first informed them that a small, twin-engine plane had crashed into the World Trade Center. The President's reaction was that the incident must have been caused by pilot error.
    Elsewhere in the White House, a series of 9:00 meetings was about to begin. In the absence of information that the crash was anything other than an accident, the White House staff monitored the news as they went ahead with their regular schedules.
    At 9:39, the NMCC's deputy director for operations, a military officer, opened the call from the Pentagon, which had just been hit. He began:"An air attack against North America may be in progress. NORAD, what's the situation?" NORAD said it had conflicting reports. Its latest information was "of a possible hijacked aircraft taking off out of JFK en route to Washington D.C." The NMCC reported a crash into the mall side of the Pentagon and requested that the Secretary of Defense be added to the conference.
    By 10:03, when United 93 crashed in Pennsylvania, there had been no mention of its hijacking and the FAA had not yet been added to the teleconference.
    NORAD officials have maintained consistently that had the passengers not caused United 93 to crash, the military would have prevented it from reaching Washington, D.C. That conclusion is based on a version of events that we now know is incorrect. The Langley fighters were not scrambled in response to United 93; NORAD did not have 47 minutes to intercept the flight; NORAD did not even know the plane was hijacked until after it had crashed. It is appropriate, therefore, to reconsider whether United 93 would have been intercepted.
    Had it not crashed in Pennsylvania at 10:03, we estimate that United 93 could not have reached Washington any earlier than 10:13, and probably would have arrived before 10:23. There was only one set of fighters circling Washington during that time frame-the Langley F-16s. They were armed and under NORAD's control. After NEADS learned of the hijacking at 10:07, NORAD would have had from 6 to 16 minutes to locate the flight, receive authorization to shoot it down, and communicate the order to the pilots, who (in the same span) would have had to authenticate the order, intercept the flight, and execute the order.`

-The two commands I used with `grep -i` looked for all lines that contained the name "Hani" and looked for all lines that contained the word "crash", with no specification with the capitalization. This command would be useful in the case where you are looking for a specific word/string in a file, and you don't want it to be specified by its capitalization.

**Second command option(-c)**
- Command: `grep -c Pentagon chapter-1.txt`
- Output: `23`

- Command: `grep -c "New York" chapter-1.txt`
- Output: `39`

- The two commands that I used with `grep -c` returned the number of lines that contianed the string that I was looking for ("Pentagon" and "New York"). This command would be useful when trying to find the amount of lines that contain a word/string that we are looking for.

**Third command option(-r)**
- Command: `grep -r "New York" plos`
- Output:
`plos/pmed.0020065.txt:        applying it to data collected from hospital emergency departments in New York City. The`
  
`plos/pmed.0020065.txt:        analyze emergency department data in New York City in parallel with other methods, and it`

`plos/pmed.0020059.txt:          New York City Emergency Department Syndromic Surveillance System`

`plos/pmed.0020059.txt:          The New York City Emergency Department syndromic surveillance system is described in`

`plos/pmed.0020059.txt:          illness. As of November 2002, 38 of New York City's 66 emergency departments were`

`plos/pmed.0020059.txt:          Implementation for New York City Syndromic Surveillance`

`plos/pmed.0020059.txt:          the new method in New York City, a number of highly significant outbreak signals were`

`plos/pmed.0020059.txt:          December, driven by an unusually early influenza season in New York City.`

`plos/pmed.0020059.txt:        space–time scan statistic. When applied to the New York City diarrhea data described above,`

`plos/pmed.0020060.txt:        successfully bigamous marriages in New York and California.`

`plos/pmed.0020060.txt:        affair with a New York dancer. Dr. Charles Boyd had tried to prove this paternity with his`

`plos/pmed.0020060.txt:        Museum of French Art in New York, auctioned, and finally ending up in the possession of a`

`plos/journal.pbio.0030050.txt:        Paleoanthropologist Ralph Holloway (Columbia University, New York, United States) uses`

`plos/pmed.0010060.txt:        of clinical trial results [1,2]. The debate has intensified since New York State Attorney`

`plos/pmed.0020201.txt:        Institute in New York describe a protocol for deriving mesenchymal precursors, which they`

`plos/pmed.0010062.txt:            (Respitrace Ambulatory Monitoring, Ardsley, New York, United States) were used to`

`plos/pmed.0020034.txt:        York in 1935, and the recognition that hay fever was a major community problem in New York`

`plos/pmed.0020034.txt:        Children in New York, Atlanta, Philadelphia, and Washington, D.C. spend long hours indoors,`

`plos/journal.pbio.0020064.txt:        York, New York, United States). Damak says he does not know why the two sets of T1R3`

`plos/journal.pbio.0020214.txt:        the main positive impacts of the New York–based International Science Foundation set up by`

`plos/journal.pbio.0020214.txt:        Soros Foundation, based in New York] and the Department of Education) (Table 2), reprints`

`plos/journal.pbio.0020214.txt:        Cancer Research (LICR) based jointly in Zurich, New York, and London, and the Belozersky`

`plos/pmed.0020045.txt:          a kind gift of Nada Abumhrad (SUNY at Stony Brook, New York, United States). Cells were`

`plos/pmed.0020045.txt:          following the manufacturer's protocol (Intergen, Purchase, New York, United States) [13].`

`plos/journal.pbio.0020404.txt:        Lorna Role and her colleagues at Columbia University in New York City. “In 1995, we turned`

`plos/journal.pbio.0020028.txt:        University College of Physicians and Surgeons in New York City. Stein has researched`

`plos/pmed.0020040.txt:        effects include weight gain and water retention, and patients with a history of New York`

- Command: `grep -r "computer science"`
- Output: `./government/Gen_Account_Office/pe1019.txt:as chemistry, biology, physics, and computer science."
./plos/journal.pbio.0030032.txt:        the number of earned master's degrees in mathematics and computer science more than
./biomed/1471-2229-2-9.txt:        formalisms used in engineering and computer science [ 24 ]`

-The two commands I used with `grep -r` recursively searched all files and directories under the current working directory for the string that I passed in to be looked for ("New York" and "computer science"). When given a specific directory/file, `grep -r` will recursively search under that directory/file for the given string and return all occurences of that string.

**Fourth Command Option (-n)**
- Command: `grep -n computer chapter-1.txt`
- Output: `16:    When he checked in for his flight to Boston, Atta was selected by a computerized prescreening system known as CAPPS (Computer Assisted Passenger Prescreening System), created to identify passengers who should be subject to special security measures. Under security rules in place at the time, the only consequence of Atta's selection by CAPPS was that his checked bags were held off the plane until it was confirmed that he had boarded the aircraft. This did not hinder Atta's plans.`

- Command: `grep -n Boston chapter-1.txt`
- Output: `14:    Boston: American 11 and United 175. Atta and Omari boarded a 6:00 A.M. flight from Portland to Boston's Logan International Airport.`
`16:    When he checked in for his flight to Boston, Atta was selected by a computerized prescreening system known as CAPPS (Computer Assisted Passenger Prescreening System), created to identify passengers who should be subject to special security measures. Under security rules in place at the time, the only consequence of Atta's selection by CAPPS was that his checked bags were held off the plane until it was confirmed that he had boarded the aircraft. This did not hinder Atta's plans.`

`18:    Atta and Omari arrived in Boston at 6:45. Seven minutes later, Atta apparently took a call from Marwan al Shehhi, a longtime colleague who was at another terminal at Logan Airport. They spoke for three minutes.`

`34:    While Atta had been selected by CAPPS in Portland, three members of his hijacking team-Suqami, Wail al Shehri, and Waleed al Shehri-were selected in Boston. Their selection affected only the handling of their checked bags, not their screening at the checkpoint. All five men cleared the checkpoint and made their way to the gate for American 11. Atta, Omari, and Suqami took their seats in business class (seats 8D, 8G, and 10B, respectively). The Shehri brothers had adjacent seats in row 2 (Wail in 2A, Waleed in 2B), in the firstclass cabin. They boarded American 11 between 7:31 and 7:40. The aircraft pushed back from the gate at 7:40.`

`38:    Washington Dulles: American 77. Hundreds of miles southwest of Boston, at Dulles International Airport in the Virginia suburbs of Washington, D.C., five more men were preparing to take their early morning flight. At 7:15, a pair of them, Khalid al Mihdhar and Majed Moqed, checked in at the American Airlines ticket counter for Flight 77, bound for Los Angeles. Within the next 20 minutes, they would be followed by Hani Hanjour and two brothers, Nawaf al Hazmi and Salem al Hazmi.`

`56:    The four men passed through the security checkpoint, owned by United Airlines and operated under contract by Argenbright Security. Like the checkpoints in Boston, it lacked closed-circuit television surveillance so there is no documentary evidence to indicate when the hijackers passed through the checkpoint, what alarms may have been triggered, or what security procedures were administered. The FAA interviewed the screeners later; none recalled anything unusual or suspicious.`

`62:    They were planning to hijack these planes and turn them into large guided missiles, loaded with up to 11,400 gallons of jet fuel. By 8:00 A.M. on the morning of Tuesday, September 11,2001, they had defeated all the security layers that America's civil aviation security system then had in place to prevent a hijacking. The Hijacking of American 11 American Airlines Flight 11 provided nonstop service from Boston to Los Angeles. On September 11, Captain John Ogonowski and First Officer Thomas McGuinness piloted the Boeing 767. It carried its full capacity of nine flight attendants. Eighty-one passengers boarded the flight with them (including the five terrorists).22 The plane took off at 7:59. Just before 8:14, it had climbed to 26,000 feet, not quite its initial assigned cruising altitude of 29,000 feet. All communications and flight profile data were normal. About this time the "Fasten Seatbelt" sign would usually have been turned off and the flight attendants would have begun preparing for cabin service.`

`64:    At that same time, American 11 had its last routine communication with the ground when it acknowledged navigational instructions from the FAA's air traffic control (ATC) center in Boston. Sixteen seconds after that transmission, ATC instructed the aircraft's pilots to climb to 35,000 feet. That message and all subsequent attempts to contact the flight were not acknowledged. From this and other evidence, we believe the hijacking began at 8:14 or shortly thereafter.`

`78:    At 8:21, one of the American employees receiving Ong's call in North Carolina, Nydia Gonzalez, alerted the American Airlines operations center in Fort Worth, Texas, reaching Craig Marquis, the manager on duty. Marquis soon realized this was an emergency and instructed the airline's dispatcher responsible for the flight to contact the cockpit. At 8:23, the dispatcher tried unsuccessfully to contact the aircraft. Six minutes later, the air traffic control specialist in American's operations center contacted the FAA's Boston Air Traffic Control Center about the flight. The center was already aware of the problem.`

`80:    Boston Center knew of a problem on the flight in part because just before 8:25 the hijackers had attempted to communicate with the passengers. The microphone was keyed, and immediately one of the hijackers said, "Nobody move. Everything will be okay. If you try to make any moves, you'll endanger yourself and the airplane. Just stay quiet." Air traffic controllers heard the transmission; Ong did not. The hijackers probably did not know how to operate the cockpit radio communication system correctly, and thus inadvertently broadcast their message over the air traffic control channel instead of the cabin public-address channel. Also at 8:25, and again at 8:29, Amy Sweeney got through to the American Flight Services Office in Boston but was cut off after she reported someone was hurt aboard the flight. Three minutes later, Sweeney was reconnected to the office and began relaying updates to the manager, Michael Woodward.`

`108:    At 8:52, in Easton, Connecticut, a man named Lee Hanson received a phone call from his son Peter, a passenger on United 175. His son told him: "I think they've taken over the cockpit-An attendant has been stabbed- and someone else up front may have been killed. The plane is making strange moves. Call United Airlines-Tell them it's Flight 175, Boston to LA." Lee Hanson then called the Easton Police Department and relayed what he had heard.`

`154:    At the same time, Boston Center realized that a message transmitted just before 8:25 by the hijacker pilot of American 11 included the phrase, "We have some planes."`

`158:    United 175 was hijacked between 8:42 and 8:46, and awareness of that hijacking began to spread after 8:51. American 77 was hijacked between 8:51 and 8:54. By 9:00, FAA and airline officials began to comprehend that attackers were going after multiple aircraft. American Airlines' nationwide ground stop between 9:05 and 9:10 was followed by a United Airlines ground stop. FAA controllers at Boston Center, which had tracked the first two hijackings, requested at 9:07 that Herndon Command Center "get messages to airborne aircraft to increase security for the cockpit." There is no evidence that Herndon took such action. Boston Center immediately began speculating about other aircraft that might be in danger, leading them to worry about a transcontinental flight-Delta 1989-that in fact was not hijacked. At 9:19, the FAA's New England regional office called Herndon and asked that Cleveland Center advise Delta 1989 to use extra cockpit security.`

`220:    FAA Control Centers often receive information and make operational decisions independently of one another. On 9/11, the four hijacked aircraft were monitored mainly by the centers in Boston, New York, Cleveland, and Indianapolis. Each center thus had part of the knowledge of what was going on across the system. What Boston knew was not necessarily known by centers in New York, Cleveland, or Indianapolis, or for that matter by the Command Center in Herndon or by FAA headquarters in Washington.`

`266:FAA Awareness. Although the Boston Center air traffic controller realized at an early stage that there was something wrong with American 11, he did not immediately interpret the plane's failure to respond as a sign that it had been hijacked. At 8:14, when the flight failed to heed his instruction to climb to 35,000 feet, the controller repeatedly tried to raise the flight. He reached out to the pilot on the emergency frequency. Though there was no response, he kept trying to contact the aircraft.`

`276:    The controller told us that he then knew it was a hijacking. He alerted his supervisor, who assigned another controller to assist him. He redoubled his efforts to ascertain the flight's altitude. Because the controller didn't understand the initial transmission, the manager of Boston Center instructed his quality assurance specialist to "pull the tape" of the radio transmission, listen to it closely, and report back.`

`278:    Between 8:25 and 8:32, in accordance with the FAA protocol, Boston Center managers started notifying their chain of command that American 11 had been hijacked. At 8:28, Boston Center called the Command Center in Herndon to advise that it believed American 11 had been hijacked and was heading toward gr Center's airspace.`

`282:    The Herndon Command Center immediately established a teleconference between Boston, New York, and Cleveland Centers so that Boston Center could help the others understand what was happening.`

`284:    At 8:34, the Boston Center controller received a third transmission from American 11:`

`290:Military Notification and Response. Boston Center did not follow the protocol in seeking military assistance through the prescribed chain of command. In addition to notifications within the FAA, Boston Center took the initiative, at 8:34, to contact the military through the FAA's Cape Cod facility. The center also tried to contact a former alert site in Atlantic City, unaware it had been phased out. At 8:37:52, Boston Center reached NEADS. This was the first notification received by the military-at any level-that American 11 had been hijacked:`

`292:    FAA: Hi. Boston Center TMU [Traffic Management Unit], we have a problem here. We have a hijacked aircraft headed towards New York, and we need you guys to, we need someone to scramble some F-16s or something up there, help us out.`

`316:    UAL 175: Yeah. We figured we'd wait to go to your center. Ah, we heard a suspicious transmission on our departure out of Boston, ah, with someone, ah, it sounded like someone keyed the mikes and said ah everyone ah stay in your seats.`

`356:    Meanwhile, a manager from Boston Center reported that they had deciphered what they had heard in one of the first hijacker transmissions from American 11: Boston Center: Hey . . . you still there?`

`360:    Boston Center: . . . as far as the tape, Bobby seemed to think the guy said that "we have planes." Now, I don't know if it was because it was the accent, or if there's more than one, but I'm gonna, I'm gonna reconfirm that for you, and I'll get back to you real quick. Okay? New England Region: Appreciate it.`

`364:    Boston Center: Planes, as in plural.`

`366:    Boston Center: It sounds like, we're talking to New York, that there's another one aimed at the World Trade Center.`

`370:    Boston Center: A second one just hit the Trade Center.`

`374:    Boston Center immediately advised the New England Region that it was going to stop all departures at airports under its control. At 9:05, Boston Center confirmed for both the FAA Command Center and the New England Region that the hijackers aboard American 11 said "we have planes." At the same time, New York Center declared "ATC zero"-meaning that aircraft were not permitted to depart from, arrive at, or travel through New York Center's airspace until further notice.`

`376:    Within minutes of the second impact, Boston Center instructed its controllers to inform all aircraft in its airspace of the events in New York and to advise aircraft to heighten cockpit security. Boston Center asked the Herndon Command Center to issue a similar cockpit security alert nationwide. We have found no evidence to suggest that the Command Center acted on this request or issued any type of cockpit security alert.`

`404:    By 9:25, FAA's Herndon Command Center and FAA headquarters knew two aircraft had crashed into the World Trade Center. They knew American 77 was lost. At least some FAA officials in Boston Center and the New England Region knew that a hijacker on board American 11 had said "we have some planes." Concerns over the safety of other aircraft began to mount. A manager at the Herndon Command Center asked FAA headquarters if they wanted to order a "nationwide ground stop." While this was being discussed by executives at FAA headquarters, the Command Center ordered one at 9:25.`

`412:    At 9:21, NEADS received a report from the FAA: FAA: Military, Boston Center. I just had a report that American 11 is still in the air, and it's on its way towards-heading towards Washington. NEADS: Okay. American 11 is still in the air?`

`434:    The mention of a "third aircraft" was not a reference to American 77. There was confusion at that moment in the FAA. Two planes had struck the World Trade Center, and Boston Center had heard from FAA headquarters in Washington that American 11 was still airborne. We have been unable to identify the source of this mistaken FAA information.`

`440:    At the suggestion of the Boston Center's military liaison, NEADS contacted the FAA's Washington Center to ask about American 11. In the course of the conversation, a Washington Center manager informed NEADS:"We're looking- we also lost American 77." The time was 9:34. This was the first notice to the military that American 77 was missing, and it had come by chance. If NEADS had not placed that call, the NEADS air defenders would have received no information whatsoever that the flight was even missing, although the FAA had been searching for it. No one at FAA headquarters ever asked for military assistance with American 77.`

`442:    At 9:36, the FAA's Boston Center called NEADS and relayed the discovery about an unidentified aircraft closing in on Washington:"Latest report. Aircraft VFR [visual flight rules] six miles southeast of the White House. . . . Six, southwest. Six, southwest of the White House, deviating away." This startling news prompted the mission crew commander at NEADS to take immediate control of the airspace to clear a flight path for the Langley fighters:"Okay, we're going to turn it . . . crank it up. . . . Run them to the White House." He then discovered, to his surprise, that the Langley fighters were not headed north toward the Baltimore area as instructed, but east over the ocean." I don't care how many windows you break," he said." Damn it. . . . Okay. Push them back."`

`448:    Right after the Pentagon was hit, NEADS learned of another possible hijacked aircraft. It was an aircraft that in fact had not been hijacked at all. After the second World Trade Center crash, Boston Center managers recognized that both aircraft were transcontinental 767 jetliners that had departed Logan Airport. Remembering the "we have some planes" remark, Boston Center guessed that Delta 1989 might also be hijacked. Boston Center called NEADS at 9:41 and identified Delta 1989, a 767 jet that had left Logan Airport for Las Vegas, as a possible hijack. NEADS warned the FAA's Cleveland Center to watch Delta 1989. The Command Center and FAA headquarters watched it too. During the course of the morning, there were multiple erroneous reports of hijacked aircraft. The report of American 11 heading south was the first; Delta 1989 was the second.`

`598:    We found no evidence that, at this critical time, NORAD's top commanders, in Florida or Cheyenne Mountain, coordinated with their counterparts at FAA headquarters to improve awareness and organize a common response. Lower-level officials improvised-for example, the FAA's Boston Center bypassed the chain of command and directly contacted NEADS after the first hijacking. But the highest-level Defense Department officials relied on the NMCC's air threat conference, in which the FAA did not participate for the first 48 minutes.`

-The two commands that I used with `grep -n` looked for and returned the line in the file where the specified string ("computer" and "Boston") was located. If there are multiple occurences, it returns all lines that include the specified string. This would be useful in the case where we are looking for the specific locations of occurences for a specified string.

## **Sources**
- https://man7.org/linux/man-pages/man1/grep.1.html
- https://docs.rackspace.com/docs/use-the-linux-grep-command
