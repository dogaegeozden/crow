# CROW
![CrowLogo](https://cdn.pixabay.com/photo/2017/01/31/17/00/animal-2025562_960_720.png)

Crow is a command line reconnaissance tool to collect information about a target system and document findings in text files with dates and times. It's very flexible and, that's why you can combine the options to execute better reconnaissance attacks. For example you can use -torc, -nmap and -grabB to grab service banners over a tor connection, write the output of nmap scan in to a text file. List of the tools that are automated by tor are listed down below:
 
1) iputils-ping 
2) nmap 
3) netcat
4) tor
5) proxychains 
6) curl
7) gobuster
8) proxychains

## INSTALLATION
1) ```git clone https://github.com/tamrinotte/crow.git```
2) ```cd crow```
3) ```sudo cp crow /usr/bin/```
4) ```sudo chown $USER:$USER /usr/bin/crow && sudo chmod u+x /usr/bin/crow```


## OPTIONS

	    -ping, --ping                                                                                                                   
                Send a ping to a target device. The default options are set to -c 5                                                     
                                                                                                                                        
	    -r, --rush                                                                                                                      
                Use this option to scan all TCP and UDP ports quickly.

	    -nmap, --nmap
                Use this option to scan the services available on a target device. Use double quotes to use the options that are available to nmap's itself. The default options are set to -sV -sC -sT -A -p-

        -netc, --netc
                Do anything that you would do with netcat's it self. 

        -torc, --torc
                Execute operations over a tor connection.

        -grabb, --grabb
                Grab service banners using the last nmap scan.
	    
	    -gobtr, --gobtr
                Enumerate the target to reveal hidden subdomains or folders.


## EXAMPLES
	sudo crow -ping 10.10.10.10
	sudo crow -ping "-c 3" 10.10.10.10
	sudo crow -nmap 10.10.10.10
	sudo crow -nmap "-sT -sV -sC -A -p-" 10.10.10.10
	sudo crow -netc "1-65535" 10.10.10.10
	sudo crow -netc "-zv" "1-65535" 10.10.10.10
	sudo crow -torc -ping  "-c 3" -nmap "-sT -sV -sC -A" -netc "-zv" "1-65535" -grabB 10.10.10.10
	sudo crow -r 10.10.10.10
	sudo crow -gobtr "dir" -u -w "/usr/share/dirb/wordlists/common.txt" 10.10.10.10
