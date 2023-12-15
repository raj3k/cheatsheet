# Listening Ports and Applications using lsof Command

To check open TCP and UDP ports on a Linux system, you can use the `lsof` command. This tool provides information about files and processes, including network-related details. Follow the steps below to list open ports and their associated applications.

## Command to Check Open Ports

```bash
sudo lsof -i -P -n | grep LISTEN
```

##Explanation of Flags:

* i: Look for listing ports.
* P: Inhibits the conversion of port numbers to port names for network files. This can improve the speed of the lsof command and is useful when port name lookup is not working properly.
* n: Do not use DNS name for host and service lookups.
* | grep LISTEN: Pipe the output to grep to filter and display only the ports in the LISTEN state.