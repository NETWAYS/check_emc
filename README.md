check_emc
=========

checks the EMC CLARIION SAN devices.

`check_emc_clariion.pl` receives the data from the emc devices via Navicli or Naviseccli if user and password are provided.

### Usage

#### check_emc.pl


    check_emc.pl -h

    check_emc.pl --man

    check_emc.pl -H <host> -t <checktype>

Options:

    -h          Display this helpmessage.
    -H          The hostname or ipaddress of the emc centera device.
    -t          The check type to execute:
                the following checks are currently available
                    node_status - checks the status of the centera nodes
                    capacity - check the drive usage
    -u          administrative user used for the cli connection
    -p          administrative password used for the cli connection
    --node      the cluster node to check (ony used with check type node_status)
    --script    cli script with commands executed on the centera command line
            


#### check_emc_clariion.pl 

    check_emc_clariion.pl -h | --help

    check_emc_clariion.pl -H <host> -t <checktype>

    check_emc_clariion.pl -H <host> -u <user> -p <password> -t <checktype>

Options:

    -h      Display this helpmessage.
    -H      The hostname or ipaddress of the emc storage processor device.
    -u      The user used to connect to the emc storage processor device
            with Naviseccli. You must use this option with -password !
    -p      The password of the user used to connect to the emc storage
            processor device with Naviseccli.
    -t      The check type to execute:

                sp - check the status of the storage processors
                disk - check the status of the physical disks attached in the DAE`s
                cache - check the status of the read and write cache
                faults - Report the different faults on the array
                portstate - check the status of the FC ports in the SP`s
                hbastate - check the connection state of the specified node

            type options:
   
                sp
                --sp    The storageprocessor to check e.g. A or B
            
                portstate
                --sp    The storageprocessor to check e.g. A or B
                --port  The port ID to check e.g. 0 or 1 or 0, 1, 2 or 3 for Clariion CX3-80 - if not specified, all ports are checked
            
                hbastate
                --node  The node name to check out of navisphere
                --paths The number of available FC Paths from the client to the SAN Infrastructure e.g. 2

