# Week 5 - Niagara VFX Technical Report

## 1. Fire Effect

### Research

Before diving into the project I wanted to do a little research on Niagara systems in order to deeper understand what I would be working with for this week worth of content. 

I looked into various forum posts that were created by others in the community and I found a lot of useful information on how to create Niagara systems and how to use them in a blueprint. I looked briefly through the documentation of the Niagara systems provided by unreal (Creating Visual Effects in Niagara for Unreal Engine | Unreal Engine 5.7 Documentation | Epic Developer Community, s.d.). This helped me to generalise how to use the Niagara system and how to create emitters and renderers.

For the fire effect I had found a really short and simple tutorial to create the fire. (Super Easy Fire Effect in Unreal Engine 5.4, 2024). It used SubUVs which weren't necessary for this portion of the week's content so I just swapped that out for using basic sprite rendering. 

---

For the first effect, I created a standard fire system `NS_FireNormal` designed to be a versatile environmental asset. The core of this effect relies on a sprite renderer to create the illusion of rising flames through upward velocity and turbulence.

I started by setting up a `SpawnRate` module driven by a User Parameter `User.SpawnRate`. This allows me to control the density of the fire directly from the level instance without opening the Niagara editor. The particles are spawned from a Sphere location, giving the fire a natural, rounded base.

To make the movement feel realistic, I used `Add Velocity` with a random range, controlled by `User.MinVelocity` and `User.MaxVelocity`. I also added a `Drag` module to slow the particles down as they rise, simulating air resistance. The color transitions from a hot core to cool smoke using a `LinearColor` curve, which I also exposed as a user parameter `User.Curve for Colors`.

![Fire Setup](image.png)
*Figure 1: The Niagara System overview for the Fire effect, showing the emitter stack.*

![Fire Effect In-Game](firenormalgif.gif)
*Figure 2: The final Fire effect in the level.*

![alt text](image-15.png)
*Figure 2.1: Additional user parameters I added for the Fire effect.*

## 2. Fireball Projectile

When it came down to doing some research for the fireball projectile, I found this useful post on artstation from a 3D artist who had created a fireball projectile using Niagara systems. (Stylized Fireball VFX UE5, s.d.). This artstation post clearly outlined the blueprints for the material alongside their setup for the Niagara system, which was a great starting point for my own implementation. I worked with this as a base for creating my own fireball projectile.

I ultimately looked at this tutorial I found on youtube (Create a Fireball Projectile VFX in Unreal Engine Using Niagara System Tutorial Custom Texture, 2023) which had pretty much everything I needed in order to create the fireball projectile.

---

I implemented the Fireball as a projectile-based effect, `NS_Fireball`. This system is more complex, combining a glowing core, a smoke trail, and sparks. It's designed to work with the `BP_Shooter` blueprint I set up.

The most important part of this effect is the trail. I used a `NiagaraRibbonRendererProperties` for the `Trail` emitter. This creates a smooth, continuous geometry behind the projectile, which looks much better than just spawning a line of sprites. The ribbon uses `M_Trail`, a material I set up with `MaterialExpressionPanner` to scroll two textures (`TestTexture90` and `T_Smoke_Tiled_D`) at different speeds. This makes the trail look like it's flowing and evolving, not just a static streak.

![M_Trail setup](image-1.png)
![alt text](image-2.png)
*Figure 3: The M_Trail material setup with two textures scrolling at different speeds.*

I then duplicated the emitter for FireRibbon to create a second FireRibbon which was used to add a bit more depth and variety to the Ribbon trail that would follow behind the main particle. I went in and adjusted thingsl ike the `Spawn Rate` and various parameters to make it look visually different from the main trail.

![alt text](nosecondribbon.gif) 
*Figure 4: Without Second Ribbon*
![alt text](withsecondribbon.gif)
*Figure 4.1: With Second Ribbon*

I then finished it off by making emitters for the smoke and the actual fireball. This was achieved by using my M_Smoke material and various parameters to control the smoke's behavior. I also added a `Drag` module to slow the particles down as they trail behind the main particle.

![alt text](image-3.png)

*Figure 5: The smoke and fireball emitters.*

I then very quickly set up a very basic `BP_Shooter` blueprint to spawn the projectile just so I could demonstrate how it looked being fired from a spawner.

![alt text](fireballshooting.gif)

*Figure 6: The Fireball being fired from a spawner.*

![alt text](image-14.png)
*Additional user parameters I added*

## 3. Lightning Strike

When looking for resources to help me with the lightning strike asset, it was a bit more scarce in what I could find documented online to help me with what I needed specifically. I found a short thread on reddit (Emotional-Bid-4173, 2022) which very loosely outlined a basic striking lightning asset setup, though wasn't very indepth nor did it contain much information that I could use to create a basis for my own asset. 

I turned to the unreal engine forums and found a slightly better step by step in order to create a basis for my own asset (Lightning VFX: Step-by-Step Guide | ICVR Lightfall | Community tutorial, 2024). This forum post had a bit more depth to it and allowed me to understand the general outline of what emitters and states I would need to be using, with the application of short lifetime mixed with the use of `Spawn Burst Instantaneous` in order to create the main bolt flashing effect.

Settling on a middle ground I then utilised parts of a tutorial I found online to fill my gaps in knowledge, more specifically when it came to creating additional effects like sparks flying off the ground upon collision. (Simple Lightning Strike Part 1 - Custom Lightning Strike with Sparks Unreal Engine Niagara, 2023). This tutorial was effective at highlighting that in a simple manner and ultimately was a useful resource for me to create the sparks and the emitter which I then tweaked to be more in line with the thunderbolt I made.

---

For the Lightning Strike `NS_LightningStrike`, I wanted a short-lived, high-impact effect. I used a Ribbon Renderer again and utilised a `Spawn Burst Instantaneous` in order to create the main bolt flashing effect. Combined with a short lifetime, this creates the illusion of a flash of lightning.

![alt text](image-4.png)
*Figure 7: The Lightning Strike emitter setup.*

In order to give the lightning some adjustable parameters too, I created a `LightningStrike` user parameter which allows the user to adjust the colour of said lightning strike. I also created a few more parameters such as `Size Minimum` and `Size Maximum` which are both Vector 2Ds in order to control the size of the lightning strike. To top it off I then added a `NoiseStrength` user parameter so you can adjust the noise strength of the lightning strike.

![Lightning Strike User Parameters](image-5.png)
*Figure 8: The Lightning Strike user parameters.*

To add a bit more flair to the effect too, I created a new emitter which utilised a `M_Glow` which was used to create some glowing sparks that would appear when the ground was hit by the lightning.

![alt text](image-6.png)
*Figure 9: Glow Material Setup*

I then adjusted a few parameters for the sparks and specifically added some `Gravity Force` and `Drag` to make the sparks look more natural and less like they were just floating in the air. This gave them a realistic look as if they would spew out from the broken ground and then bounce back to the floor.

![alt text](image-7.png)
*Figure 10: Spark Emitter Setup*

![alt text](lightningstrike.gif)
*Figure 11: The final Lightning Strike effect in the level.*

## 4. Slash Attack VFX

The slash effect was actually suprisingly easy to create as it was utilising sockets and meshes which I had already covered in depth for the prior week of work. The only research I wanted to look into was how to actually create the sword trail effect in the Niagara system as utilising animation notifiers to link it up to my animation montage was already something I had understood. I found this tutorial on youtube (UE5: How To Make ‘Sword-Trails’ (In 3 Minutes), 2024) which perfectly outlined the exact thing I needed which was creating the sword trail. 

---

For the Slash Attack, I utilised the `Stable_Sword_Outward_Slash_Montage` I had made in the previous week to drive the visual effects. The key to this implementation was using Animation Notifiers to trigger the effect at the precise moment of the swing.

I used the `AnimNotifyState_TimedNiagaraEffect` which is a built-in notify state that allows for the spawning of a Niagara System for a duration. I set the Template to `NS_SwordTrail` and attached it to the `WeaponTip` socket. This ensures the trail follows the tip of the blade perfectly during the animation.

![alt text](image-16.png)
*Figure 12: The AnimNotifyState_TimedNiagaraEffect setup in the animation montage.*

The `NS_SwordTrail` system itself relies on a `NiagaraRibbonRendererProperties` within the `Minimal` emitter. This renderer generates geometry between the spawned particles, creating a smooth, continuous trail that visualizes the weapon's path. The system is spawned and updated based on the duration defined in the animation notify, ensuring it only appears during the active slash frames.

![alt text](image-17.png)
*Figure 13: The NS_SwordTrail system showing the ribbon renderer setup.*

Additionally I had to sample both sockets on the skeletal mesh of my weapon in order to get the trail to follow the tip of the blade perfectly. I then created `trailDirection` and `trailWidth` so that I would be able to directly link these vectors to the initalise particle lerp.

![alt text](slashes.gif)
*Figure 14: The final Slash effect in the editor montage.*


## 5. Decal Impact

For a decal impact I had a brief look into unreal engine's documentation of a decal renderer in order to better understand how I would go about creating and implementing this decal into my project. (Decals in Unreal Engine | Unreal Engine 5.7 Documentation | Epic Developer Community, s.d.). This pretty clearly outlined what the decal was and how I could integrate it with Niagara's systems. 

I then also read through Niagara renderers in order to see how I could directly use this to add a decal renderer into my emitter for my blood effect. (Render Module Reference for Niagara Effects in Unreal Engine | Unreal Engine 5.7 Documentation | Epic Developer Community, s.d.). This proved to be useful as I was able to understand implementation of the decal renderer property and use that in order to have decals spawn on the ground after my emitter was done emitting the blood splatter particles.

---

For the impact effect, I used `NS_Blood` to create a splatter on the ground. This is triggered when the attack first hits an enemy that can take damage, which then transitions into a decal when it collides with a surface.

![alt text](image-8.png)
*Figure 15: The spawning system blueprints after damage is applied to the enemy.*

The core of this effect is the `Stain` emitter. It spawns a single particle that acts as a decal. I used `M_Blood`, which creates a masked stain using a texture sample. In the Blueprint logic for the notify, I perform a Line Trace to find the ground position and the Surface Normal. I pass these values to the Niagara system so the decal aligns perfectly with the floor, regardless of the slope.

![alt text](image-9.png)
*Figure 16: The emitter setup for NS_Blood.*

I utilised a variety of user parameters too so that certain aspects such as the amount of blood splatter, how long the blood would linger for and how big the blood would be could all be adjusted accordingly if it needed to be increased or decreased for specific reasons.

![alt text](image-10.png)
*Figure 17: The user parameters for NS_Blood.*

![alt text](bloodsplatter.gif)
*Figure 18: The final Blood splatter effect.*

## 6. SubUV Flipbook Implementation

My research for the SubUV was already mostly covered in my first fire task as the resources I looked into actually contained coverage of SubUV.

---

Finally, I created a high-fidelity variant of the fire effect, `NS_FireFlipbook`. Instead of a single static texture, this uses a Flipbook (SubUV) texture sheet. It is in essence just my fire effect except using a different material which supported SubUV elements. For this reason I wont be breaking down most of the setup as it is identical to the standard fire effect.

I enabled `SubUV` on the Sprite Renderer and used the `SubUVAnimation` module. This module iterates through the frames of the texture sheet over the particle's lifetime. This bakes complex fluid simulation behavior into the texture, making the fire look much more realistic and volatile than the standard sprite version.

![alt text](image-11.png)
*Figure 19: The SubUV settings in the Sprite Renderer.*

![alt text](image-12.png)
*Figure 20: The SubUV settings in the NS_FireFlipbook sprite renderer.*

I then set up a similar amount of user parameters for this one, however I also created a `Scale` user parameter to control the size of the fire. This would allow the fire to properly scale to become larger and ultimately not break when you would size it up.

![alt text](image-13.png)
*Figure 21: The user parameters for NS_FireFlipbook.*

![alt text](comparison.gif)
*Figure 22: Side-by-side comparison of the Standard Fire (left) and Flipbook Fire (right).*


## BIBLIOGRAPHY

Super Easy Fire Effect in Unreal Engine 5.4 (2024) Directed by hawaiifilmschool. At: https://www.youtube.com/watch?v=6h7kzUdbjHk (Accessed  29/11/2025).

Creating Visual Effects in Niagara for Unreal Engine | Unreal Engine 5.7 Documentation | Epic Developer Community (s.d.) At: https://dev.epicgames.com/documentation/en-us/unreal-engine/creating-visual-effects-in-niagara-for-unreal-engine (Accessed  29/11/2025).

Stylized Fireball VFX UE5 (s.d.) At: https://emagal9.artstation.com/projects/g0L2nP (Accessed  30/11/2025).

Create a Fireball Projectile VFX in Unreal Engine Using Niagara System Tutorial Custom Texture (2023) Directed by Breez-E Game Studios. At: https://www.youtube.com/watch?v=eOu-PGwRjDs (Accessed  30/11/2025).

Emotional-Bid-4173 (2022) How to make realistic forking lightning/thunder?. [Reddit Post] At: https://www.reddit.com/r/unrealengine/comments/zp9lzr/how_to_make_realistic_forking_lightningthunder/ (Accessed  30/11/2025).

Simple Lightning Strike Part 1 - Custom Lightning Strike with Sparks Unreal Engine Niagara (2023) Directed by Breez-E Game Studios. At: https://www.youtube.com/watch?v=YQlskAHqcas (Accessed  30/11/2025).

UE5: How To Make ‘Sword-Trails’ (In 3 Minutes) (2024) Directed by Royal Skies. At: https://www.youtube.com/watch?v=LibOjabsOw8 (Accessed  30/11/2025).

Decals in Unreal Engine | Unreal Engine 5.7 Documentation | Epic Developer Community (s.d.) At: https://dev.epicgames.com/documentation/en-us/unreal-engine/decals-in-unreal-engine (Accessed  01/12/2025).

Render Module Reference for Niagara Effects in Unreal Engine | Unreal Engine 5.7 Documentation | Epic Developer Community (s.d.) At: https://dev.epicgames.com/documentation/en-us/unreal-engine/render-module-reference-for-niagara-effects-in-unreal-engine (Accessed  01/12/2025).





