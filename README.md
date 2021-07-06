# windscribe-python-wrapper
Quick & dirty wrapper for the Windscribe CLI for Python



# Prerequisites
This needs to be run on Linux as there is only a Windscribe CLI for Linux (as far as I'm aware).

Visit https://windscribe.com/guides/linux for Windscribe CLI installation instructions for your favorite distro. This was made using an Ubuntu VM.


# Usage
There are two necessary files:
1. servers.txt - text file which holds the list of server names you'd like to choose from if connecting to a random server.
2. windscribe.py - file which contains the Windscribe class. Remember this is quick and dirty!

#### Example:
##### Log in and connect to random server
```
from windscribe import Windscribe

vpn = Windscribe(<serverlist file>, <user>, <password>)
vpn.connect(rand=True)

```
##### Log in and connect to specific server
```
from windscribe import Windscribe

vpn = Windscribe(<serverlist file>, <user>, <password>)
vpn.connect(server="Cheese")

```

#### Methods

###### Login
```vpn.login()```
  This is automatically called when instantiating the class. No need to call it again.
  
###### Locations
```vpn.locations()```
  Print the available connection locations to the shell. This includes location, short name, city, label, and Pro-only indicator.
  
###### Connect
```vpn.connect(server, rand)```
  This connects to a server if specified, a random server if rand = True, or the best available if both arguments are not passed.
  Server should be the Label of the server (for example, server in Las Vegas is labelled "Casino". Get the labels for all available servers by using the locations() method.
  
###### Disconnect
```vpn.disconnect()```
  Disconnect from the current server.
  
###### Logout
```vpn.logout()```
  Log out of the current logged in user.
