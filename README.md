# AoMR : Better AI Scaling

A custom mod for the videogame Age of Mythology Retold who make the AI scale better as the number of players in the game increase

[link to the uploaded mod](https://www.ageofempires.com/mods/details/434805/)  

![Splash screen with some catchy resume of what the mod does and a laser-eyes Cronos](/assets/splash.png)


# What does this mod do ?

Short answer, the AI (standard, moderate, hard) scale far better in games with more players since it is not capped for party of only two players.

#

Vanilla :

- AI won't get more than 1TC for Standard, 2TC for Moderate, 3TC for Hard, whatever the available colony near by
-   AI won't seek far colony even if there are available near by (42% of the size of the map for 2 players, 19% for 12 players...) except in lategame for titan and harder.
-   AI won't train more than fixed villagers pop, 16/30/50/75 for first difficulties, whatever are their population
-   AI won't train more military pop than 1.5x count of villagers pop

#

Modded :

*"Stockpile X" : then the lesser of resources of food/wood/gold have at least X stock*

Based on the number of players on the map (assert there are 1TC & 2 colonies spawn by player) :
-   Allow the AI to colonize more TC for Standard/Moderate/Hard difficulties. Titan, Extreme and Legendary have no limit.
    - Now capped at third of all colonies in Standard, half colonies in Moderate, half all TC in Hard
-   Allow the AI to colonize farther. In lategame (ie age 4 & stockpile of 1k) it increases again for hard and moderate difficulties
-   Allow the AI to train more villagers (game cap is 100)
    - Standard keep the same ratio, Moderate and Hard got few more by arbitraty choice
-   Allow the AI to train more military pop since its based on economy pop (villagers + fish boats + caravan). Titan and harder difficulties have no military pop cap.  
    -   Fixed issue for Standard, Moderate and Hard in lategame (stockpile > 2k). It used max villagers pop instead of economic pop, but economic pop can be higher since it includes caravans and fishing boat, resulting in potential bit less military pop than before the stockpile
    -   Added a "very late game" scaling military pop :
        -   compute the ratio stockpile / arbitraty value (10k for Hard for example)
        -   compute the ratio colonised TC / max colonisable TC
        -   apply the worst ratio and a linear degretion by number of players
        -   increase the default 1.5 vanilla ratio of economy pop to determine the military pop cap (ex: Hard goes from 1.5 ratio with 2 players to 4.0 ratio with 12 players. In 12 players, it means the hard cap goes from 75 military pop to 300)

#

- The AI now may rush a bit (a lot) on free TC it sees. 
- Also it may build wonders later since it is spending more for military.

Feel free to ping me on the #myth-modding channel in the official AoE discord if you have questions.

Enjoy.

#

<table>
  <tr>
    <td width="50%"><img src="/assets/TC vanilla chart.JPG"></td>
    <td width="50%"><img src="/assets/TC modded chart.JPG"></td>
  </tr>
  <tr>
    <td width="50%" style="text-align:center;">Vanilla max colony by nb players and difficulties</td>
    <td width="50%" style="text-align:center;">Modded max colony by nb players and difficulties</td>
  </tr>
</table>

#

<table>
  <tr>
    <td width="50%"><img src="/assets/TC ranged vanilla chart.JPG"></td>
    <td width="50%"><img src="/assets/TC ranged modded chart.JPG"></td>
  </tr>
  <tr>
    <td width="50%" style="text-align:center;">Vanilla distance max between colony and main town by nb players</td>
    <td width="50%" style="text-align:center;">Modded distance max between colony and main town by nb players</td>
  </tr>
</table>

#

<table>
  <tr>
    <td width="50%"><img src="/assets/Villagers vanilla pop chart.JPG"></td>
    <td width="50%"><img src="/assets/Villagers modded pop chart.JPG"></td>
  </tr>
  <tr>
    <td width="50%" style="text-align:center;">Vanilla max villagers by nb player and difficulties (cap 100)</td>
    <td width="50%" style="text-align:center;">Modded max villagers by nb player & difficulties(cap 100)</td>
  </tr>
</table>

#

#

<table>
  <tr>
    <td width="50%"><img src="/assets/Military vanilla pop chart.JPG"></td>
    <td width="50%"><img src="/assets/Military modded pop chart.JPG"></td>
  </tr>
  <tr>
    <td width="50%" style="text-align:center;">Vanilla max military unit by nb players and difficulty<br>
(no caravan no fishing boat for the example)</td>
    <td width="50%" style="text-align:center;">Modded max military unit by nb players and difficulty<br>
if stockpile > 2000 & built TC < (nb players / 3)<br>
(no caravan no fishing boat for the example)</td>
  </tr>
</table>

#

<table>
  <tr>
    <td><img src="/assets/Military modded hard difficulty incr chart.JPG"></td>
  </tr>
  <tr>
    <td style="text-align:center;">Modded max military unit by nb players for HARD AI<br>
if stockpile > 2k & built TC >= (nb players / 3).<br>
Scaling from smallest ratio between<br>
resources (stockpile/10k ) & TC(current/max buildable)<br>
(no caravan no fishing boat for the example)</td>
  </tr>
</table>








