
### Note
    - Etherchannel (for more than one Port and up to 8 port channel depand on switch)
    - This configuration apply on both sides switches


## Step-1
```
interface port-channel 1
    switchport mode trunk
    switchport trunk allowed vlan 1-2,4,6,10,13-14,16,20-21,22
    switchport trunk native vlan 1
    end
```
## Step-2
```
interface range GigabitEthernet5/0/46-47
    channel-group 1 mode on
    end
```

## Step-3
```
interface range GigabitEthernet5/0/46-47
    switchport mode trunk
    switchport trunk allowed vlan 1-2,4,6,10,13-14,16,20-21,22
    switchport trunk native vlan 1
    exit
```        
