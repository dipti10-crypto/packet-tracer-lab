# 2-Switch-VLAN-Trunk-Configuration

## Step 1: Create VLAN on Switch 0
- Switch> enable
- Switch# configure terminal

- Switch(config)# vlan 10
- Switch(config-vlan)# name STUDENT
- Switch(config-vlan)# exit

- Switch(config)# vlan 20
- Switch(config-vlan)# name TEACHER
- Switch(config-vlan)# exit

# Step 2: Create VLAN on Switch 1
- Switch> enable
- Switch# configure terminal

- Switch(config)# vlan 10
- Switch(config-vlan)# name STUDENT
- Switch(config-vlan)# exit

- Switch(config)# vlan 20
- Switch(config-vlan)# name TEACHER
- Switch(config-vlan)# exit

# Step 3: SW0- PC ports configure
PC0 → VLAN 10
- Switch(config)# interface fa0/1
- Switch(config-if)# switchport mode access
- Switch(config-if)# switchport access vlan 10
- Switch(config-if)# exit

PC1 → VLAN 20
- Switch(config)# interface fa0/2
- Switch(config-if)# switchport mode access
- Switch(config-if)# switchport access vlan 20
- Switch(config-if)# exit

# Step 5: Configure Trunk
sw0 →
- Switch(config)# interface fa0/24
- Switch(config-if)# switchport mode trunk
- Switch(config-if)# exit
  
sw1 →
- Switch(config)# interface fa0/24
- Switch(config-if)# switchport mode trunk
- Switch(config-if)# exit


# Step 6: PC IP Configuration
PC0
- IP Address: 192.168.10.10
- Subnet Mask: 255.255.255.0

PC2
- IP Address: 192.168.10.20
- Subnet Mask: 255.255.255.0

PC1
- IP Address: 192.168.20.10
- Subnet Mask: 255.255.255.0

PC3
- IP Address: 192.168.20.20
- Subnet Mask: 255.255.255.0

# Step 7: Ping Test
Test 1: PC0 → PC3
- ping 192.168.10.20

Test 2: PC1 → PC2
- ping 192.168.20.20

Test 3: PC0 → PC4
- ping 192.168.20.20
