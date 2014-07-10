notmuch-bash
============

simple consolewrapper for notmuch to save yourself from typing all the time

<img src="http://media.giphy.com/media/d8v55gXkiNj3y/giphy.gif"/>

⬈ This is the effect of notmuch

### Usage

    press arrow up to cycle suggestions
    type 'exit' to quit
    
    notmuchbash> showtags
    
    possible tags:
      work      tech       mailinglist
      family    friends    dropbox
      social    personal   music
     
    notmuchbash> search tag:inbox
    
    thread:0000000000006978      July 01 [1/1] StumbleUpon; "The 10 Most Ridiculously Awesome Geeky Kitchens"
    thread:0000000000006979      July 01 [1/1] Foobar; "The 12 Most Ridiculously Awesome Geeky Kittnes"
    --MORE--
    
    notmuchbash> thread:0000000000006978
    
    StumbleUpon <no-reply@stumblemail.com> (July 01) (inbox unread)
    Subject: "The 10 Most Ridiculously Awesome Geeky Computer Pranks," and more recommendations just for you
    From: StumbleUpon <no-reply@stumblemail.com>
    To: foo@bar.com
    Date: Tue, 01 Jul 2014 09:35:46 +0000
    StumbleUpon
    -------------------------
    
    Hi foo,
    =====================================
    We think you want to see this.
    =====================================
    --MORE--

### Why

I wanted something simple without needing the ruby-bindings.
At the same time I wanted some 'notmuch'-presets (which can be defined in the script) which I could launch with the arrow-up keys.

### Remote usage

My email gets fetched and tagged on my homeserver.
However, on my local laptops I use a simple remote bashwrapper for the `notmuch` binary, you can do this like so:

    wget "https://gist.githubusercontent.com/coderofsalvation/c60a1cde22d972828d4c/raw/a04ac4e82468d024e5865444292417e4555fd3f3/remotewrapper.bash" -O notmuch
    sed -i 's/cmd=asciidoc/cmd=notmuch/g' notmuch
    (open the notmuch file in an editor and change the host/ip e.g.)
    cp notmuch ~/bin/notmuch
    
Now your local 'notmuch-bash' can run 'notmuch' on your laptop (while 'notmuch' actually executes at the homeserver).
 
### Known Issues

* 'show' does not display message which are multipart-messages
