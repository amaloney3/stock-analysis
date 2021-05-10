# Stocking Up: Coding for Analysis (and Re-Analysis) of Market Performance in 2017 & 2018
The purpose of this project was not only to summarize the recent performance of several stocks, but 
make the original analysis lighter and more nimble, so it could be adapted to heftier data in the future. The
exercise reinforces the importance of intuitive data design, clean code and strong logic for programmers
and clients alike.

## Results
The stocks selected for analysis had an incredibly polarized performance during the years in question. All but one made significant gains in 2017, with DQ finishing the year nearly 200% above where it started. The average return in 2017 was more than 67%, and only one stock (TERP) actually lost ground (see image below)

![image](https://user-images.githubusercontent.com/1015285/117599945-88f0af00-b110-11eb-8f86-b04110395136.png)

The story turned almost completely on its head in 2018. All but two stocks (ENPH & RUN) lost ground, with 2017's high-achiever (DQ) suffering the most precipitous decline, nearly 63% from where it began (of course, after the gains in 2017, such a reversion might be a bit more expected). The gains made by ENPH & RUN tempered the average return -- it was "only" -8.5% -- though, among stocks that ended up "in the red," the average loss in 2018 was 26.8%.

![image](https://user-images.githubusercontent.com/1015285/117600348-5abf9f00-b111-11eb-8bb6-f64adde47b0a.png)

## Summary

But the code is just as crucial as the output. As programmers, we want to produce results, but also give ourselves the ability to adjust and improve over time.
In that vein, it helps to fine-tune the structure underlying the analysis, to make it as logical and amenable to updates as possible. Such tweaks not only help us 
reproduce results over time, but lighten the load on our machines, and make it easier to handle more and more data in the future.

The original code for this project contained, among other things, a nested For/Next loop (see below) that iterated over the dataset multiple times (once for each stock). Although conceptually sound, such a structure would certainly drag down processing power if we tried to analyze a larger set of stocks.


![image](https://user-images.githubusercontent.com/1015285/117604413-edb10700-b11a-11eb-8a10-2e1809b6cc17.png)


This was certainly one of the main reasons, if not, the main reason that the run-time on the 2017 analysis using the original version of the code was roughly 0.703 seconds, while the most recent run-time for the 2018 analysis using the original code was .609 seconds.


The Refactored version, on the other hand, iterates through the entire dataset only one time, and divvies up key calculations (such as returning the stock tickers, volume and annual returns output) into their own, smaller loops.

![image](https://user-images.githubusercontent.com/1015285/117604326-bf332c00-b11a-11eb-8153-b5d07c6993ff.png)


 The refactored version also made frequent use of the array structure, with the "tickerIndex" array functioning as something of a skeleton key for volume, starting and ending prices. As you can see in the Resources folder, the run-times for the refactored analyeses were much lighter, coming in at .09375 (2017) and .08579 (2018) seconds.
 
 



