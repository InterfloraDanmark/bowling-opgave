# Programmerings opgave

## Bowling-point algoritme

Implement an algoritme which continuesly calculates the sum of a game, which follows the [10-pin rule](https://en.wikipedia.org/wiki/Ten-pin_bowling#Traditional_scoring) for point calculation in bowling.

In order to resolve the task you have to use the two REST API endpoints which are temporarily provided:

<table>
  <tbody>
    <tr>
      <th align="center" width="5%">Method</th>
      <th align="center" width="30%">URL</th>
      <th align="center" width="25%">Parametre</th>
      <th align="center" width="40%">Beskrivelse</th>
    </tr>
    <tr>
      <td valign="top">GET</td>
      <td valign="top">http://13.74.31.101/api/points</td>
      <td valign="top"></td>
      <td>
        <ul>
          <li>Returns a JSON-list with a random length and combination of valid bowling points, as well as a token, which must be used for the POST endpoint.</li>
          <li>Strike is represented by [10,0]</li>
          <li>Spare is represented by f.ex. [7,3] or [0,10] or [5,5]</li>
      </ul>
      </td>
    </tr>
    <tr>
      <td valign="top">POST</td>
      <td valign="top">http://13.74.31.101/api/points</td>
      <td valign="top"><i>token</i>: (string)
        <br />
        YHGgktp8DkUpMsmjmJfsOTJ3PUAxJOBk
        <br /><br />
        <i>points</i>: (array)
        <br />
        [10,16,23,33,48]
        <br />
        <br />
        Eksempel på json body:
        <br />
        {"token": "124jgjfj3FkenI", "points": [5, 10, 25, 30]}
      </td>
      <td valign="top"><i>token</i>: Received in GET<br /><i>points</i>: Your calculated sums<br /><br />Returned HTTP status code ”200 OK” if <i>token</i> is correct og JSON { "success": true } if the <i>sums</i> are correct.<br /><br />The sums are a list of the accumulated results.<br /><br />F.ex. the <i>points</i> [[3,7],[10,0],[8,2],[8,1],[10,0],[3,4],[7,0],[5,5],[3,2],[2,5]] yield the <i>sums</i> [20,40,58,67,84,91,98,111,116,123], where 123 is the total sum after, in this case, 10 rounds. <br /><br /> Tip: If the points end on a <i>spare / strike</i> before a normal games length (10 rounds) it won't trigger a bonus. F.ex the points [[2, 0], [8, 2]] will give the  <i>sums</i> [2, 12]</td>
    </tr>
  </tbody>
</table>

## Forudsætninger
* Programming language: Javascript (VueJS 3) 
* Løsningsdesign/arkitektur: Valgfrit 
* UI: Valgfrit om nødvendig
* Source code can the belivered in the following way: 
  * .zip fil 
  * URL to the git repo 
* The source code should contain code which varifies that your point-algorithm Kildekode functions.
* 10-pin bowling with traditional 10-pin rules. 
  * https://en.wikipedia.org/wiki/Ten-pin_bowling#Traditional_scoring  
  * https://en.wikipedia.org/wiki/Bowling
  * Simulator: http://www.bowlinggenius.com/ 
