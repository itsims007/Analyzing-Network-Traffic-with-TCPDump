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
            -We will create shell script for our website traffic monitor.

    -Task 3: Create and read dump files

    -Task 4: Create sequence of dump files with size and time limits

    -Task 5: Advanced expressions for more filtering options





