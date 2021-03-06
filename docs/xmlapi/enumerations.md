# Response Data Constants
Constant values are used in certain response data columns to represent enumerated types.  These constants are defined in the tables below.

## Order State

<table border="1">
    <tbody>
        <tr>
            <th>Value</th>
            <th>Meaning</th>
        </tr>
        <tr>
            <td align="right">0</td>
            <td>Open or Active</td>
        </tr>
        <tr>
            <td align="right">1</td>
            <td>Closed</td>
        </tr>
        <tr>
            <td align="right">2</td>
            <td>Expired or Fulfilled</td>
        </tr>
        <tr>
            <td align="right">3</td>
            <td>Cancelled</td>
        </tr>
        <tr>
            <td align="right">4</td>
            <td>Pending</td>
        </tr>
        <tr>
            <td align="right">5</td>
            <td>Character Deleted</td>
        </tr>
    </tbody>
</table>

### Applies to
* [Char - MarketOrders](char_marketorders.md)
* [Corp - MarketOrders](corp_marketorders.md)

## Order Range

<table border="1">
    <tbody>
        <tr>
            <th>Value</th>
            <th>Meaning</th>
        </tr>
        <tr>
            <td align="right">32767</td>
            <td>Region (buy order).  Default value for all sell orders.</td>
        </tr>
        <tr>
            <td align="right">-1</td>
            <td>Station (buy order)</td>
        </tr>
        <tr>
            <td align="right">0</td>
            <td>Solar System (buy order)</td>
        </tr>
        <tr>
            <td align="right">5, 10, 20, or 40</td>
            <td>Jumps from station where order was placed (buy order)</td>
        </tr>
    </tbody>
</table>

### Applies to
* [Char - MarketOrders](char_marketorders.md)
* [Corp - MarketOrders](corp_marketorders.md)

## Raw Quantity

<table border="1">
    <tbody>
        <tr>
            <th>Value</th>
            <th>Meaning</th>
        </tr>
        <tr>
            <td align="right">-1</td>
            <td>Every item __except__ blueprints: Singleton _(=non-stackable)_</td>
        </tr>
        <tr>
            <td align="right">-1</td>
            <td>Blueprint _Original_</td>
        </tr>
        <tr>
            <td align="right">-2</td>
            <td>Blueprint _Copy_</td>
        </tr>
    </tbody>
</table>

### Applies to
* [Char - AssetList](char_assetlist.md)
* [Corp - AssetList](corp_assetlist.md)
* [Char - ContractItems](char_contractitems.md)
* [Corp - ContractItems](corp_contractitems.md)

## Inventory Flags

These are the flags used by the inventory system. This data is available in the EVE SDE invFlags table.
They define hangars or slots where an item may reside. It should be noted that ingame items may have multiple flags, but the API will only show a single flag.


### Applies to
* [Char - AssetList](char_assetlist.md)
* [Char - Blueprints](char_blueprints.md)
* [Corp - AssetList](corp_assetlist.md)
* [Char - Blueprints](corp_blueprints.md)

## Reference Type

<table border="1">
    <tbody>
        <tr>
            <th>refTypeID</th>
            <th>Name</th>
            <th>argName1</th>
            <th>argID1</th>
            <th>reason</th>
            <th>comment</th>
        </tr>
        <tr>
            <td align="right">1</td>
            <td>Player Trading</td>
            <td>Station name</td>
            <td>
                StationID
                <sup>
                <a href="../../sde/mssql_staStations/">[1]</a>
                </sup>
            </td>
            <td></td>
            <td>Location of direct player trade.  See <a href="../../sde/mssql_staStations/">Stations Table</a>.</td>
        </tr>
        <tr>
            <td align="right">2</td>
            <td>Market Transaction</td>
            <td>
                transactionID
                <sup>
                <a href="../char_wallettransactions/">[1]</a>
                <a href="../corp_wallettransactions/">[2]</a>
                </sup>
            </td>
            <td>0</td>
            <td></td>
            <td>See <a href="../char_wallettransactions/">Char - WalletTransactions</a> or <a href="../corp_wallettransactions/">Corp - WalletTransactions</a>.</td>
        </tr>
        <tr>
            <td align="right">10</td>
            <td>Player Donation</td>
            <td></td>
            <td>0</td>
            <td>"DESC:" + player entered text</td>
            <td>Player donation with text entered by the donator appearing in the "reason" field.</td>
        </tr>
        <tr>
            <td align="right">17</td>
            <td>Bounty Prize (historical)</td>
            <td>NPC Name</td>
            <td>NPC ID</td>
            <td></td>
            <td>Relaced with refTypeID 85 in Trinity release.</td>
        </tr>
        <tr>
            <td align="right">19</td>
            <td>Insurance</td>
            <td>
                Destroyed Ship Type ID
                <sup>
                <a href="../../sde/yaml_typeIDs/">[1]</a>
                </sup>
            </td>
            <td>0</td>
            <td></td>
            <td>See <a href="../../sde/yaml_typeIDs/">Inventory Types file</a>.</td>
        </tr>
        <tr>
            <td align="right">35</td>
            <td>CONCORD Spam Prevention Act (CSPA)</td>
            <td>Player name</td>
            <td>Player character ID</td>
            <td></td>
            <td>Player name refers to the player you're trying to contact.</td>
        </tr>
        <tr>
            <td align="right">37</td>
            <td>Corp Account Withdrawal</td>
            <td>Player name that performed withdrawal</td>
            <td>Player character ID that performed withdrawal</td>
            <td>Player entered text</td>
            <td>Corp account withdrawal with text entered by the withdrawing player appearing in the "reason" field.</td>
        </tr>
        <tr>
            <td align="right">46</td>
            <td>Broker Fee</td>
            <td>EVE System</td>
            <td>1</td>
            <td></td>
            <td>Tags the market order commission fee for a market transaction.  The ownerName2 field indicates to whom the fee was paid.</td>
        </tr>
        <tr>
            <td align="right">56</td>
            <td>Manufacturing</td>
            <td>
                Job ID
                <sup>
                <a href="../char_industryjobs/">[1]</a>
                <a href="../corp_industryjobs/">[2]</a>
                </sup>
            </td>
            <td>0</td>
            <td></td>
            <td>Fee for industry manufacturing job.  See <a href="../char_industryjobs/">Char - IndustryJobs</a> or <a href="../corp_industryjobs/">Corp - IndustryJobs</a>.</td>
        </tr>
        <tr>
            <td align="right">63, 64, 71, 72, 73, 74, 79, 80, 81, 82</td>
            <td>Various contract types</td>
            <td>Contract ID?</td>
            <td>0</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td align="right">85</td>
            <td>Bounty Prizes</td>
            <td></td>
            <td>
                solarSystemID
                <sup>
                <a href="../sqlite_mapSolarSystems/" title="mapSolarSystems.solarSystemID">[1]</a>
                </sup>
            </td>
            <td>NPC ID:quantity killed[,id:qty[,...]]</td>
            <td>Arg1ID provides the solar system ID where the bounty was acquired.  For each type of NPC killed, its typeID is followed by a colon and the quantity killed. These pairs are seperated by commas, and if there are too many (more than about 60 characters' worth) the list is ended with a literal ",..." to indicate that more have been left off the list.</td>
        </tr>
        <tr>
            <td align="right">97</td>
            <td>Customs Office Export Duty</td>
            <td>Planet name</td>
            <td>
                Planet ID
                <sup>
                <a href="../sqlite_mapDenormalize/" title="mapDenormalize.itemID">[1]</a>
                </sup>
            </td>
            <td>"Export Duty for " + planet name</td>
            <td>Customs office export duty for the named planet.  The duty was paid to the entity with ownerID2.</td>
        </tr>
    </tbody>
</table>

### Applies to
* [Char - WalletJournal](char_walletjournal.md)
* [Corp - WalletJournal](corp_walletjournal.md)

## Notification Type

<table border="1">
    <tbody>
        <tr>
            <th>TypeID</th>
            <th>Description</th>
	    <th>Structured Data</th>
        </tr>
        <tr>
            <td align="right">1</td>
            <td>Legacy</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">2</td>
            <td>Character deleted</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">3</td>
            <td>Give medal to character</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">4</td>
            <td>Alliance maintenance bill</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">5</td>
            <td>Alliance war declared</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">6</td>
            <td>Alliance war surrender</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">7</td>
            <td>Alliance war retracted</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">8</td>
            <td>Alliance war invalidated by Concord</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">9</td>
            <td>Bill issued to a character</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">10</td>
            <td>Bill issued to corporation or alliance</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">11</td>
            <td>Bill not paid because there's not enough ISK available</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">12</td>
            <td>Bill, issued by a character, paid</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">13</td>
            <td>Bill, issued by a corporation or alliance, paid</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">14</td>
            <td>Bounty claimed</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">15</td>
            <td>Clone activated</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">16</td>
            <td>New corp member application</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">17</td>
            <td>Corp application rejected</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">18</td>
            <td>Corp application accepted</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">19</td>
            <td>Corp tax rate changed</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">20</td>
            <td>Corp news report, typically for shareholders</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">21</td>
            <td>Player leaves corp</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">22</td>
            <td>Corp news, new CEO</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">23</td>
            <td>Corp dividend/liquidation, sent to shareholders</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">24</td>
            <td>Corp dividend payout, sent to shareholders</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">25</td>
            <td>Corp vote created</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">26</td>
            <td>Corp CEO votes revoked during voting</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">27</td>
            <td>Corp declares war</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">28</td>
            <td>Corp war has started</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">29</td>
            <td>Corp surrenders war</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">30</td>
            <td>Corp retracts war</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">31</td>
            <td>Corp war invalidated by Concord</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">32</td>
            <td>Container password retrieval</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">33</td>
            <td>Contraband or low standings cause an attack or items being confiscated</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">34</td>
            <td>First ship insurance</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">35</td>
            <td>Ship destroyed, insurance payed</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">36</td>
            <td>Insurance contract invalidated/runs out</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">37</td>
            <td>Sovereignty claim fails (alliance)</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">38</td>
            <td>Sovereignty claim fails (corporation)</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">39</td>
            <td>Sovereignty bill late (alliance)</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">40</td>
            <td>Sovereignty bill late (corporation)</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">41</td>
            <td>Sovereignty claim lost (alliance)</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">42</td>
            <td>Sovereignty claim lost (corporation)</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">43</td>
            <td>Sovereignty claim acquired (alliance)</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">44</td>
            <td>Sovereignty claim acquired (corporation)</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">45</td>
            <td>Alliance anchoring alert</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">46</td>
            <td>Alliance structure turns vulnerable</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">47</td>
            <td>Alliance structure turns invulnerable</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">48</td>
            <td>Sovereignty disruptor anchored</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">49</td>
            <td>Structure won/lost</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">50</td>
            <td>Corp office lease expiration notice</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">51</td>
            <td>Clone contract revoked by station manager</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">52</td>
            <td>Corp member clones moved between stations</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">53</td>
            <td>Clone contract revoked by station manager</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">54</td>
            <td>Insurance contract expired</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">55</td>
            <td>Insurance contract issued</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">56</td>
            <td>Jump clone destroyed</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">57</td>
            <td>Jump clone destroyed</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">58</td>
            <td>Corporation joining factional warfare</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">59</td>
            <td>Corporation leaving factional warfare</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">60</td>
            <td>Corporation kicked from factional warfare on startup because of too low standing to the faction</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">61</td>
            <td>Character kicked from factional warfare on startup because of too low standing to the faction</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">62</td>
            <td>Corporation in factional warfare warned on startup because of too low standing to the faction</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">63</td>
            <td>Character in factional warfare warned on startup because of too low standing to the faction</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">64</td>
            <td>Character loses factional warfare rank</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">65</td>
            <td>Character gains factional warfare rank</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">66</td>
            <td>Agent has moved</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">67</td>
            <td>Mass transaction reversal message</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">68</td>
            <td>Reimbursement message</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">69</td>
            <td>Agent locates a character</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">70</td>
            <td>Research mission becomes available from an agent</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">71</td>
            <td>Agent mission offer expires</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">72</td>
            <td>Agent mission times out</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">73</td>
            <td>Agent offers a storyline mission</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">74</td>
            <td>Tutorial message sent on character creation</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">75</td>
            <td>Tower alert</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">76</td>
            <td>Tower resource alert</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">77</td>
            <td>Station aggression message</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">78</td>
            <td>Station state change message</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">79</td>
            <td>Station conquered message</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">80</td>
            <td>Station aggression message</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">81</td>
            <td>Corporation requests joining factional warfare</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">82</td>
            <td>Corporation requests leaving factional warfare</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">83</td>
            <td>Corporation withdrawing a request to join factional warfare</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">84</td>
            <td>Corporation withdrawing a request to leave factional warfare</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">85</td>
            <td>Corporation liquidation</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">86</td>
            <td>Territorial Claim Unit under attack</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">87</td>
            <td>Sovereignty Blockade Unit under attack</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">88</td>
            <td>Infrastructure Hub under attack</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">89</td>
            <td>Contact add notification</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">90</td>
            <td>Contact edit notification</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">91</td>
            <td>Incursion Completed</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">92</td>
            <td>Corp Kicked</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">93</td>
            <td>Customs office has been attacked</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">94</td>
            <td>Customs office has entered reinforced</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">95</td>
            <td>Customs office has been transferred</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">96</td>
            <td>FW Alliance Warning</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">97</td>
            <td>FW Alliance Kick</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">98</td>
            <td>AllWarCorpJoined Msg</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">99</td>
            <td>Ally Joined Defender</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">100</td>
            <td>Ally Has Joined a War Aggressor</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">101</td>
            <td>Ally Joined War Ally</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">102</td>
            <td>New war system: entity is offering assistance in a war.</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">103</td>
            <td>War Surrender Offer</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">104</td>
            <td>War Surrender Declined</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">105</td>
            <td>FacWar LP Payout Kill</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">106</td>
            <td>FacWar LP Payout Event</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">107</td>
            <td>FacWar LP Disqualified Eventd</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">108</td>
            <td>FacWar LP Disqualified Kill</td>
            <td>TBD</td>
        </tr>
    </tbody>
</table>

### Applies to
* [Char - Notifications](char_notifications.md)
