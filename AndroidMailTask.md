# SevenRE Coding Test (Native Android)

[SevenRE](http://www.seven-re.com/home) is a German technology start-up building great products. With welcoming arms for the young eager minds of tomorrow we have prepared a competitive screening test. Your overall objective would be to ***prepare a Mailbox*** which fetches mail list from server and shows them in simple list and some additional functionalities.

### Tasks

- Login screen (Use Google API for login, like login via Google Plus, we will use Gmail for testing)
- Fetch inbox mails of that Gmail account (Fetch recent 50 mails)
- Store emails in local database with fields like id, sender name, sender mail id, subject, content, etc (it would be nice to see if Realm is used as db, #notRequired) (fun would be if you can download attachments, *#notRequired*)
- User can delete mail (delete mails from local db) (it would be nice if it is removed from gmail account also, *#notRequired*)
- User can reply to mail (make view for sending mail) (make dummy method that sends mail to any RESTApi, response will be error) (you can send email using Google API's, *#notMandatory*)
- List item which is showing email is Swipeable like Gmail, user can delete & reply from there)
- Sync mails every 15 minutes

To send mail, use HTTP post method to add all contents or simply make Rest call as shown below
```sh
http://www.random-server.com/send?subject=MySubject&sender=temp@var.com&timeStamp=11112342234&body=MyTrialMail
```

### Tips
- Use Github to find some useful code or library
- Popular library for use are Dagger2, Retrofit, OkHttp, EventBus, Realm, LeakCanary, Butterknife; use some of this to prove competency
- Swipe list item can look like [this] 
- We love to have beautiful UI. Find some nice UI view or animations online to impress us
- Using some test case can be nice
- Explore MVP pattern and try to follow it, many examples are available online
 
We don't expect you to finish all tasks but will give more preference to person who is able to complete maximum tasks. We ask more but we pay more! 

> Contact us in case of some  confusion in question or need some help in coding. 
> We are happy to guide you for solving this.
> jobs@seven-re.com

##### Disclaimer

Your work for the tasks listed here is neither related to what we are doing nor will it be used for any internal/external development; its just a test!

##### Good luck :)

[this]: <http://i.stack.imgur.com/aB55l.png>
