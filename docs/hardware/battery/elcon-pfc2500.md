# Elcon PFC2500

The Elcon PFC-2500 is used to charge the internal battery pack of our electric vehicles. 

![](/assets/hardware/battery/elcon-pfc2500-charger-1.png)



## LED Charge State 
| LED State | Description |
| --------- | ----------- |
| Solid Red | Full Power < 85% |
| Flashing Red | CV 85% < SOC |
| Solid Yellow | Equalize stage CC |
| Solid Green | Finished or BMS Enable Circuit Open |
| Alt Green / Red | No Battery Connected |

!!! warning

    The charger will not output power (solid green led) unless the BMS circuit is closed.
