# Emergency Withdrawal

As the code of Summit DeFi is completely custom built, it does not follow the generic pattern of a masterchef contract however; we have ensured that we included the important functionality of an Emergency Withdrawal to allow users to always be able to retrieve their funds.

To access the Emergency Withdrawal functionality, you will need to head to the cartographer contract which can be found:

**Fantom**: [**here**](https://ftmscan.com/address/0x71210e72d065c19406913cd706e964a9f21856d4#writeContract) or by going to [https://ftmscan.com/](https://ftmscan.com) and then searching for the cartographer contract `0x71210E72D065C19406913cD706e964A9f21856D4` and then navigating to the "Write Contract" tab:\


**Polygon**: [**here** ](https://polygonscan.com/address/0x8733820E0097e9289c30764018B9eE5d47E8332B#code)or by going to [https://polygonscan.com/](https://polygonscan.com) and then searching for the cartographer contract `0x8733820E0097e9289c30764018B9eE5d47E8332B` and then navigating to the "Write Contract" tab:\


![](<../.gitbook/assets/image (28).png>)

You will then need to connect your wallet by clicking on "Connect to Web3":

![As usual, your wallet will ask you to confirm the connection so read the prompts that pop-up and confirm the connection](<../.gitbook/assets/image (30).png>)



Once your wallet has connected, scroll down to function 8. emergencyWithdrawal

![](<../.gitbook/assets/image (14).png>)

For `_token` you will need to input the contract address of the token you wish to withdraw.

* You can see the list of contract addresses for the tokens:
  * Fantom -  [**here**](fantom-token-contracts.md).
  * Polygon - [**here**](polygon-token-contracts.md).
* Find the asset your asset and the corresponding contract for it then input that in this field.

For `_elevation` this is what Elevation your funds were in. If you were in multiple Elevations, then just repeat this process for each Elevation.&#x20;

* From the below table, look for the Elevation and then use the corresponding `Elevation uint8` number.

| Elevation | Elevation uint8 |
| --------- | --------------- |
| Oasis     | 0               |
| Plains    | 1               |
| Mesa      | 2               |
| Summit    | 3               |

Once you have filled in the fields, it should look similar to the below example:

![](<../.gitbook/assets/image (22).png>)

Next you will need to click on "Write".&#x20;

After clicking on "Write" your wallet will ask you to confirm a blockchain transaction and then once confirmed by the blockchain, your requested token will be withdrawn and returned to your wallet.

Repeat this process for your other assets.



