# KClendUtilities
To get started, make a new sheet in your google drive. Then go to "Tools" > Script editor
Replace myFunction with the code in lentOrders

Go to your kucoin account on desktop and under API management create a new api with TRADE permission and any IP
copy the credentials it gives you to a note and put them into the code

READ THROUGH THE CODE. every relevant line is annotated to help you understand what it is doing
I am a stranger and you are about to run my script with access to both the spreadsheet file on your google drive and ability to make external calls
Its always good practice to take a look through code because althoug the api you made cannot withdraw at all, it can still make trades on your behalf
The code should only have the urls to the timestamp and margin/lend/trade/unsettled (your unsettled lending orders)

Once you are satisfied that you are not about to run malware, change the function its going to run from httpGet to customButton from the down arrow and hit Run
It will then ask you for authorization to be able to read/write to the spreadsheet 
Click review permissions and log in. Google will tell you that the app if unverified really want to know you know what youre doing.
ALthough I wrote the script, you are the one running it with your account so you should know what its doing
The script you are editing is linked to the spreadsheet and is run under your own account, I dont have access or ability to change, run, or control the script
It only makes get requests rather than posts, which means information comes in rather than infomration going out
Every request made using your signature and passphrase are encrypted so this information is not even sent in plaintext for the request
After you trust the script, click the grey underlined "advanced" and "go to project" then allow what it asks
then click run again

if you get an exception in the logger on line 7 , you have to go to the dropdown arrow next to run and select to run the customButton script

You will now have a new menu on the spreadsheet next to "tools" "addons" "help" called Script Menu from which you can call the function
now you may get an error if you havent renamed teh sheet from testgrounds on line 60, either rename the sheet you are on from sheet1 to testgrounds or go to line 60 in the code and change testgrounds to Sheet1 or you could delete .getSheetByName("testgrounds") if youll only ever use one sheet
Now you can call the function  and it will display size, accrued interest, filled, rate, term, and maturity date  =F2/86400+date(1970,1,1) in an adjacent cell turns it to a date

now you can do some cell math https://ibb.co/PgjKKLf
