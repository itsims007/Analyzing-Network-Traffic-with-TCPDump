# Analyzing-Network-Traffic-with-TCPDump
    - we are going to focus on:

      1. Using tcpdump to capture TCP packets

      2. Analyze captured packets


-This hands on project is divided into following tasks:

    -Task 1: Overview and warm up
    
        We start by opening a terminal and enter
        sudo tcpdump.
        without limits dumps will continue if this occurs hit control-c

        for additonal options for can enter man tcpdump for menu press q to exit

        to set limit we enter sudo tcpdump -c 10 
        it captures the first 10 packets then stops.
        an additional option is entering -# after the packet limit, it adds the packet number

        entering sudo tcpdump -D shows all the network interfaces on your workstation.

        entering sudo tcpdump -i ens5 -c 10
        will only capture that one designated network and 10 packets 

        We start by entering sudo tcpdump -#tttt host skyroute66.com -c 10
        because the site has no traffic packets were not captured

        we can also filter with port numbers. by entering sudo tcpdump -#tttt -c 10 port 443 
        additionally we can enter entering 
        sudo tcpdump -#tttt -c 10 port 443 and host skyroute66.com to filter by host and port. 
        
    -Task 2: Create shell script and explore more options
    
        We will create shell script for our website traffic monitor.
        Next we open visual studio, select desktop , then we create a file and name it watchdog.sh (sh because we are creating a shell).
        We are now going to write, start constructing our command that we want to use. We want to do TCP dump and we want it to have a line number
        and then head to the on that and also the human readable time and we're going to limit it to host Sky work 66.com
        because we want to capture both incoming and outgoing traffic from that website.
        
        Okay, So now we're going to right click on this and open an integrated terminal. 
        That is if you do an LS and see that script is right there but now it's not executed well, so we're just going to make it execute by doing 
        a change mode plus execute for watch dot dot sh.
         
        So we're going to execute it by doing dot slash watch dot sh. We're gonna test it out. Alright, so see it's waiting for package.
        we're going to reload and you can see that it is capturing packets, it's captured 10 packets and then
        stop.This nice format with a line number with a human readable date with the source I P address, destination I. P.
        Address which is the Skyroute66 it's showing you the packet contents. 

        This is what it captured from the network traffic
   
    
    -Task 3: Create and read dump files
        Now we figure out what command we actually want to use to capture our packet. Now this is nice to look at it on the screen but what
        if we want to save them for later? We're also going to use another utility to look at these actual content to see
        what they are in a better format. 
        
        For that we need to dump our capture packets in a dump file. Now we do that with and um command line option lower
        case w capture that means we're just going to capture. 

         We're going to execute this again. So we're only capturing 10 packets and you can see
        it's listening. It created the capture p cap right there waiting for us to generate some traffic.
        
        So let's go  do a refresh. It captured 10 packets as we specified. And then it stopped.


        What we can do is use to do T. C. P dump to use the lower case r option to read their trial so we can say capture dot P
        cap and they will read that trial just as if it is just capturing it from the network. Now you can also pass the same formatting options to it.

        There's another utility you can look at this dump file in a much more user friendly way.
            - This utility is called WireShark.
                We're going to go to computer.It's on the desktop it's going to be Under rhyme.
                rhyme desktop and captured the  pcap. That's our capture file that we just created.

        Now you can see that it is create presenting it in a much more useful way for you to explore the content.
        there are the 10 packets right there with the line number with the time source I. P. Address to destination I. P.
        Address also the protocol length and what it really means. It is useful is it actually breaks down this package
        Now obviously you can have more than 10 packets.
        Um and at the next task we're going to talk about how to
        create dump files with a time limit, Let's say I just want 10
        minutes of traffic and also a size limits.
        Obviously these these files can grow extremely large and you
        will not be able to open it easily.

        
    -Task 4: Create sequence of dump files with size and time limits





