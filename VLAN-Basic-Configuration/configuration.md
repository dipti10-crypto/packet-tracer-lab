## Example Scenario
![VLAN Basic Configuration](./vlan%20topology.png)
| PC  | Port  | VLAN    | IP            |
| --- | ----- | ------- | ------------- |
| PC1 | Fa0/1 | VLAN 10 | 192.168.10.10 |
| PC2 | Fa0/2 | VLAN 10 | 192.168.10.11 |
| PC3 | Fa0/3 | VLAN 20 | 192.168.20.10 |
| PC4 | Fa0/4 | VLAN 20 | 192.168.20.11 |

## Step 1 — Switch Configuration

- Switch> enable
- Switch# configure terminal

## Step 2 — VLAN Create
- Switch(config)# vlan 10
- Switch(config-vlan)# name Student
- Switch(config-vlan)# exit

- Switch(config)# vlan 20
- Switch(config-vlan)# name Teacher
- Switch(config-vlan)# exit

## Step 3 — Switchport Access

For VLAN 10

- Switch(config)# interface range fa0/1-2
- Switch(config-if-range)# switchport mode access
- Switch(config-if-range)# switchport access vlan 10
- Switch(config-if-range)# exit


For VLAN 20

- Switch(config)# interface range fa0/3-4
- Switch(config-if-range)# switchport mode access
- Switch(config-if-range)# switchport access vlan 20
- Switch(config-if-range)# exit

## Step 4 — Configuration check
- Switch# show vlan brief

## Step 5 - Ping Test

- ping 192.168.10.10
- ping 192.168.20.11

## Output
![Ping Test](./ping%20test.png)
