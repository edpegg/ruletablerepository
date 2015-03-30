# Introduction #

There are 450 unique unresolved 2-state 2-color turmites left. This is a subpage of EdPeggsBusyBeaverTurmiteChallenge.

I simulated all 2<sup>16</sup>=65,536 rules of the 2s2c turmites and noted below how much of each type resolved at regular iteration steps (powers of 10).

Unique rules exclude reflections, rotations, 'odd' rotations and slower versions. In case of doubles, I always take the one to be unique as the one that has the lowest sorting order. For example, In this pair of doubles, i take the first:<br>
t22r120041121010<br>
t22r180041181010<br>
<br>
t22r120041121010 is a file-friendly notation I'm using. "t22" means turmite with 2 states and 2 colors, so the rule string is <code>{{{1,2,0},{0,4,1}},{{1,2,1},{0,1,0}}}</code>.<br>
<br>
<h2>Resolved rules</h2>

This table lists counts of resolved turmites for various classes.<br>
<br>
<table cellpadding='2' cellspacing='0' border='1'><tr><th align='right'>Resolved at or below iteration:</th><th></th><th>0</th><th>10<sup>3</sup></th><th>10<sup>4</sup></th><th>10<sup>5</sup></th><th>10<sup>6</sup></th><th>10<sup>7</sup></th><th>10<sup>8</sup></th><th>10<sup>9</sup></th><th>10<sup>10</sup></th><th>10<sup>11</sup></th><th>10<sup>12</sup></th><th>10<sup>13</sup></th><th></th><th>Sum</th></tr><tr><td></td><td></td><td></td></tr><tr><th align='right'>1</th><th>Highway</th><th align='right'>Classic</th><td align='right'>Rules: 15360<br></br></td><td align='right'>Rules: 4645<br></br></td><td align='right'>Rules: 136<br>Unique: 44</br></td><td align='right'>Rules: 180<br>Unique: 41</br></td><td align='right'>Rules: 80<br>Unique: 24</br></td><td align='right'>Rules: 82<br>Unique: 26</br></td><td align='right'>Rules: 118<br>Unique: 23</br></td><td align='right'>Rules: 90<br>Unique: 25</br></td><td align='right'>Rules: 58<br>Unique: 17</br></td><td></td><td align='right'>Rules: 2<br>Unique: 1</br></td><td align='right'>Rules: 2<br>Unique: 1</br></td><td align='right'>Rules: 20753<br></br></td></tr><tr><th align='right'>2</th><th>Unary counter</th><th align='right'>Single</th><td align='right'>Rules: 12<br></br></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td align='right'>Rules: 12<br></br></td></tr><tr><th align='right'>3</th><th align='right'>Double</th><td align='right'>Rules: 2473<br></br></td><td align='right'>Rules: 122<br>Unique: 27</br></td><td align='right'>Rules: 12<br>Unique: 4</br></td><td align='right'>Rules: 8<br>Unique: 3</br></td><td align='right'>Rules: 12<br>Unique: 5</br></td><td align='right'>Rules: 14<br>Unique: 5</br></td><td></td><td align='right'>Rules: 8<br>Unique: 3</br></td><td></td><td></td><td></td><td></td><td align='right'>Rules: 2649<br></br></td></tr><tr><th align='right'>4</th><th align='right'>Quadruple</th><td align='right'>Rules: 18<br></br></td><td></td><td></td><td></td><td></td><td align='right'>Rules: 4<br>Unique: 1</br></td><td></td><td></td><td></td><td></td><td></td><td></td><td align='right'>Rules: 22<br></br></td></tr><tr><th align='right'>5</th><th>Binary counter</th><th align='right'>Single</th><td align='right'>Rules: 4<br></br></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td align='right'>Rules: 4<br></br></td></tr><tr><th align='right'>6</th><th align='right'>Double</th><td align='right'>Rules: 1134<br></br></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td align='right'>Rules: 1134<br></br></td></tr><tr><th align='right'>7</th><th align='right'>Quadruple</th><td align='right'>Rules: 24<br></br></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td align='right'>Rules: 24<br></br></td></tr><tr><th align='right'>8</th><th>Langton</th><th align='right'>Classic</th><td align='right'>Rules: 806<br>Unique: 1</br></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td align='right'>Rules: 806<br>Unique: 1</br></td></tr><tr><th align='right'>9</th><th align='right'>Look-alike</th><td></td><td></td><td></td><td align='right'>Rules: 224<br>Unique: 10</br></td><td></td><td></td><td align='right'>Rules: 4<br>Unique: 1</br></td><td></td><td></td><td></td><td></td><td></td><td align='right'>Rules: 228<br>Unique: 11</br></td></tr><tr><th>10</th><th align='right'>All highways</th><td align='right'>Rules: 19831<br></br></td><td align='right'>Rules: 4767<br></br></td><td align='right'>Rules: 148<br>Unique: 48</br></td><td align='right'>Rules: 412<br>Unique: 54</br></td><td align='right'>Rules: 92<br>Unique: 29</br></td><td align='right'>Rules: 100<br>Unique: 32</br></td><td align='right'>Rules: 122<br>Unique: 24</br></td><td align='right'>Rules: 98<br>Unique: 28</br></td><td align='right'>Rules: 58<br>Unique: 17</br></td><td></td><td align='right'>Rules: 2<br>Unique: 1</br></td><td align='right'>Rules: 2<br>Unique: 1</br></td><td align='right'>Rules: 25632<br></br></td></tr><tr><th>11</th><th>Wedge</th><th></th><th align='right'>Single</th><td></td><td align='right'>Rules: 8<br>Unique: 2</br></td><td align='right'>Rules: 4<br>Unique: 1</br></td><td align='right'>Rules: 2<br>Unique: 1</br></td><td align='right'>Rules: 8<br>Unique: 1</br></td><td align='right'>Rules: 4<br>Unique: 1</br></td><td align='right'>Rules: 4<br>Unique: 1</br></td><td></td><td align='right'>Rules: 2<br>Unique: 1</br></td><td></td><td></td><td></td><td align='right'>Rules: 32<br>Unique: 8</br></td></tr><tr><th>12</th><th align='right'>Double</th><td align='right'>Rules: 4<br>Unique: 1</br></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td align='right'>Rules: 4<br>Unique: 1</br></td></tr><tr><th>13</th><th align='right'>Quadruple</th><td align='right'>Rules: 2<br>Unique: 1</br></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td align='right'>Rules: 2<br>Unique: 1</br></td></tr><tr><th>14</th><th align='right'>All wedges</th><td align='right'>Rules: 6<br>Unique: 2</br></td><td align='right'>Rules: 8<br>Unique: 2</br></td><td align='right'>Rules: 4<br>Unique: 1</br></td><td align='right'>Rules: 2<br>Unique: 1</br></td><td align='right'>Rules: 8<br>Unique: 1</br></td><td align='right'>Rules: 4<br>Unique: 1</br></td><td align='right'>Rules: 4<br>Unique: 1</br></td><td></td><td align='right'>Rules: 2<br>Unique: 1</br></td><td></td><td></td><td></td><td align='right'>Rules: 38<br>Unique: 10</br></td></tr><tr><th>15</th><th>Spiral</th><th>Square</th><th align='right'>Linear</th><td align='right'>Rules: 693<br></br></td><td align='right'>Rules: 4<br>Unique: 1</br></td><td align='right'>Rules: 8<br>Unique: 2</br></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td align='right'>Rules: 705<br></br></td></tr><tr><th>16</th><th align='right'>Power-growth</th><td align='right'>Rules: 114<br>Unique: 22</br></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td align='right'>Rules: 114<br>Unique: 22</br></td></tr><tr><th>17</th><th align='right'>Odd shaped</th><td align='right'>Rules: 48<br>Unique: 19</br></td><td></td><td></td><td align='right'>Rules: 8<br>Unique: 1</br></td><td align='right'>Rules: 4<br>Unique: 1</br></td><td></td><td></td><td align='right'>Rules: 4<br>Unique: 1</br></td><td></td><td></td><td></td><td></td><td align='right'>Rules: 64<br>Unique: 22</br></td></tr><tr><th>18</th><th align='right'>All spirals</th><td align='right'>Rules: 855<br></br></td><td align='right'>Rules: 4<br>Unique: 1</br></td><td align='right'>Rules: 8<br>Unique: 2</br></td><td align='right'>Rules: 8<br>Unique: 1</br></td><td align='right'>Rules: 4<br>Unique: 1</br></td><td></td><td></td><td align='right'>Rules: 4<br>Unique: 1</br></td><td></td><td></td><td></td><td></td><td align='right'>Rules: 883<br></br></td></tr><tr><th>19</th><th>Stuck</th><th align='right'></th><td align='right'>Rules: 23548<br></br></td><td align='right'>Rules: 13358<br></br></td><td align='right'>Rules: 162<br>Unique: 53</br></td><td align='right'>Rules: 12<br>Unique: 3</br></td><td align='right'>Rules: 28<br>Unique: 9</br></td><td align='right'>Rules: 8<br>Unique: 2</br></td><td></td><td></td><td align='right'>Rules: 8<br>Unique: 2</br></td><td align='right'>Rules: 4<br>Unique: 1</br></td><td></td><td></td><td align='right'>Rules: 37128<br></br></td></tr><tr><td></td><td></td><td></td></tr><tr><th>20</th><th align='right'>All</th><td align='right'>Rules: 44240<br></br></td><td align='right'>Rules: 18137<br></br></td><td align='right'>Rules: 322<br>Unique: 104</br></td><td align='right'>Rules: 434<br>Unique: 59</br></td><td align='right'>Rules: 132<br>Unique: 40</br></td><td align='right'>Rules: 112<br>Unique: 35</br></td><td align='right'>Rules: 126<br>Unique: 25</br></td><td align='right'>Rules: 102<br>Unique: 29</br></td><td align='right'>Rules: 68<br>Unique: 20</br></td><td align='right'>Rules: 4<br>Unique: 1</br></td><td align='right'>Rules: 2<br>Unique: 1</br></td><td align='right'>Rules: 2<br>Unique: 1</br></td><td align='right'>Rules: 63681<br></br></td></tr></table>

Notes:<br>
<ul><li><b>0 and 10</b><sup>3</sup> iterations:<b>For some classes, it's unfeasible for me to check how much are unique.<br>
</li><li></b>2, 3, 4:<b>A Unary highway looks similar to a Classic highway, except that the turmite travels back to the start every time it grows.</b><br>
</li><li><b>15, 16:</b> This includes rotated squares (and diamonds), but not the parallelograms.<br>
</li><li><b>16:</b> The growth ratio is asymptotic and limits to: c・iter<sup>2/3</sup>.<br>
</li><li><b>10</b><sup>10</sup> and up:<b>Incomplete numbers. See description above.</li></ul></b>

<h2>Interesting rules</h2>

Some interesting rules to try or to study:<br>
<br>
<table><thead><th> t22r021010181020 </th><th> Unresolved </th><th> One-dimensional chaos, 2-wide. </th></thead><tbody>
<tr><td> t22r021021120181 </td><td> Unresolved </td><td> Slowest growing two-dimensional rule. </td></tr>
<tr><td> t22r041110141010 </td><td> Unresolved </td><td> One-dimensional chaos, 1-wide. |Slowest growing rule overall. </td></tr>
<tr><td> t22r111120141080 </td><td> Unresolved </td><td> Chaotic thick spiral with high visits-count spots. </td></tr>
<tr><td> t22r120081180041 </td><td> Resolved </td><td> Highest period highway. </td></tr>
<tr><td> t22r120081180111 </td><td> Resolved </td><td> Asymetrically growing double unary highway. One side grows twice as fast. </td></tr>
<tr><td> t22r120111120080 </td><td> Resolved </td><td> Most complex 'stuck'-pattern so far. </td></tr>
<tr><td> t22r120141011020<br>A different one:<br>t22r111041120180 </td><td> Unresolved </td><td> Spiral with embedded wedges, slightly chaotical. </td></tr>
<tr><td> t22r121081120011<br>A different one:<br>t22r121181120011 </td><td> Unresolved </td><td> Two binary counters that interfere with each other to create one-dimensional chaos. </td></tr>
<tr><td> t22r121110140080<br>A smaller one:<br>t22r141021180111 </td><td> Resolved </td><td> Double highway which aren't co-linear. </td></tr>
<tr><td> t22r121181110040 </td><td> Unresolved </td><td> Spiral with chaotic highways internally. </td></tr>
<tr><td> t22r140111121040 </td><td> Resolved </td><td> Highest ratio of highway period vs. iteration at which highway starts. </td></tr></tbody></table>

<h2>Unresolved rules</h2>

These rules are unsimulatable by any of my experimental software, and will take me weeks to months to similate to just 10 billion iterations in Golly:<br>
<br>
t22r011010120021 gens 10000000000 area 41197756 maxVisits 1083 colors 59.36% 40.64%<br>
t22r011010120081 gens 10000000000 area 35934867 maxVisits 1145 colors 66.36% 33.64%<br>
t22r011010120111 gens 10000000000 area 16443021 maxVisits 2317 colors 50.02% 49.98%<br>
t22r011010121180 gens 10000000000 area 43473139 maxVisits 903 colors 49.92% 50.08%<br>
t22r011010140021 gens 10000000000 area 5786748 maxVisits 6365 colors 42.51% 57.49%<br>
t22r011011120081 gens 10000000000 area 19636834 maxVisits 1602 colors 60.51% 39.49%<br>
t22r011011120121 gens 10000000000 area 3468126 maxVisits 11858 colors 0.14% 99.86%<br>
t22r011020120081 gens 10000000000 area 37617243 maxVisits 1120 colors 67.63% 32.37%<br>
t22r011020120121 gens 10000000000 area 10950596 maxVisits 4431 colors 50.00% 50.00%<br>
t22r011020120141 gens 10000000000 area 20541521 maxVisits 1902 colors 49.99% 50.01%<br>
t22r011020120181 gens 10000000000 area 22689142 maxVisits 1745 colors 50.01% 49.99%<br>
t22r011020121140 gens 10000000000 area 29753289 maxVisits 2383 colors 49.89% 50.11%<br>
t22r011020180041 gens 10000000000 area 21299344 maxVisits 1628 colors 69.48% 30.52%<br>
t22r011020180081 gens 10000000000 area 28120966 maxVisits 1524 colors 63.54% 36.46%<br>
t22r011021120041 gens 10000000000 area 12988392 maxVisits 3041 colors 49.69% 50.31%<br>
t22r011021120141 gens 10000000000 area 14847532 maxVisits 2238 colors 0.16% 99.84%<br>
t22r011021121040 gens 10000000000 area 17337072 maxVisits 4313 colors 58.86% 41.14%<br>
t22r011021140181 gens 10000000000 area 5959359 maxVisits 6015 colors 0.05% 99.95%<br>
t22r011021180021 gens 10000000000 area 26216418 maxVisits 1351 colors 61.07% 38.93%<br>
t22r011021180041 gens 10000000000 area 24924630 maxVisits 1524 colors 55.28% 44.72%<br>
t22r011021180081 gens 10000000000 area 20033121 maxVisits 2042 colors 52.78% 47.22%<br>
t22r011021181020 gens 10000000000 area 42947210 maxVisits 998 colors 57.68% 42.32%<br>
t22r011021181040 gens 10000000000 area 12692773 maxVisits 5203 colors 77.67% 22.33%<br>
t22r011040120121 gens 10000000000 area 6169381 maxVisits 6591 colors 49.96% 50.04%<br>
t22r011040140121 gens 10000000000 area 3166127 maxVisits 10481 colors 50.05% 49.95%<br>
t22r011041121080 gens 10000000000 area 36976853 maxVisits 1199 colors 60.43% 39.57%<br>
t22r121110140081	gens      31503305	area       4453122	maxVisits           109	colors   0.06    0.94<br>
t22r141020180111	gens      50072778	area       6849737	maxVisits           110	colors   0.06    0.94<br>
t22r141111120011 gens 10000000000 area 43891274 maxVisits 877 colors 50.47% 49.53%<br>
t22r141120120011 gens 10000000000 area 18183921 maxVisits 1893 colors 49.97% 50.03%<br>
t22r141121110021	gens 1725966849281<br>
t22r141121180010 gens 10000000000 area 12339915 maxVisits 4132 colors 24.99% 75.01% <br>


The rules below have all been run until 10 billion steps. A few have a 'gens' number less than that because their patterns grew so fast they hit my memory limit of the application used to generate the images and analyzed data. Those rules have been verified to be unresolved at 10 billion with other software.<br>
<br>
t22r011011121080 gens 10000000000 area 19618200 maxVisits 1603 colors 54.74% 45.26%<br>
t22r011040120021 gens 10000000000 area 7757632 maxVisits 5405 colors 62.28% 37.72%<br>
t22r011040120041 gens 10000000000 area 12268734 maxVisits 2620 colors 61.21% 38.79%<br>
t22r011040121180 gens 10000000000 area 3867700 maxVisits 65435 colors 49.97% 50.03%<br>
t22r011040141020 gens 10000000000 area 10667660 maxVisits 2978 colors 61.23% 38.77%<br>
t22r011041120021 gens 10000000000 area 11660442 maxVisits 4190 colors 62.75% 37.25%<br>
t22r011041120111 gens 10000000000 area 41632368 maxVisits 812 colors 1.92% 98.08%<br>
t22r011110120011 gens 10000000000 area 15946376 maxVisits 2281 colors 48.99% 51.01%<br>
t22r011110120021 gens 10000000000 area 18983396 maxVisits 2024 colors 36.57% 63.43%<br>
t22r011110120081 gens 10000000000 area 32989365 maxVisits 1186 colors 46.23% 53.77%<br>
t22r011110121040 gens 10000000000 area 19520917 maxVisits 2052 colors 49.97% 50.03%<br>
t22r011120120011 gens 10000000000 area 26593507 maxVisits 1387 colors 49.96% 50.04%<br>
t22r011120121040 gens 10000000000 area 22046622 maxVisits 1833 colors 49.93% 50.07%<br>
t22r011121120081 gens 10000000000 area 30921279 maxVisits 1470 colors 47.78% 52.22%<br>
t22r011121121080 gens 10000000000 area 41664332 maxVisits 972 colors 49.96% 50.04%<br>
t22r011121141080 gens 10000000000 area 27827708 maxVisits 1453 colors 63.40% 36.60%<br>
t22r011121180011 gens 10000000000 area 19598607 maxVisits 1919 colors 50.19% 49.81%<br>
t22r011121180021 gens 10000000000 area 25140305 maxVisits 1400 colors 52.00% 48.00%<br>
t22r011121180041 gens 10000000000 area 20071938 maxVisits 1735 colors 37.95% 62.05%<br>
t22r011121181080 gens 10000000000 area 13852222 maxVisits 328809279 colors 54.47% 45.53%<br>
t22r011140121040 gens 10000000000 area 6668047 maxVisits 10129 colors 50.03% 49.97%<br>
t22r011141120041 gens 10000000000 area 21099507 maxVisits 2069 colors 67.57% 32.43%<br>
t22r021010110111 gens 10000000000 area 13907705 maxVisits 2452 colors 50.02% 49.98%<br>
t22r021010110181 gens 10000000000 area 37601265 maxVisits 997 colors 50.01% 49.99%<br>
t22r021010120081 gens 10000000000 area 23439264 maxVisits 1711 colors 65.37% 34.63%<br>
t22r021010120121 gens 10000000000 area 7995282 maxVisits 4683 colors 49.95% 50.05%<br>
t22r021010120181 gens 10000000000 area 16709704 maxVisits 2133 colors 50.01% 49.99%<br>
t22r021010121010 gens 10000000000 area 9584302 maxVisits 3787 colors 59.46% 40.54%<br>
t22r021010121110 gens 10000000000 area 17254321 maxVisits 2220 colors 49.97% 50.03%<br>
t22r021010121140 gens 10000000000 area 26667243 maxVisits 1426 colors 49.93% 50.07%<br>
t22r021010121180 gens 10000000000 area 26538537 maxVisits 1341 colors 49.99% 50.01%<br>
t22r021010140081 gens 10000000000 area 5550248 maxVisits 6801 colors 24.52% 75.48%<br>
t22r021010140121 gens 10000000000 area 19054802 maxVisits 1951 colors 49.97% 50.03%<br>
t22r021010140141 gens 10000000000 area 24188811 maxVisits 1590 colors 49.92% 50.08%<br>
t22r021010140181 gens 10000000000 area 19487629 maxVisits 1993 colors 49.97% 50.03%<br>
t22r021010141110 gens 10000000000 area 18774425 maxVisits 2035 colors 49.95% 50.05%<br>
t22r021010141140 gens 10000000000 area 11491038 maxVisits 3317 colors 49.96% 50.04%<br>
t22r021010181140 gens 10000000000 area 29596410 maxVisits 1447 colors 49.88% 50.12%<br>
t22r021011110011 gens 10000000000 area 25997250 maxVisits 1296 colors 60.85% 39.15%<br>
t22r021011110021 gens 10000000000 area 28597444 maxVisits 1379 colors 61.67% 38.33%<br>
t22r021011110041 gens 10000000000 area 29119968 maxVisits 1287 colors 53.40% 46.60%<br>
t22r021011110081 gens 10000000000 area 30394816 maxVisits 1175 colors 59.61% 40.39%<br>
t22r021011120081 gens 10000000000 area 18226258 maxVisits 1919 colors 62.04% 37.96%<br>
t22r021011120111 gens 10000000000 area 10068466 maxVisits 3162 colors 0.88% 99.12%<br>
t22r021011121040 gens 10000000000 area 6347661 maxVisits 6320 colors 58.03% 41.97%<br>
t22r021011121180 gens 10000000000 area 19369425 maxVisits 1931 colors 48.50% 51.50%<br>
t22r021011181020 gens 10000000000 area 32660632 maxVisits 1385 colors 58.69% 41.31%<br>
t22r021011181040 gens 10000000000 area 13887418 maxVisits 3347 colors 62.37% 37.63%<br>
t22r021020110021 gens 10000000000 area 8603531 maxVisits 4430 colors 82.73% 17.27%<br>
t22r021020110041 gens 10000000000 area 28866012 maxVisits 1615 colors 64.84% 35.16%<br>
t22r021020110111 gens 10000000000 area 14390723 maxVisits 2646 colors 50.01% 49.99%<br>
t22r021020110181 gens 10000000000 area 16107232 maxVisits 2241 colors 50.02% 49.98%<br>
t22r021020120111 gens 10000000000 area 2821481 maxVisits 12056 colors 50.14% 49.86%<br>
t22r021020141010 gens 10000000000 area 6575374 maxVisits 6294 colors 62.26% 37.74%<br>
t22r021020181020 gens 10000000000 area 11283793 maxVisits 3157 colors 57.45% 42.55%<br>
t22r021020181180 gens 10000000000 area 29316378 maxVisits 1283 colors 49.95% 50.05%<br>
t22r021021120081 gens 10000000000 area 11966220 maxVisits 2882 colors 62.87% 37.13%<br>
t22r021021120181 gens 10000000000 area 29438 maxVisits 48771579 colors 26.19% 73.81%<br>
t22r021021140181 gens 10000000000 area 2691952 maxVisits 17145 colors 0.09% 99.91%<br>
t22r021040121010 gens 90734845149 area 48109755 maxVisits 6815 density 27.67% colors 53.04% 46.96%<br>
t22r021040121110 gens 10000000000 area 14214157 maxVisits 4541 colors 49.84% 50.16%<br>
t22r021040140111 gens 10000000000 area 6806222 maxVisits 5557 colors 49.99% 50.01%<br>
t22r021041110141 gens 10000000000 area 14989492 maxVisits 2400 colors 0.15% 99.85%<br>
t22r021041120111 gens 10000000000 area 21703359 maxVisits 1503 colors 1.24% 98.76%<br>
t22r021041181180 gens 10000000000 area 27742468 maxVisits 1617 colors 51.15% 48.85%<br>
t22r021080110011 gens 10000000000 area 26801324 maxVisits 1438 colors 67.27% 32.73%<br>
t22r021080110041 gens 10000000000 area 21299344 maxVisits 1628 colors 69.48% 30.52%<br>
t22r021080110081 gens 10000000000 area 38395190 maxVisits 952 colors 67.42% 32.58%<br>
t22r021080120021 gens 10000000000 area 4323579 maxVisits 8866 colors 69.43% 30.57%<br>
t22r021080120121 gens 10000000000 area 30212603 maxVisits 1568 colors 49.95% 50.05%<br>
t22r021080120141 gens 10000000000 area 15804794 maxVisits 2416 colors 49.97% 50.03%<br>
t22r021080120181 gens 10000000000 area 10764959 maxVisits 3086 colors 53.31% 46.69%<br>
t22r021080121010 gens 10000000000 area 16335953 maxVisits 2492 colors 62.96% 37.04%<br>
t22r021080121110 gens 10000000000 area 21138897 maxVisits 1803 colors 49.97% 50.03%<br>
t22r021080140121 gens 10000000000 area 3119437 maxVisits 15865 colors 49.90% 50.10%<br>
t22r021080140181 gens 10000000000 area 31283165 maxVisits 1682 colors 49.92% 50.08%<br>
t22r021080181120 gens 10000000000 area 1630712 maxVisits 121623 colors 50.27% 49.73%<br>
t22r021081110041 gens 10000000000 area 19755469 maxVisits 1947 colors 54.22% 45.78%<br>
t22r021081110111 gens 10000000000 area 46354585 maxVisits 716 colors 2.32% 97.68%<br>
t22r021081110181 gens 10000000000 area 24824604 maxVisits 1612 colors 0.39% 99.61%<br>
t22r021081120081 gens 10000000000 area 20508380 maxVisits 1860 colors 64.53% 35.47%<br>
t22r021081121010 gens 10000000000 area 20700041 maxVisits 1825 colors 58.24% 41.76%<br>
t22r021081181040 gens 10000000000 area 10635147 maxVisits 4201 colors 43.73% 56.27%<br>
t22r021110110081 gens 10000000000 area 30127969 maxVisits 1256 colors 43.43% 56.57%<br>
t22r021110110141 gens 10000000000 area 31349339 maxVisits 1168 colors 0.10% 99.90%<br>
t22r021110120181 gens 10000000000 area 23820895 maxVisits 1543 colors 0.08% 99.92%<br>
t22r021110121020 gens 10000000000 area 3695743 maxVisits 9419 colors 50.13% 49.87%<br>
t22r021110181040 gens 10000000000 area 42226111 maxVisits 1145 colors 49.94% 50.06%<br>
t22r021111110011 gens 10000000000 area 30127782 maxVisits 1110 colors 49.54% 50.46%<br>
t22r021111110041 gens 10000000000 area 23217724 maxVisits 1504 colors 35.63% 64.37%<br>
t22r021111110081 gens 10000000000 area 37389534 maxVisits 1013 colors 47.60% 52.40%<br>
t22r021111141010 gens 10000000000 area 22414216 maxVisits 2132 colors 61.12% 38.88%<br>
t22r021111141020 gens 10000000000 area 7817317 maxVisits 4635 colors 63.20% 36.80%<br>
t22r021120121010 gens 10000000000 area 6525732 maxVisits 7823 colors 50.02% 49.98%<br>
t22r021120121040 gens 10000000000 area 12327587 maxVisits 4065 colors 49.99% 50.01%<br>
t22r021120181020 gens 10000000000 area 9380391 maxVisits 3797 colors 49.95% 50.05%<br>
t22r021121110011 gens 10000000000 area 26331814 maxVisits 1700 colors 51.56% 48.44%<br>
t22r021121181080 gens 10000000000 area 31496806 maxVisits 1246 colors 53.93% 46.07%<br>
t22r021140181040 gens 10000000000 area 27315331 maxVisits 1905 colors 49.93% 50.07%<br>
t22r021141110041 gens 10000000000 area 12056704 maxVisits 3131 colors 58.29% 41.71%<br>
t22r021141141010 gens 10000000000 area 5409505 maxVisits 6575 colors 45.73% 54.27%<br>
t22r021180121010 gens 10000000000 area 20663422 maxVisits 1940 colors 49.99% 50.01%<br>
t22r021180121020 gens 10000000000 area 3933290 maxVisits 9029 colors 50.29% 49.71%<br>
t22r021180181080 gens 10000000000 area 11390854 maxVisits 3219 colors 49.97% 50.03%<br>
t22r021181110021 gens 10000000000 area 23768249 maxVisits 1596 colors 48.76% 51.24%<br>
t22r021181110041 gens 10000000000 area 19476445 maxVisits 1941 colors 39.17% 60.83%<br>
t22r021181110081 gens 10000000000 area 19527405 maxVisits 1861 colors 50.83% 49.17%<br>
t22r021181120081 gens 10000000000 area 10023091 maxVisits 3428 colors 59.47% 40.53%<br>
t22r021181181020 gens 10000000000 area 13905088 maxVisits 2552 colors 49.99% 50.01%<br>
t22r041010120141 gens 10000000000 area 11294548 maxVisits 3475 colors 49.95% 50.05%<br>
t22r041010121010 gens 10000000000 area 14153961 maxVisits 2796 colors 49.98% 50.02%<br>
t22r041010121020 gens 10000000000 area 18680102 maxVisits 1823 colors 51.66% 48.34%<br>
t22r041010121110 gens 10000000000 area 21731434 maxVisits 1760 colors 49.94% 50.06%<br>
t22r041010121120 gens 10000000000 area 12849379 maxVisits 2924 colors 49.99% 50.01%<br>
t22r041010140121 gens 10000000000 area 8642788 maxVisits 4258 colors 49.97% 50.03%<br>
t22r041011121020 gens 10000000000 area 8487968 maxVisits 5230 colors 49.03% 50.97%<br>
t22r041020110181 gens 10000000000 area 9098324 maxVisits 3896 colors 49.94% 50.06%<br>
t22r041020120181 gens 10000000000 area 3132577 maxVisits 12088 colors 50.09% 49.91%<br>
t22r041020141010 gens 10000000000 area 4042244 maxVisits 9389 colors 42.49% 57.51%<br>
t22r041020141080 gens 10000000000 area 3898888 maxVisits 9958 colors 24.54% 75.46%<br>
t22r041021140181 gens 10000000000 area 3790803 maxVisits 9421 colors 0.09% 99.91%<br>
t22r041110121010 gens 10000000000 area 6817010 maxVisits 5612 colors 50.00% 50.00%<br>
t22r041110141010 gens 10000000000 area 33 maxVisits 1369898461 colors 51.52% 48.48%<br>
t22r041120121020 gens 10000000000 area 9814592 maxVisits 4259 colors 49.94% 50.06%<br>
t22r041120121040 gens 10000000000 area 7121298 maxVisits 5834 colors 49.89% 50.11%<br>
t22r041120181010 gens 10000000000 area 9089026 maxVisits 4194 colors 49.94% 50.06%<br>
t22r041120181020 gens 10000000000 area 8570434 maxVisits 5043 colors 49.94% 50.06%<br>
t22r041121141010 gens 10000000000 area 11264625 maxVisits 3392 colors 41.61% 58.39%<br>
t22r041121141080 gens 10000000000 area 7367199 maxVisits 4648 colors 28.52% 71.48%<br>
t22r041121181080 gens 10000000000 area 15345344 maxVisits 2358 colors 36.59% 63.41%<br>
t22r111010021110 gens 10000000000 area 13670537 maxVisits 2366 colors 50.06% 49.94%<br>
t22r111010021180 gens 10000000000 area 10673835 maxVisits 3081 colors 50.08% 49.92%<br>
t22r111010041120 gens 10000000000 area 13771072 maxVisits 2462 colors 50.00% 50.00%<br>
t22r111010120010 gens 10000000000 area 37901523 maxVisits 987 colors 49.99% 50.01%<br>
t22r111010120011 gens 10000000000 area 21641400 maxVisits 1703 colors 49.93% 50.07%<br>
t22r111010120080 gens 10000000000 area 41055182 maxVisits 887 colors 49.72% 50.28%<br>
t22r111010120081 gens 10000000000 area 43956095 maxVisits 864 colors 49.95% 50.05%<br>
t22r111010120110 gens 10000000000 area 42700206 maxVisits 825 colors 42.10% 57.90%<br>
t22r111010121080 gens 10000000000 area 36428229 maxVisits 1019 colors 49.70% 50.30%<br>
t22r111010121110 gens 10000000000 area 36013700 maxVisits 967 colors 40.51% 59.49%<br>
t22r111010141120 gens 10000000000 area 28351828 maxVisits 1299 colors 42.24% 57.76%<br>
t22r111011121010 gens 10000000000 area 39037300 maxVisits 878 colors 52.93% 47.07%<br>
t22r111020021110 gens 10000000000 area 10327986 maxVisits 3254 colors 50.08% 49.92%<br>
t22r111020021180 gens 10000000000 area 10089100 maxVisits 3406 colors 50.09% 49.91%<br>
t22r111020041120 gens 10000000000 area 10762448 maxVisits 3308 colors 49.98% 50.02%<br>
t22r111020081140 gens 10000000000 area 8016005 maxVisits 4738 colors 49.12% 50.88%<br>
t22r111020120011 gens 10000000000 area 32097987 maxVisits 1316 colors 49.97% 50.03%<br>
t22r111020120040 gens 10000000000 area 17093580 maxVisits 2324 colors 55.14% 44.86%<br>
t22r111020120081 gens 10000000000 area 32344293 maxVisits 1537 colors 49.92% 50.08%<br>
t22r111020120180 gens 10000000000 area 26049201 maxVisits 1365 colors 39.32% 60.68%<br>
t22r111020140021 gens 10000000000 area 13481810 maxVisits 3350 colors 50.00% 50.00%<br>
t22r111020140110 gens 10000000000 area 28047664 maxVisits 1442 colors 49.99% 50.01%<br>
t22r111020140120 gens 10000000000 area 23848517 maxVisits 1981 colors 53.02% 46.98%<br>
t22r111020180010 gens 10000000000 area 41024395 maxVisits 953 colors 48.23% 51.77%<br>
t22r111020180011 gens 10000000000 area 41171036 maxVisits 980 colors 49.93% 50.07%<br>
t22r111020180020 gens 10000000000 area 26637381 maxVisits 1369 colors 49.22% 50.78%<br>
t22r111020180021 gens 10000000000 area 35168872 maxVisits 1101 colors 49.92% 50.08%<br>
t22r111020180081 gens 10000000000 area 26949521 maxVisits 1556 colors 49.91% 50.09%<br>
t22r111020180110 gens 10000000000 area 34198865 maxVisits 1035 colors 40.38% 59.62%<br>
t22r111020180111 gens 10000000000 area 35403860 maxVisits 979 colors 16.92% 83.08%<br>
t22r111020180120 gens 10000000000 area 21998169 maxVisits 1699 colors 41.67% 58.33%<br>
t22r111020181110 gens 10000000000 area 32320600 maxVisits 995 colors 37.29% 62.71%<br>
t22r111020181180 gens 10000000000 area 32231735 maxVisits 1331 colors 39.43% 60.57%<br>
t22r111021021110 gens 10000000000 area 7820068 maxVisits 4250 colors 50.11% 49.89%<br>
t22r111021120040 gens 10000000000 area 11737068 maxVisits 3867 colors 49.99% 50.01%<br>
t22r111021120110 gens 10000000000 area 26130261 maxVisits 4019 colors 24.96% 75.04%<br>
t22r111021120180 gens 10000000000 area 14724498 maxVisits 15939 colors 24.95% 75.05%<br>
t22r111021121110 gens 10000000000 area 22891154 maxVisits 6105 colors 25.32% 74.68%<br>
t22r111021140011 gens 10000000000 area 10352497 maxVisits 3513 colors 41.65% 58.35%<br>
t22r111021140021 gens 10000000000 area 6137730 maxVisits 6471 colors 30.90% 69.10%<br>
t22r111021140081 gens 10000000000 area 14382794 maxVisits 3292 colors 38.53% 61.47%<br>
t22r111021140180 gens 10000000000 area 8221684 maxVisits 4581 colors 25.00% 75.00%<br>
t22r111021141080 gens 10000000000 area 24466183 maxVisits 1564 colors 56.54% 43.46%<br>
t22r111021141110 gens 10000000000 area 25144213 maxVisits 26652 colors 24.26% 75.74%<br>
t22r111021141180 gens 10000000000 area 25055475 maxVisits 2026 colors 26.15% 73.85%<br>
t22r111021180010 gens 10000000000 area 43165777 maxVisits 874 colors 49.93% 50.07%<br>
t22r111021180011 gens 10000000000 area 27318379 maxVisits 1275 colors 49.16% 50.84%<br>
t22r111021180020 gens 10000000000 area 32669728 maxVisits 1193 colors 49.92% 50.08%<br>
t22r111021181020 gens 10000000000 area 20894567 maxVisits 2027 colors 49.71% 50.29%<br>
t22r111021181110 gens 10000000000 area 26539158 maxVisits 8152 colors 25.61% 74.39%<br>
t22r111040120011 gens 10000000000 area 17632791 maxVisits 2280 colors 49.95% 50.05%<br>
t22r111040121110 gens 10000000000 area 30186260 maxVisits 1077 colors 29.94% 70.06%<br>
t22r111040121120 gens 10000000000 area 5933284 maxVisits 6559 colors 37.72% 62.28%<br>
t22r111041041120 gens 10000000000 area 16529100 maxVisits 2397 colors 54.77% 45.23%<br>
t22r111041120021 gens 10000000000 area 13528123 maxVisits 3260 colors 63.12% 36.88%<br>
t22r111041120111 gens 10000000000 area 35381919 maxVisits 936 colors 0.81% 99.19%<br>
t22r111041120180 gens 10000000000 area 30333193 maxVisits 1938 colors 32.65% 67.35%<br>
t22r111041121010 gens 10000000000 area 32386254 maxVisits 1231 colors 40.47% 59.53%<br>
t22r111041140120 gens 10000000000 area 14643276 maxVisits 3754 colors 33.28% 66.72%<br>
t22r111110120011 gens 10000000000 area 27039209 maxVisits 1308 colors 32.94% 67.06%<br>
t22r111110120021 gens 10000000000 area 33907931 maxVisits 1112 colors 11.79% 88.21%<br>
t22r111110120081 gens 10000000000 area 42316772 maxVisits 893 colors 18.17% 81.83%<br>
t22r111110121010 gens 10000000000 area 47103665 maxVisits 783 colors 2.88% 97.12%<br>
t22r111110121080 gens 10000000000 area 38306914 maxVisits 865 colors 1.82% 98.18%<br>
t22r111110141020 gens 10000000000 area 29507410 maxVisits 1108 colors 1.67% 98.33%<br>
t22r111111120011 gens 10000000000 area 15228930 maxVisits 2464 colors 40.95% 59.05%<br>
t22r111120141020 gens 10000000000 area 16586844 maxVisits 2648 colors 0.35% 99.65%<br>
t22r111120141080 gens 212788056 area 37720405 maxVisits 136057 colors 0.50 0.50<br>
t22r111121121010 gens 10000000000 area 28097232 maxVisits 1319 colors 38.29% 61.71%<br>
t22r111121141020 gens 10000000000 area 21051731 maxVisits 1858 colors 52.65% 47.35%<br>
t22r111121141080 gens 10000000000 area 14431862 maxVisits 2691 colors 43.63% 56.37%<br>
t22r111121180010 gens 10000000000 area 26929966 maxVisits 4364 colors 24.96% 75.04%<br>
t22r111121180011 gens 10000000000 area 24385176 maxVisits 1449 colors 42.14% 57.86%<br>
t22r111121181020 gens 10000000000 area 14986928 maxVisits 2454 colors 37.90% 62.10%<br>
t22r111121181080 gens 10000000000 area 17666152 maxVisits 2088 colors 42.53% 57.47%<br>
t22r120011120020 gens 10000000000 area 21883070 maxVisits 2146 colors 54.23% 45.77%<br>
t22r120011120080 gens 10000000000 area 28851286 maxVisits 1329 colors 50.70% 49.30%<br>
t22r120011120081 gens 10000000000 area 26675524 maxVisits 1543 colors 50.97% 49.03%<br>
t22r120011121040 gens 10000000000 area 11351331 maxVisits 3554 colors 49.97% 50.03%<br>
t22r120011121080 gens 10000000000 area 28604350 maxVisits 1283 colors 49.95% 50.05%<br>
t22r120011121110 gens 10000000000 area 21843385 maxVisits 1603 colors 33.55% 66.45%<br>
t22r120011121180 gens 10000000000 area 24562147 maxVisits 1504 colors 32.53% 67.47%<br>
t22r120011140011 gens 10000000000 area 17890141 maxVisits 1922 colors 41.00% 59.00%<br>
t22r120011140080 gens 10000000000 area 23528032 maxVisits 1775 colors 45.36% 54.64%<br>
t22r120011140110 gens 10000000000 area 24968465 maxVisits 1425 colors 28.80% 71.20%<br>
t22r120011140111 gens 10000000000 area 338171 maxVisits 232271 colors 0.00% 100.00%<br>
t22r120011140120 gens 10000000000 area 17773172 maxVisits 2246 colors 22.62% 77.38%<br>
t22r120011140180 gens 10000000000 area 13723791 maxVisits 2461 colors 27.99% 72.01%<br>
t22r120011141080 gens 10000000000 area 4528576 maxVisits 63057 colors 49.99% 50.01%<br>
t22r120011141110 gens 10000000000 area 33607036 maxVisits 972 colors 29.95% 70.05%<br>
t22r120011180040 gens 10000000000 area 11779429 maxVisits 3414 colors 39.09% 60.91%<br>
t22r120011180110 gens 10000000000 area 29258622 maxVisits 1215 colors 39.94% 60.06%<br>
t22r120011180111 gens 10000000000 area 20171392 maxVisits 1651 colors 1.29% 98.71%<br>
t22r120011180120 gens 10000000000 area 37570244 maxVisits 1032 colors 38.58% 61.42%<br>
t22r120011180181 gens 10000000000 area 18604891 maxVisits 2388 colors 0.17% 99.83%<br>
t22r120011181080 gens 10000000000 area 23631621 maxVisits 1695 colors 49.94% 50.06%<br>
t22r120011181110 gens 10000000000 area 32363514 maxVisits 1084 colors 32.20% 67.80%<br>
t22r120011181120 gens 10000000000 area 21630457 maxVisits 1852 colors 31.91% 68.09%<br>
t22r120021021110 gens 10000000000 area 2580535 maxVisits 22344 colors 59.39% 40.61%<br>
t22r120021021180 gens 10000000000 area 20665999 maxVisits 2066 colors 60.99% 39.01%<br>
t22r120021141040 gens 10000000000 area 7603318 maxVisits 6829 colors 50.00% 50.00%<br>
t22r120021141110 gens 10000000000 area 6987210 maxVisits 5560 colors 37.73% 62.27%<br>
t22r120021141180 gens 10000000000 area 16542293 maxVisits 2022 colors 31.24% 68.76%<br>
t22r120021180010 gens 10000000000 area 34205399 maxVisits 1522 colors 58.19% 41.81%<br>
t22r120021180110 gens 10000000000 area 34832938 maxVisits 1154 colors 47.17% 52.83%<br>
t22r120021181010 gens 10000000000 area 24029057 maxVisits 1946 colors 49.94% 50.06%<br>
t22r120021181120 gens 10000000000 area 9226300 maxVisits 4239 colors 30.52% 69.48%<br>
t22r120041120010 gens 10000000000 area 9267208 maxVisits 4925 colors 69.00% 31.00%<br>
t22r120041120020 gens 10000000000 area 19343604 maxVisits 3098 colors 57.81% 42.19%<br>
t22r120041121010 gens 10000000000 area 11691911 maxVisits 3411 colors 49.98% 50.02%<br>
t22r120041140010 gens 10000000000 area 20640482 maxVisits 2148 colors 62.50% 37.50%<br>
t22r120041180010 gens 10000000000 area 20228037 maxVisits 2337 colors 61.31% 38.69%<br>
t22r120041180021 gens 10000000000 area 29378824 maxVisits 1449 colors 62.23% 37.77%<br>
t22r120041180121 gens 10000000000 area 17867734 maxVisits 2041 colors 0.16% 99.84%<br>
t22r120081081120 gens 73594517815 area 46522472 maxVisits 5775 density 27.39% colors 49.97% 50.03%<br>
t22r120081120010 gens 10000000000 area 21880745 maxVisits 1738 colors 50.87% 49.13%<br>
t22r120081120120 gens 10000000000 area 13633770 maxVisits 2494 colors 38.33% 61.67%<br>
t22r120081121110 gens 10000000000 area 23725309 maxVisits 1494 colors 33.02% 66.98%<br>
t22r120081121180 gens 10000000000 area 27218587 maxVisits 1342 colors 31.10% 68.90%<br>
t22r120081140111 gens 10000000000 area 9767173 maxVisits 3306 colors 0.71% 99.29%<br>
t22r120081140121 gens 10000000000 area 5948728 maxVisits 6801 colors 0.06% 99.94%<br>
t22r120081141120 gens 10000000000 area 10738708 maxVisits 2996 colors 27.74% 72.26%<br>
t22r120081180040 gens 10000000000 area 18055046 maxVisits 2370 colors 55.63% 44.37%<br>
t22r120111021010 gens 10000000000 area 8583146 maxVisits 3908 colors 50.03% 49.97%<br>
t22r120111041020 gens 10000000000 area 13659672 maxVisits 2608 colors 50.00% 50.00%<br>
t22r120111081080 gens 10000000000 area 23152329 maxVisits 1780 colors 50.00% 50.00%<br>
t22r120111121010 gens 10000000000 area 22189070 maxVisits 1657 colors 33.54% 66.46%<br>
t22r120111121080 gens 10000000000 area 24919497 maxVisits 1433 colors 33.01% 66.99%<br>
t22r120111140011 gens 10000000000 area 21517351 maxVisits 1740 colors 38.30% 61.70%<br>
t22r120111141010 gens 10000000000 area 11611501 maxVisits 2990 colors 32.46% 67.54%<br>
t22r120111141080 gens 10000000000 area 16785908 maxVisits 2044 colors 30.45% 69.55%<br>
t22r120111180010 gens 10000000000 area 23716485 maxVisits 7986 colors 26.66% 73.34%<br>
t22r120111180081 gens 10000000000 area 15622606 maxVisits 2291 colors 33.08% 66.92%<br>
t22r120111181010 gens 10000000000 area 32779011 maxVisits 1102 colors 32.20% 67.80%<br>
t22r120121081020 gens 10000000000 area 10930181 maxVisits 3313 colors 50.12% 49.88%<br>
t22r120121180041 gens 10000000000 area 14377127 maxVisits 2314 colors 31.25% 68.75%<br>
t22r120141011020 gens 994004085 area 35250513 maxVisits 3468 colors 0.48 0.52<br>
t22r120141021040 gens 10000000000 area 4923646 maxVisits 7478 colors 49.94% 50.06%<br>
t22r120141041010 gens 10000000000 area 12695980 maxVisits 2956 colors 49.96% 50.04%<br>
t22r120141041020 gens 10000000000 area 5003384 maxVisits 7402 colors 50.13% 49.87%<br>
t22r120141081010 gens 10000000000 area 13249640 maxVisits 2902 colors 49.94% 50.06%<br>
t22r120141120011 gens 10000000000 area 15751955 maxVisits 2370 colors 49.94% 50.06%<br>
t22r120141120021 gens 10000000000 area 6158076 maxVisits 6217 colors 50.13% 49.87%<br>
t22r120141140011 gens 10000000000 area 15025779 maxVisits 2441 colors 44.12% 55.88%<br>
t22r120181021010 gens 10000000000 area 14841160 maxVisits 2286 colors 50.03% 49.97%<br>
t22r120181021040 gens 10000000000 area 19641237 maxVisits 2127 colors 49.97% 50.03%<br>
t22r120181081020 gens 10000000000 area 6588595 maxVisits 5465 colors 50.11% 49.89%<br>
t22r120181081080 gens 10000000000 area 10028433 maxVisits 3450 colors 49.94% 50.06%<br>
t22r120181120010 gens 10000000000 area 14353782 maxVisits 3801 colors 25.67% 74.33%<br>
t22r120181120011 gens 10000000000 area 23558585 maxVisits 1489 colors 40.24% 59.76%<br>
t22r120181120081 gens 10000000000 area 12743884 maxVisits 2815 colors 41.98% 58.02%<br>
t22r120181121010 gens 10000000000 area 25005030 maxVisits 1347 colors 32.50% 67.50%<br>
t22r120181121080 gens 10000000000 area 27829748 maxVisits 1364 colors 31.09% 68.91%<br>
t22r120181140011 gens 10000000000 area 26344558 maxVisits 1504 colors 39.01% 60.99%<br>
t22r120181140021 gens 10000000000 area 20015093 maxVisits 2016 colors 32.21% 67.79%<br>
t22r120181140081 gens 10000000000 area 3734411 maxVisits 10047 colors 0.00% 100.00%<br>
t22r120181181010 gens 10000000000 area 22113414 maxVisits 1822 colors 31.90% 68.10%<br>
t22r120181181080 gens 10000000000 area 9437032 maxVisits 4292 colors 30.52% 69.48%<br>
t22r121010021120 gens 10000000000 area 27866427 maxVisits 1720 colors 49.92% 50.08%<br>
t22r121010021180 gens 10000000000 area 18251752 maxVisits 1848 colors 50.00% 50.00%<br>
t22r121010041110 gens 10000000000 area 15620959 maxVisits 2228 colors 50.03% 49.97%<br>
t22r121010081110 gens 10000000000 area 10804725 maxVisits 3112 colors 50.09% 49.91%<br>
t22r121010081120 gens 10000000000 area 11755833 maxVisits 2919 colors 50.07% 49.93%<br>
t22r121010081180 gens 10000000000 area 22418867 maxVisits 1522 colors 49.99% 50.01%<br>
t22r121010110011 gens 10000000000 area 22109608 maxVisits 1934 colors 49.95% 50.05%<br>
t22r121010110021 gens 10000000000 area 32210815 maxVisits 1411 colors 49.97% 50.03%<br>
t22r121010110080 gens 10000000000 area 26367953 maxVisits 1309 colors 49.16% 50.84%<br>
t22r121010110081 gens 10000000000 area 41412306 maxVisits 934 colors 49.93% 50.07%<br>
t22r121010110111 gens 10000000000 area 27281125 maxVisits 1279 colors 32.95% 67.05%<br>
t22r121010140010 gens 10000000000 area 26109574 maxVisits 1414 colors 59.16% 40.84%<br>
t22r121010140021 gens 10000000000 area 8040024 maxVisits 4644 colors 49.94% 50.06%<br>
t22r121010140080 gens 10000000000 area 19531775 maxVisits 2040 colors 59.60% 40.40%<br>
t22r121010140110 gens 10000000000 area 42722360 maxVisits 894 colors 50.45% 49.55%<br>
t22r121010140120 gens 10000000000 area 17435190 maxVisits 2152 colors 49.72% 50.28%<br>
t22r121010140121 gens 10000000000 area 18529529 maxVisits 1919 colors 49.98% 50.02%<br>
t22r121010141110 gens 10000000000 area 32763942 maxVisits 1137 colors 42.07% 57.93%<br>
t22r121011110011 gens 10000000000 area 38300986 maxVisits 964 colors 49.99% 50.01%<br>
t22r121011110080 gens 10000000000 area 44174083 maxVisits 825 colors 49.94% 50.06%<br>
t22r121011110081 gens 10000000000 area 40765818 maxVisits 936 colors 48.23% 51.77%<br>
t22r121011110180 gens 10000000000 area 27206306 maxVisits 4435 colors 24.96% 75.04%<br>
t22r121011120080 gens 10000000000 area 28646854 maxVisits 1250 colors 49.96% 50.04%<br>
t22r121011120110 gens 10000000000 area 15476517 maxVisits 5060 colors 24.98% 75.02%<br>
t22r121011120180 gens 10000000000 area 12876513 maxVisits 9413 colors 25.00% 75.00%<br>
t22r121011140020 gens 10000000000 area 9886225 maxVisits 5026 colors 50.00% 50.00%<br>
t22r121011140110 gens 10000000000 area 12981831 maxVisits 4810 colors 16.65% 83.35%<br>
t22r121011140180 gens 10000000000 area 12044146 maxVisits 4162 colors 25.00% 75.00%<br>
t22r121011141010 gens 10000000000 area 32958157 maxVisits 1111 colors 57.27% 42.73%<br>
t22r121011141110 gens 10000000000 area 29097166 maxVisits 1219 colors 25.66% 74.34%<br>
t22r121011141180 gens 10000000000 area 20826362 maxVisits 8942 colors 25.72% 74.28%<br>
t22r121020021110 gens 10000000000 area 12459359 maxVisits 4078 colors 50.02% 49.98%<br>
t22r121020021140 gens 10000000000 area 6960054 maxVisits 5607 colors 49.92% 50.08%<br>
t22r121020021180 gens 10000000000 area 8767500 maxVisits 4342 colors 50.00% 50.00%<br>
t22r121020081110 gens 10000000000 area 10327268 maxVisits 3247 colors 50.07% 49.93%<br>
t22r121020081120 gens 10000000000 area 8479681 maxVisits 4206 colors 50.13% 49.87%<br>
t22r121020081180 gens 10000000000 area 6814053 maxVisits 5207 colors 50.09% 49.91%<br>
t22r121020110040 gens 10000000000 area 14272145 maxVisits 3535 colors 63.11% 36.89%<br>
t22r121020110081 gens 10000000000 area 26604649 maxVisits 1637 colors 49.93% 50.07%<br>
t22r121020110111 gens 10000000000 area 33437673 maxVisits 1104 colors 11.77% 88.23%<br>
t22r121020141010 gens 10000000000 area 17135634 maxVisits 2186 colors 57.17% 42.83%<br>
t22r121021140021 gens 10000000000 area 12572790 maxVisits 3484 colors 42.13% 57.87%<br>
t22r121040021110 gens 10000000000 area 11526382 maxVisits 3757 colors 50.01% 49.99%<br>
t22r121040021140 gens 10000000000 area 2767407 maxVisits 12469 colors 50.10% 49.90%<br>
t22r121040021180 gens 10000000000 area 5185101 maxVisits 6249 colors 50.09% 49.91%<br>
t22r121040081180 gens 10000000000 area 8110366 maxVisits 4210 colors 50.04% 49.96%<br>
t22r121041110020 gens 10000000000 area 12340171 maxVisits 3855 colors 49.97% 50.03%<br>
t22r121041110021 gens 10000000000 area 16644943 maxVisits 2472 colors 55.14% 44.86%<br>
t22r121041140081 gens 10000000000 area 2776666 maxVisits 12319 colors 32.75% 67.25%<br>
t22r121080021140 gens 10000000000 area 4205424 maxVisits 9339 colors 50.01% 49.99%<br>
t22r121080021180 gens 10000000000 area 6649156 maxVisits 5162 colors 50.01% 49.99%<br>
t22r121080081180 gens 10000000000 area 21665555 maxVisits 1707 colors 49.94% 50.06%<br>
t22r121080110011 gens 10000000000 area 43055203 maxVisits 951 colors 49.93% 50.07%<br>
t22r121080110021 gens 10000000000 area 31362567 maxVisits 1405 colors 49.92% 50.08%<br>
t22r121080110080 gens 10000000000 area 25904739 maxVisits 1400 colors 49.03% 50.97%<br>
t22r121080110081 gens 10000000000 area 35280664 maxVisits 1061 colors 49.93% 50.07%<br>
t22r121080110111 gens 10000000000 area 42478741 maxVisits 866 colors 18.17% 81.83%<br>
t22r121080110180 gens 10000000000 area 23974873 maxVisits 1481 colors 43.79% 56.21%<br>
t22r121080120110 gens 10000000000 area 34182997 maxVisits 1165 colors 42.23% 57.77%<br>
t22r121080140010 gens 10000000000 area 25387679 maxVisits 1550 colors 52.00% 48.00%<br>
t22r121080140021 gens 10000000000 area 18938595 maxVisits 2398 colors 49.94% 50.06%<br>
t22r121080140120 gens 10000000000 area 28437767 maxVisits 2112 colors 57.34% 42.66%<br>
t22r121081110011 gens 10000000000 area 39853830 maxVisits 891 colors 49.72% 50.28%<br>
t22r121081110080 gens 10000000000 area 32293737 maxVisits 1220 colors 49.92% 50.08%<br>
t22r121081110081 gens 10000000000 area 26932665 maxVisits 1374 colors 49.20% 50.80%<br>
t22r121081120010 gens 10000000000 area 28746989 maxVisits 1347 colors 49.96% 50.04%<br>
t22r121081120011 gens 10000000000 area 199 maxVisits 1199679932 colors 37.69% 62.31%<br>
t22r121110021110 gens 10000000000 area 15135898 maxVisits 2337 colors 0.08% 99.92%<br>
t22r121110110040 gens 10000000000 area 35400691 maxVisits 941 colors 0.80% 99.20%<br>
t22r121110110081 gens 10000000000 area 35247008 maxVisits 1039 colors 16.94% 83.06%<br>
t22r121110110140 gens 10000000000 area 46788013 maxVisits 765 colors 0.00% 100.00%<br>
t22r121110140020 gens 10000000000 area 25393858 maxVisits 1298 colors 1.58% 98.42%<br>
t22r121110140111 gens 10000000000 area 28611904 maxVisits 1347 colors 0.00% 100.00%<br>
t22r121111110011 gens 10000000000 area 42514624 maxVisits 865 colors 42.10% 57.90%<br>
t22r121111110020 gens 10000000000 area 26985583 maxVisits 2747 colors 24.97% 75.03%<br>
t22r121111110081 gens 10000000000 area 35479187 maxVisits 1055 colors 40.36% 59.64%<br>
t22r121111120010 gens 10000000000 area 15375628 maxVisits 5793 colors 24.98% 75.02%<br>
t22r121111120081 gens 13294807061 area 42790455 maxVisits 1258 density 24.70% colors 42.23% 57.77%<br>
t22r121111140011 gens 10000000000 area 12168073 maxVisits 2906 colors 41.24% 58.76%<br>
t22r121111140081 gens 10000000000 area 5107469 maxVisits 8736 colors 22.22% 77.78%<br>
t22r121111141010 gens 10000000000 area 15900155 maxVisits 2347 colors 40.36% 59.64%<br>
t22r121120141010 gens 10000000000 area 6837655 maxVisits 4743 colors 0.17% 99.83%<br>
t22r121121140011 gens 10000000000 area 15473837 maxVisits 2274 colors 39.77% 60.23%<br>
t22r121121140021 gens 10000000000 area 29165505 maxVisits 2271 colors 39.49% 60.51%<br>
t22r121141141010 gens 10000000000 area 7421549 maxVisits 4426 colors 1.50% 98.50%<br>
t22r121181110020 gens 10000000000 area 14945070 maxVisits 4551 colors 24.97% 75.03%<br>
t22r121181110040 gens 10000000000 area 28932090 maxVisits 2084 colors 32.52% 67.48%<br>
t22r121181110081 gens 10000000000 area 21569724 maxVisits 1883 colors 41.66% 58.34%<br>
t22r121181120010 gens 10000000000 area 13068907 maxVisits 7231 colors 24.99% 75.01%<br>
t22r121181120011 gens 10000000000 area 203 maxVisits 1015053509 colors 58.62% 41.38%<br>
t22r121181140010 gens 10000000000 area 15911417 maxVisits 3437 colors 33.28% 66.72%<br>
t22r121181141010 gens 10000000000 area 18553855 maxVisits 1959 colors 45.74% 54.26%<br>
t22r140011121080 gens 10000000000 area 4527348 maxVisits 104566 colors 49.97% 50.03%<br>
t22r140011121110 gens 10000000000 area 11671067 maxVisits 2905 colors 32.45% 67.55%<br>
t22r140011121180 gens 10000000000 area 16795015 maxVisits 2152 colors 30.47% 69.53%<br>
t22r140021121010 gens 10000000000 area 13687842 maxVisits 4072 colors 49.88% 50.12%<br>
t22r140021140111 gens 10000000000 area 11804875 maxVisits 2745 colors 0.80% 99.20%<br>
t22r140111121010 gens 10000000000 area 33578136 maxVisits 988 colors 29.95% 70.05%<br>
t22r140111121020 gens 10000000000 area 6905658 maxVisits 5913 colors 37.72% 62.28%<br>
t22r140111140021 gens 10000000000 area 9197979 maxVisits 4899 colors 38.96% 61.04%<br>
t22r140121140010 gens 10000000000 area 10526815 maxVisits 4713 colors 33.27% 66.73%<br>
t22r140121140011 gens 10000000000 area 18561126 maxVisits 1921 colors 39.30% 60.70%<br>
t22r140121140081 gens 10000000000 area 16061351 maxVisits 2687 colors 35.33% 64.67%<br>
t22r140121181080 gens 10000000000 area 16366699 maxVisits 2031 colors 31.25% 68.75%<br>
t22r141010021120 gens 10000000000 area 16176870 maxVisits 2196 colors 49.97% 50.03%<br>
t22r141010021140 gens 10000000000 area 14028601 maxVisits 2893 colors 49.93% 50.07%<br>
t22r141010110020 gens 10000000000 area 10058198 maxVisits 3377 colors 41.66% 58.34%<br>
t22r141010120110 gens 10000000000 area 11911154 maxVisits 2965 colors 41.26% 58.74%<br>
t22r141011120011 gens 23447376704 area 46523418 maxVisits 1964 density 25.66% colors 59.19% 40.81%<br>
t22r141011120081 gens 23821006483 area 44461504 maxVisits 2063 density 25.97% colors 52.01% 47.99%<br>
t22r141011120180 gens 34853479222 area 37283457 maxVisits 5010 density 18.66% colors 33.31% 66.69%<br>
t22r141011140120 gens 10000000000 area 10514825 maxVisits 4959 colors 33.29% 66.71%<br>
t22r141020021110 gens 10000000000 area 7589831 maxVisits 4648 colors 50.04% 49.96%<br>
t22r141020021180 gens 10000000000 area 22319004 maxVisits 1908 colors 49.98% 50.02%<br>
t22r141020081120 gens 10000000000 area 11826234 maxVisits 5666 colors 49.83% 50.17%<br>
t22r141020110020 gens 10000000000 area 6384710 maxVisits 6777 colors 30.91% 69.09%<br>
t22r141020110021 gens 10000000000 area 14430729 maxVisits 3386 colors 49.97% 50.03%<br>
t22r141020110080 gens 10000000000 area 14342161 maxVisits 3271 colors 38.55% 61.45%<br>
t22r141020120011 gens 10000000000 area 8041536 maxVisits 5111 colors 49.95% 50.05%<br>
t22r141020120081 gens 10000000000 area 19326808 maxVisits 2263 colors 49.95% 50.05%<br>
t22r141020120110 gens 10000000000 area 13022788 maxVisits 4841 colors 40.79% 59.21%<br>
t22r141020180110 gens 10000000000 area 4838925 maxVisits 8814 colors 22.21% 77.79%<br>
t22r141021120010 gens 10000000000 area 10204030 maxVisits 4167 colors 50.03% 49.97%<br>
t22r141021120111 gens 10000000000 area 25218254 maxVisits 1344 colors 1.58% 98.42%<br>
t22r141021180011 gens 10000000000 area 19584137 maxVisits 2150 colors 59.59% 40.41%<br>
t22r141040120011 gens 72483942329 area 44149819 maxVisits 6107 density 26.88% colors 50.00% 50.00%<br>
t22r141110120111 gens 10000000000 area 27600368 maxVisits 1439 colors 0.00% 100.00%<br>
t22r141111110021 gens 10000000000 area 27827005 maxVisits 1401 colors 50.01% 49.99%<br>
t22r141111120010 gens 10000000000 area 13166132 maxVisits 4268 colors 16.65% 83.35%<br>
t22r141121120081 gens 10000000000 area 25787169 maxVisits 2358 colors 57.33% 42.67%<br>