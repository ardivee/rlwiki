---
layout: default
title: Boost Pads
permalink: /pages/udk/boost-pads
toc:
   - name: Requirements
     link: requirements
   - name: Setup
     link: setup
   - name: Info
     link: info
   - name: Credits
     link: credits
---
{% assign last_modified_at = "1 Mar, 2020"%}
# Boost Pads

---

#### Requirements

---

###### - [Dummy Classes](/pages/assets/dummy-classes "Dummy Classes")
###### - [Dummy Assets ( PARK_P )](/pages/assets/dummy-assets "Dummy Assets")
###### - [Setup Classes](/pages/udk/setup-classes "Setup Classes") 

#### Setup

---

###### - Open your Actor Classes window 
###### - Search for ```VehiclePickup_Boost_TA``` and drag it into your scene
###### - Press F4 to open the Properties window or use Right Click > Properties
###### - Choose the type of boost you want to use ( In this example we are using the Pill Boost )
###### - Set the Boost Amount to ```9999```
###### - Browse to your ```Park_P``` package, locate ```Boost_Pickup_Pill_Local``` and press the Green Arrow to use it
###### - Set the Boost Type to ```BoostType_Pill```
###### - Set the Respawn Delay to ```10```
###### - Browse to your ```Park_P``` package and drag ```BoostPill_FXActor``` into your scene, place it at the same location as your ```VehiclePickup_Boost_TA```
###### - Open the Properties window of the FXActor, check ```No Delete``` under Actor ( This makes sure it's also visible by other clients! )
   ![FXActor Example](/assets/img/fxactor_example.png "FXActor Example")
###### - Type the name of the FXActor you just placed in the FXActor input of the ```VehiclePickUp_Boost``` properties ( You can see the name by selecting it )
###### - And that's it! You now have a fully working Boost Pad
###### <span style="color:red;">***NOTE: Keep in mind that if you save the map under a different name the reference to the FXActor will be gone, however it will still work if you rename your map outside of UDK***</span>

##### Example

![Boost Pad Example](/assets/img/boostpill_example.png "Boost Pad Example")

#### Info

---

{:.responsive-table}
| Boost | Boost Amount | Local Pickup Sound | Boost Type | Respawn Delay | FXActor |
| ----------- | ----------- | ----------- | ----------- | ----------- |
| Pad | 0.12 | Boost_Pickup_Pad_Local | BoostType_Pad | 4 | BoostPad_FXActor |
| Pill | 9999 | Boost_Pickup_Pill_Local | BoostType_Pill | 10 | BoostPill_FXActor |

#### Credits

---

###### - Eliot ( UE Explorer )
###### - Martinn ( UPK Decryptor )

**Last Updated: {{ last_modified_at }}**