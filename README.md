
<h2>Program Modifications</h2>
<p>For this application I took what we learned in “Android Basics with Compose” and I modified the script we wrote by adding additional code. First I knew that we needed to be able to input the amount of guests so I included another EditNumberField in my TipCalculatorLayout() method. This edit field allowed for input of the number of guests so we could take that input and divide the total.  The number of guests would only be used in the calculation if the switch was changed to indicate a split bill. Because we didn't need to round up the tip with this version I modified the round up to be a split tip boolean switch. Additionally we needed to know how much the total was with tip as well as the total if split between a number so I added two additional methods one to calculate total per guest and another to calculate just the tip amount. To calculate the total per guest I took the  amount input and added the calculated tip then had that divided into the number of guest input. 
</p>

<h2>Code Modifications</h2>

        EditNumberField(
            label = R.string.number_of_guest,
            leadingIcon = R.drawable.money,
            keyboardOptions = KeyboardOptions.Default.copy(
                keyboardType = KeyboardType.Number,
                imeAction = ImeAction.Done
            ),
            value = partyNumber,
            onValueChange = {partyNumber = it},
            modifier = Modifier.padding(bottom = 32.dp).fillMaxWidth()
        )

        //Split bill indicator
        SplitTheTipRow(
            splitTip = splitTip,
            onSplitChanged = {splitTip = it},
            modifier = Modifier.padding(bottom = 32.dp)
        )
        //Total amount
        Text(
            text = stringResource(R.string.total,total),
            style = MaterialTheme.typography.displaySmall
        )
        //Tip amount
        Text(
            text = stringResource(R.string.tip,tip),
            style = MaterialTheme.typography.displaySmall
        )

        Spacer(modifier = Modifier.height(150.dp))
        //Amount per quest
        Text(
            text = stringResource(R.string.amount_per_guest,totalPerGuest),
            style = MaterialTheme.typography.displaySmall
        )

        
        
<h2>Screenshots of IDE, code, and the program running on AVD</h2>
      
<img src=https://github.com/AmberKRodriguez/Tip-Calculator-App/blob/main/Screenshot%202025-09-01%20at%201.56.57%E2%80%AFPM.png/>

<img src=https://github.com/AmberKRodriguez/Tip-Calculator-App/blob/main/Screenshot%202025-09-01%20at%2012.51.23%E2%80%AFPM.png/> 
