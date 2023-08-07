title: Tunnel Vision Debugging
date: 2014

One of my pitfalls when it comes to programming is Tunnel Vision Debugging. Let's assume that I wanted to perform a task, I was then able to accomplish that task and then moved on. Fast forward a couple of weeks, I try to accomplish that same task that worked and now it fails.

I look at my code and there is nothing wrong, I have not changed anything and yet it fails. Then I formulate a possible cause of the problem as X, I start going down this rabbit hole to prove to myself that X is indeed the cause of the problem and nothing else.

Well I just recently delt with this pitfall while working on [Finkit](https://github.com/Fuchida/Archive/tree/master/finkit). I was adding a new test to the test suite but when it came to run the tests, all the previous tests failed.

For whatever reason, my test setup could not send mail. The connection times out when trying to connect to the SMTP server. I immediately pronounced that that problem was my SMTP server in conjuction with SSL/TLS requirements and so I went down the following path.

* Rewrite the python mail sending code (still times out)

* Remove the mail sending module and write the mail sending code using strictly python (still fails)

* Plan to SSH to the server and remove TLS requirements.

2hrs later, I had to leave home and decided I would do step three later. Now while at a different location, I used the service called [Nitrous](http://web.archive.org/web/20150408062119/https://www.nitrous.io/) ( Nitrous.io has since shut down ) to run the tests one more time before diving into Postfix. My tests passed without a flinch, turns out <sup>TM</sup> , I had forgotten that my residential ISP blocks port 25.

I should have started at the base of the issue, "why is the connection timing out" and troubleshooted the network vs the application then move on to the application.
