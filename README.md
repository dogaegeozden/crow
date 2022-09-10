# CROW
![CrowLogo](https://cdn.pixabay.com/photo/2017/01/31/17/00/animal-2025562_960_720.png)

Crow is a command line reconnaissance tool that you can use to collect information about the target system and document them in xml files with dates and times. It's very flexible that's why you can do everything you to wish do with the tools that are automated by crow. Crow is allowing you to control the fallowing softwares. It's allowing you to combine the options to execute better reconnaissance attacks. For example you could use -torc, -nmap and -grabB to scan the services available on the target device from a tor connection, write the output of nmap scan in to a xml file and to grab all the service banners using that information just with 1 line of code over a tor connection again.
 
1) iputils-ping 
2) nmap 
3) netcat
4) tor
5) proxychains 
6) curl

## INSTALLATION
1) ```git clone https://github.com/tamrinotte/crow.git```
2) ```cd crow```
3) ```sudo cp crow /usr/bin/```
4) ```sudo chown $USER:$USER /usr/bin/crow && sudo chmod u+x /usr/bin/crow```


## OPTIONS

    -ping, --ping 
		Use this option to ping the target device. The default options are set to -c 10

    -nmap, --nmap
		Use this option to scan the services available on the target device. Use double quotes to enter the options that are available on nmap's it self. The default options are set to -sT -sV -sC -A -p-

	-netc, --netc
		You can use this option to basically do anything that you would do with netcat's it self. You can type crow -netc "-z -v" "1-65535" site.com to scan the ports that are available on the target server. You can also use it to create small web server, a file transfer tool or to listen TCP connections and to listen UDP activities. The default options are set to "-zv".

	-torc, --torc
		The tor option is to forward your request over a tor connection.
	
	-grabB, --grabB
		With -grabB option you can read the latest nmap scan, identify all the open ports, loop through all them and grab all the banners.

## EXAMPLES
	sudo crow -ping 10.10.10.10
	sudo crow -ping "-c 3" 10.10.10.10
	sudo crow -nmap 10.10.10.10
	sudo crow -nmap "-sT -sV -sC -A -p-" 10.10.10.10
	sudo crow -netc "1-65535" 10.10.10.10
	sudo crow -netc "-zv" "1-65535" 10.10.10.10
	sudo crow -torc -ping  "-c 3" -nmap "-sT -sV -sC -A" -netc "-zv" "1-65535" -grabB 10.10.10.10
