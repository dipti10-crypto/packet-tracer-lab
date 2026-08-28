# 2-Switch-VLAN-Trunk-Configuration

## Step 1: Create VLAN on Switch 1
- Switch> enable
- Switch# configure terminal

- Switch(config)# vlan 10
- Switch(config-vlan)# name STUDENT
- Switch(config-vlan)# exit

- Switch(config)# vlan 20
- Switch(config-vlan)# name TEACHER
- Switch(config-vlan)# exit

# Step 2: Create VLAN on Switch 2
- Switch> enable
- Switch# configure terminal

- Switch(config)# vlan 10
- Switch(config-vlan)# name STUDENT
- Switch(config-vlan)# exit

- Switch(config)# vlan 20
- Switch(config-vlan)# name TEACHER
- Switch(config-vlan)# exit
