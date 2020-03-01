---
layout: default
title: Setup Classes
permalink: /pages/udk/setup-classes
toc:
   - name: Setup
     link: setup
   - name: StaticMeshActor
     link: staticmeshactor
   - name: PrimitiveComponent
     link: primitivecomponent
   - name: Actor
     link: actor
   - name: Credits
     link: credits
---
{% assign last_modified_at = "1 Mar, 2020"%}
# Setup Classes

---

#### Setup

###### - All these files can be found in ```UDK/Development/Src/Engine/Classes```

---

##### StaticMeshActor

---


###### - We start by modifying ```StaticMeshActor.uc``` ( This is for collision )
###### - Search for this part below

> Begin Object Class=StaticMeshComponent Name=StaticMeshComponent0   
>    &nbsp;&nbsp;&nbsp;&nbsp;bAllowApproximateOcclusion=TRUE   
>    &nbsp;&nbsp;&nbsp;&nbsp;bForceDirectLightMap=TRUE   
>    &nbsp;&nbsp;&nbsp;&nbsp;bUsePrecomputedShadows=TRUE   
> End Object

###### - We need to add these lines

> BlockRigidBody=false  
> bDisableAllRigidBody=true  
> bAcceptsDynamicDecals=false

###### - So it looks like this

> Begin Object Class=StaticMeshComponent Name=StaticMeshComponent0   
>    &nbsp;&nbsp;&nbsp;&nbsp;bAllowApproximateOcclusion=TRUE   
>    &nbsp;&nbsp;&nbsp;&nbsp;bForceDirectLightMap=TRUE   
>    &nbsp;&nbsp;&nbsp;&nbsp;bUsePrecomputedShadows=TRUE   
>    &nbsp;&nbsp;&nbsp;&nbsp;BlockRigidBody=false   
>    &nbsp;&nbsp;&nbsp;&nbsp;bDisableAllRigidBody=true   
>    &nbsp;&nbsp;&nbsp;&nbsp;bAcceptsDynamicDecals=false  
> End Object

---

##### PrimitiveComponent

---

###### - Next we modify ```PrimitiveComponent.uc``` ( This is so we can setup specific collision )
###### - Search for this part below

>enum ERBCollisionChannel  
>{  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_Default,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_Nothing, // Special channel that nothing should request collision with.  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_Pawn,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_Vehicle,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_Water,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_GameplayPhysics,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_EffectPhysics,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_Untitled1,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_Untitled2,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_Untitled3,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_Untitled4,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_Cloth,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_FluidDrain,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_SoftBody,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_FracturedMeshPart,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_BlockingVolume,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_DeadPawn,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_Clothing,  
> 	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_ClothingCollision  
> };

###### - Add these lines

>  RBCC_Ball,  
>  RBCC_VehicleBlocker,  
>  RBCC_BallBlocker,

###### - So it looks like this

>enum ERBCollisionChannel  
>{  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_Default,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_Nothing, // Special channel that nothing should request collision with.  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_Pawn,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_Vehicle,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_Water,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_GameplayPhysics,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_EffectPhysics,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_Ball,  
>  &nbsp;&nbsp;&nbsp;&nbsp;RBCC_VehicleBlocker,  
>  &nbsp;&nbsp;&nbsp;&nbsp;RBCC_BallBlocker,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_Untitled1,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_Untitled2,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_Untitled3,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_Untitled4,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_Cloth,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_FluidDrain,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_SoftBody,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_FracturedMeshPart,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_BlockingVolume,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_DeadPawn,  
>	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_Clothing,  
> 	&nbsp;&nbsp;&nbsp;&nbsp;RBCC_ClothingCollision  
> };

---

##### Actor

---

###### - Last but not least, ```Actor.uc``` ( So we can make FXActor appear on other clients, and probably more! )
###### - Find the ```bNoDelete``` bool
###### - The line looks like this ```var const bool	bNoDelete; // Cannot be deleted during play.```
###### - Add parentheses after ```var```
###### - So the line will now look like this ```var() const bool	bNoDelete; // Cannot be deleted during play.```
###### - Compile your scripts

#### Credits

---

###### - Derzo ( Collisions )
###### - glhglh ( Collision Channels )
###### - Eliot ( UE Explorer )
###### - Martinn ( UPK Decryptor )

**Last Updated: {{ last_modified_at }}**

{% capture toc %}
<div class="col hide-on-small-only m1 xl1">
      <div class="toc-wrapper pinned" style="top: 0px;">
         <ul class="table-of-contents">
            <li><a href="#requirements" class="active">Requirements</a></li>
            <li><a href="#setup">Setup</a></li>
            <li><a href="#templates">Templates</a></li>
            <li><a href="#third-party-options">Third-party Options</a></li>
            <li><a href="#sass">Sass</a></li>
         </ul>
      </div>
</div>
{% endcapture %}