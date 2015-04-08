---
layout: page
title: Reading
permalink: /reading/
---

* [Semi-Technical Reads](#technical)
* [Working in Software](#career)
* [Self-Improvement and Social Psychology](#psych)
* [Health and Fitness](#health)

<aside><p>Books I've enjoyed in the past year or so, plus a few I'm hoping to crack open soon. In no particular order.</p></aside>

<h2 id="technical" class="anchor">Semi-Technical Reads</h2>

---
ul>
{% for book in site.data.reading %}
  <li>
    <a href="https://github.com/{{ member.github }}">
      {{ member.name }}
    </a>
  </li>
{% endfor %}
</ul>

{% for book in site.data.reading %}
<table class="minimum">
  <tr>
  	<td><img src="{{ site.url }}{{ book.image }}" alt="{{ book.title }}"/></td>
    <td><a href="{{ book.link }}"><b>{{ book.title }}<b/></a>
    {% if book.author %}<br>by {{ book.author }}{% endif %}
    <br>{{ book.status }}
    {% if book.description %}<br>{{ book.description }}{% endif %}
    </td>
  </tr>
</table>
{% endfor %}

[**TCP/IP For Dummies**](http://smile.amazon.com/TCP-IP-Dummies-Candace-Leiden-ebook/dp/B002MZUPUG/ref=tmm_kin_title_0?_encoding=UTF8&sr=8-6&qid=1425965841)<br><i class="fa fa-refresh"></i> In Progress<br><br>Gotta learn it somehow. |

---

| ![TCP/IP For Dummies]({{ site.url }}/assets/tcp-ip.jpg) | [**TCP/IP For Dummies**](http://smile.amazon.com/TCP-IP-Dummies-Candace-Leiden-ebook/dp/B002MZUPUG/ref=tmm_kin_title_0?_encoding=UTF8&sr=8-6&qid=1425965841)<br><i class="fa fa-refresh"></i> In Progress<br><br>Gotta learn it somehow. |

<br>

| <img src="{{ site.url }}/assets/javascriptthegoodparts.jpg" alt="JavaScript: The Good Parts"/> | [**JavaScript: The Good Parts**](http://smile.amazon.com/gp/product/B0026OR2ZY/ref=kinw_myk_ro_title)<br>by Douglas Crockford<br><i class="fa fa-refresh"></i> In Progress |

<br>

| <img src="{{ site.url }}/assets/ruby_on_rails_tutorial.png" alt="Ruby on Rails Tutorial"/> | [**Ruby on Rails Tutorial**](https://www.railstutorial.org/book)<br>by Michael Hartl<br><i class="fa fa-refresh"></i> In Progress |

<br>

| <img src="{{ site.url }}/assets/code.jpg" alt="Code"/> | [**Code**](http://smile.amazon.com/Code-Developer-Practices-Charles-Petzold-ebook/dp/B00JDMPOK2/ref=sr_1_1?s=digital-text&ie=UTF8&qid=1423800084&sr=1-1&keywords=code)<br>by Charles Petzold<br><i class="fa fa-refresh"></i> In Progress |

<br>

| <img src="{{ site.url }}/assets/crackingthecodinginterview.jpg" alt="Cracking the Coding Interview"/> | [**Cracking the Coding Interview: 150 Programming Questions and Solutions**](http://www.amazon.com/Cracking-Coding-Interview-Programming-Questions/dp/098478280X/ref=pd_sim_b_4?ie=UTF8&refRID=0EYRFHWN4DR7S6X7YAM6)<br>by Gayle Laakmann McDowell<br><i class="fa fa-refresh"></i> In Progress |

<br>

| <img src="{{ site.url }}/assets/algorithms.jpg" alt="Introduction to Algorithms, 3rd Ed."/> | [**Introduction to Algorithms, 3rd Ed.**](http://www.amazon.com/Introduction-Algorithms-3rd-Thomas-Cormen/dp/0262033844/ref=sr_1_1?ie=UTF8&qid=1424666330&sr=8-1&keywords=intro+to+algorithms)<br>by Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, and Clifford Stein<br><i class="fa fa-refresh"></i> In Progress |

<br>

| <img src="{{ site.url }}/assets/algo-design.jpg" alt="The Algorithm Design Manual"/> | [**The Algorithm Design Manual**](http://www.amazon.com/Algorithm-Design-Manual-Steven-Skiena-ebook/dp/B00B8139Z8/ref=sr_1_1_twi_2_kin?ie=UTF8&qid=1427655079&sr=8-1&keywords=the+algorithm+design+manual)<br>by Steven Skiena <br><i class="fa fa-ellipsis-h"></i> *Owned, Not Started* |

<br>

| <img src="{{ site.url }}/assets/progit.png" alt="Pro Git"/> | [**Pro Git**](http://git-scm.com/book/en/v2)<br>by Scott Chacon and Ben Straub<br><i class="fa fa-refresh"></i> In Progress |











<h2 id="career" class="anchor">Working in Software</h2>

---

| <img src="{{ site.url }}/assets/facts-and-fallacies.jpg" alt="Facts and Fallacies of Software Engineering"/> | [**Facts and Fallacies of Software Engineering**](http://www.amazon.com/Facts-Fallacies-Software-Engineering-Robert-ebook/dp/B001TKD4RG/ref=tmm_kin_title_0?_encoding=UTF8&sr=8-2&qid=1424666218)<br>by Robert L. Glass<br><i class="fa fa-refresh"></i> In Progress<br><br>This old-school classic really hits the nail on the head with its fifty-five facts and ten fallacies. Book review coming soon. | 

<br>

| <img src="{{ site.url }}/assets/codecomplete2.jpg" alt="Code Complete, 2nd Ed."/> | [**Code Complete, 2nd Ed.**](http://www.amazon.com/Code-Complete-Practical-Handbook-Construction/dp/0735619670/ref=sr_1_1?ie=UTF8&qid=1424467980&sr=8-1&keywords=code+complete)<br>by Steve McConnell<br><i class="fa fa-ellipsis-h"></i> *Not Started*<br><br>I have a great set of best practices checklists that were derived from this book, can't wait to read it in full. | 

<br>

| <img src="{{ site.url }}/assets/technicalleader.jpg" alt="Becoming a Technical Leader"/> | [**Becoming a Technical Leader**](http://smile.amazon.com/gp/product/B004J4VV3I/ref=kinw_myk_ro_title)<br>by Gerald Weinberg<br><i class="fa fa-check-square-o"></i> **Completed**<br><br>Applicable in any field. Book review coming soon-ish. | 

<br>

| <img src="{{ site.url }}/assets/apprenticeshippatterns.jpg" alt="Apprenticeship Patterns"/> | [**Apprenticeship Patterns**](http://www.amazon.com/Apprenticeship-Patterns-Guidance-Aspiring-Craftsman-ebook/dp/B002RMSZ7E/ref=tmm_kin_title_0?_encoding=UTF8&sr=&qid=)<br>by Dave Hoover and Adewale Oshineye<br><i class="fa fa-check-square-o"></i> **Completed**<br><br>Great read, lots to discuss here. I'm a big fan of the growth mindset promoted in this O'Reilly advice tome. [Read it for free.](http://chimera.labs.oreilly.com/books/1234000001813/index.html) | 

<br>

| <img src="{{ site.url }}/assets/joelspolsky.jpg" alt="Joel Spolsky"/> | **Joel Spolsky**<br>The classic. [Check out his blog.](http://www.joelonsoftware.com/) |

| <img src="{{ site.url }}/assets/joel_on_software.jpg" alt="Joel on Software"/> | [**Joel on Software**](http://smile.amazon.com/gp/product/B001NRNIMG/ref=kinw_myk_ro_title)<br>by Joel Spolsky<br><i class="fa fa-check-square-o"></i> **Completed** |

| <img src="{{ site.url }}/assets/smartandgetsthingsdone.jpg" alt="Smart and Gets Things Done"/> | [**Smart and Gets Things Done: Joel Spolsky's Concise Guide to Finding the Best Technical Talent**](http://smile.amazon.com/Smart-Gets-Things-Done-Technical/dp/1590598385/ref=asap_bc?ie=UTF8)<br>by Joel Spolsky<br><i class="fa fa-check-square-o"></i> **Completed** | 

<br>

| <img src="{{ site.url }}/assets/jeffatwood.jpg" alt="Jeff Atwood"/> | **Jeff Atwood**<br>Super insightful. [Check out his blog.](http://blog.codinghorror.com/) | 

| <img src="{{ site.url }}/assets/effectiveprogramming.png" alt="Effective Programming"/> | [**Effective Programming: More Than Writing Code**](http://smile.amazon.com/gp/product/B008HUMTO0/ref=kinw_myk_ro_title)<br>by Jeff Atwood<br><i class="fa fa-check-square-o"></i> **Completed** | 

| <img src="{{ site.url }}/assets/howtostopsucking.png" alt="How to Stop Sucking and Be Awesome Instead"/> | [**How to Stop Sucking and Be Awesome Instead**](http://smile.amazon.com/gp/product/B00BU3KPQU/ref=kinw_myk_ro_title)<br>by Jeff Atwood <br><i class="fa fa-check-square-o"></i> **Completed** | 

<br>

| <img src="{{ site.url }}/assets/codersatwork.jpg" alt="Coders At Work"/> | [**Coders at Work**](http://smile.amazon.com/gp/product/B002RHN7RM/ref=kinw_myk_ro_title)<br>by Peter Seibel <br><i class="fa fa-refresh"></i> In Progress | 

<br>

| <img src="{{ site.url }}/assets/97-things.jpg" alt="97 Things"/> | [**97 Things Every Programmer Should Know**](http://smile.amazon.com/gp/product/B002RHN7RM/ref=kinw_myk_ro_title)<br><i class="fa fa-refresh"></i> In Progress | 

<br>

| <img src="{{ site.url }}/assets/behindcloseddoors.png" alt="Behind Closed Doors"/> | [**Behind Closed Doors: Secrets of Great Management**](http://smile.amazon.com/gp/product/B00A4OA6UQ/ref=kinw_myk_ro_title)<br>by Johanna Rothman and Esther Derby<br><i class="fa fa-refresh"></i> In Progress<br><br>Reads more like a story than a career advice book. | 













<h2 id="psych" class="anchor">Self-Improvement and Social Psychology</h2>

---

| <img src="{{ site.url }}/assets/jonkabat-zinn.jpg" alt="Jon Kabat-Zinn"/> | **Jon Kabat-Zinn**<br>I love the way he talks. Hugely influential in provoking mainstream awareness of the health benefits of meditation. | 

| <img src="{{ site.url }}/assets/fullcatastropheliving.jpg" alt="Full Catastrophe Living"/> | [**Full Catastrophe Living: Using the Wisdom of Your Body and Mind to Face Stress, Pain, and Illness**](http://www.amazon.com/Full-Catastrophe-Living-Wisdom-Illness/dp/0385303122/ref=cm_cr_if_orig_subj?ie=UTF8&linkCode=xm2&tag=audiblecom0f-20)<br>by Jon Kabat-Zinn ([audiobook](http://www.amazon.com/Full-Catastrophe-Living-Wisdom-Illness/dp/B00115MP3S/ref=tmm_aud_swatch_0?_encoding=UTF8&sr=&qid=)) <br><i class="fa fa-check-square-o"></i> **Completed** | 

| <img src="{{ site.url }}/assets/whereveryougo.jpg" alt="Wherever You Go, There You Are"/> | [**Wherever You Go, There You Are: Mindfulness Meditation In Everyday Life**](http://www.amazon.com/Wherever-You-There-Are-Mindfulness-ebook/dp/B0037B6QSY/ref=tmm_kin_swatch_0?_encoding=UTF8&sr=&qid=)<br>by Jon Kabat-Zinn<br><i class="fa fa-refresh"></i> In Progress |

 <br>

| <img src="{{ site.url }}/assets/thewillpowerinstinct.jpg" alt="The Willpower Instinct"/> | [**The Willpower Instinct**](http://www.amazon.com/Willpower-Instinct-Self-Control-Works-Matters-ebook/dp/B005ERIRZE/ref=sr_1_1?ie=UTF8&qid=1423798366&sr=8-1&keywords=the+willpower+instinct)<br>by Kelly McGonigal Ph.D.<br><i class="fa fa-check-square-o"></i> **Completed**<br><br>Solid breakdown of the research that shows how our brains handle impulsiveness, and why it's not always a bad thing. I definitely recommend the [audiobook](http://www.amazon.com/The-Willpower-Instinct-Self-Control-Matters/dp/B006TI7MNA/ref=tmm_aud_title_0?ie=UTF8&qid=1426227731&sr=1-1), and at ~$6 it's a steal. Book review coming eventually. | 

<br>

| <img src="{{ site.url }}/assets/sevenhabits.jpg" alt="The 7 Habits of Highly Effective People"/> | [**The 7 Habits of Highly Effective People: Powerful Lessons in Personal Change**](http://smile.amazon.com/Habits-Highly-Effective-People-Anniversary-ebook/dp/B00GOZV3TM/ref=sr_1_1?ie=UTF8&qid=1423798461&sr=8-1&keywords=7+habits)<br>by Stephen R. Covey<br><i class="fa fa-check-square-o"></i> **Completed**<br><br>Check out my [book review here.](http://shelbyspees.github.io/speesblog/2015/03/02/book-review-seven-habits.html) | 

<br>

| <img src="{{ site.url }}/assets/dalecarnegie.jpg" alt="Dale Carnegie"/>| **Dale Carnegie**<br>I like Dale Carnegie because his writing smacks you upside the head and asks, "Why aren't you doing this, dummy?!" None of it is outside the scope of common sense, but really how common is it anyway? | 

| <img src="{{ site.url }}/assets/howtowinfriends.jpg" alt="How to Win Friends & Influence People"/> | [**How to Win Friends & Influence People**](http://smile.amazon.com/How-Win-Friends-Influence-People-ebook/dp/B003WEAI4E/ref=sr_1_1?ie=UTF8&qid=1423798589&sr=8-1&keywords=how+to+win+friends+and+influence+people)<br>by Dale Carnegie <br><i class="fa fa-check-square-o"></i> **Completed** |

| <img src="{{ site.url }}/assets/howtostopworrying.jpg" alt="How to Stop Worrying and Start Living"/> | [**How to Stop Worrying and Start Living**](http://smile.amazon.com/How-Stop-Worrying-Start-Living-ebook/dp/B003WIYCCY/ref=pd_sim_kstore_1?ie=UTF8&refRID=10NZZDZZJ7ZCE437W329)<br>by Dale Carnegie <br><i class="fa fa-refresh"></i> In Progress | 

<br>

| <img src="{{ site.url }}/assets/emotional-intelligence.jpg" alt="Emotional Intelligence"/> | [**Working with Emotional Intelligence**](http://www.amazon.com/Working-Emotional-Intelligence-Daniel-Goleman-ebook/dp/B000JMKTN2/ref=tmm_kin_swatch_0?_encoding=UTF8&sr=8-1&qid=1426226654)<br>by Daniel Goleman<br><i class="fa fa-refresh"></i> In Progress<br><br>I won this book in a raffle. It's right up my alley. Book review coming soon. | 

<br>

| <img src="{{ site.url }}/assets/leanin.jpg" alt="Lean In"/> | [**Lean In: Women, Work, and the Will to Lead**](http://smile.amazon.com/gp/product/B009LMTDL0/ref=kinw_myk_ro_title)<br>by Sheryl Sandberg<br><i class="fa fa-check-square-o"></i> **Completed** | 

<br>

| <img src="{{ site.url }}/assets/womenomics.png" alt="Womenomics"/> | [**Womenomics**](http://smile.amazon.com/gp/product/B002BD2V0G/ref=kinw_myk_ro_title)<br>by Katty Kay and Claire Shipman<br><i class="fa fa-check-square-o"></i> **Completed**<br><br>I liked this book because it discussed how promoting workplace equality for women depends on promoting domestic equality for men. Flex time for everyone and universal parental leave are some possible solutions. | 

<br>

| <img src="{{ site.url }}/assets/theconfidencecode.jpg" alt="The Confidence Code"/> | [**The Confidence Code: The Science and Art of Self-Assurance---What Women Should Know**](http://smile.amazon.com/gp/product/B00DB368AY/ref=kinw_myk_ro_title)<br>by Katty Kay and Claire Shipman<br><i class="fa fa-ellipsis-h"></i> *Owned, Not Started* | 

<br>

| <img src="{{ site.url }}/assets/59seconds.jpg" alt="59seconds"/> | [**59 Seconds: Think a Little, Change a Lot**](http://smile.amazon.com/gp/product/B002W8QXHW/ref=kinw_myk_ro_title)<br>by Richard Wiseman<br><i class="fa fa-check-square-o"></i> **Completed** | 

<br>

| <img src="{{ site.url }}/assets/mindset.jpg" alt="Mindset"/> | [**Mindset: The New Psychology of Success**](http://smile.amazon.com/gp/product/B000FCKPHG/ref=kinw_myk_ro_title)<br>by Carol Dweck<br><i class="fa fa-check-square-o"></i> **Completed**<br>I want to review this one soon. It had some of the best advice I've ever read. | 

<br>

| <img src="{{ site.url }}/assets/thepowerofhabit.jpg" alt="The Power of Habit"/> | [**The Power of Habit: Why We Do What We Do in Life and Business**](http://smile.amazon.com/gp/product/B0055PGUYU/ref=kinw_myk_ro_title)<br>by Charles Duhigg <br><i class="fa fa-check-square-o"></i> **Completed** | 

<br>

| <img src="{{ site.url }}/assets/quiet.jpg" alt="Quiet"/> | [**Quiet: The Power of Introverts in a World that Can't Stop Talking**](http://smile.amazon.com/gp/product/B004J4WNL2/ref=kinw_myk_ro_title)<br>by Susan Cain<br><i class="fa fa-refresh"></i> In Progress | 

<br>

| <img src="{{ site.url }}/assets/solvingtheprocrastinationpuzzle.jpg" alt="Solving the Procrastination Puzzle"/> | [**Solving the Procrastination Puzzle: A Concise Guide to Strategies for Change**](http://www.amazon.com/Solving-Procrastination-Puzzle-Concise-Strategies-ebook/dp/B00DGZKJ3Y/ref=cm_cr_if_orig_subj?ie=UTF8&linkCode=xm2&tag=audiblecom0f-20)<br>by Timothy A. Pychyl ([check out his podcast](http://iprocrastinate.libsyn.com/))<br><i class="fa fa-check-square-o"></i> **Completed** | 












<h2 id="health" class="anchor">Health and Fitness</h2>

---

Starting Strength

Ultramarathon Runner

Born to Run

Mindless Eating: Why We Eat More Than We Think