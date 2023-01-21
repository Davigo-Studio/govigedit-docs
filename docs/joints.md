# Joints

By ŠpaceChickn#0012

## Different Joint Types

Davigo uses many types of joints to keep objects in place. For instance, the `Blockwall` prefab uses an Overlapping Joint, whereas the Tree prefab uses the `Detachable Network Spring Joint`. This may seem confusing at first, but be assured; with enough practice, you'll be a joint-making pro!


## Spring Joints

Spring Joints will cause your objects to stay in place and wiggle when force is applied to them, like the default tree prefab. All rigidbodies with spring joints need at least 2 components to fully work the way you'd expect them to, these being the `Detachable Network Spring Joint`(DNSJ), and the `Breakable Joint`(BJ) components respectively. If this is your first time making a rigidbody with a spring joint, I recommend setting the DNSJ's variables to what the Tree prefab uses.

Now, that's great and all, but what the heck do any of these variables mean?! Well, in order from top to bottom of each component:

## Detachable Network Spring Joint

![DefaultTree](_media/joints/treepeefab.png)

 - **Interpolation Data Source:** I honestly have no idea; unless you feel like experimenting, don't touchie.
 - **Break Effect Prefab:** This is the particle system that'll play when the spring joint finally breaks. It's a good idea to make this flashy to make it clear when it has broken.
 - **Initial Position / Rotation:** also no clue. if you find someone that actually knows about this, please update this.
 - **Bake Transform:** uh yeah no clue; yell at squirrel to explain it to you or something.
 - **Mode:** This setting has 3 options. By default, it's set to `Transform`
 - **Mode `Transform`:** This will cause your rigidbody to only spring back into place once it has been moved. This will not apply to rotation with this setting enabled.
 - **Mode `Rotation`:** Like `Transform`, this will cause your rigidbody to only spring back into place when it is rotated. However, this will cause your rigidbody to not stay in place, due to it only affecting rotation in this setting.
 - **Mode: `Both`:** This will cause your rigidbody to spring back into place when it is either moved or rotated. This will give your rigidbody the spring-y effect that the tree prefab has by default. This will also allow your rigidbody to stay in place.
 - **Translation / Angular Sping:** These settings affect how much force a rigidbody will use to go back to its original position or rotation, respectively. Make sure not to set the value too high, however, as your rigidbody will go shooting off into oblivion, rendering it useless.
 - **Translation / Angular Dampen:** This is the modifier applied to your rigidbody's tramslation / angular force. A high value will perserve less force, causing your rigidbody to wiggle less, whereas a lower value will let your object spring around to its heart's desire. It's recommended to keep these values between 0.1 - 0.9.

## Breakable Joint

![BreakableJoint](_media/joints/breakablejoint.png)

 - **Interpolation Data Source:** once again, no clue. leave it on auto unless you like headaches.
 - **Health:** This is how long it will take to pull your object out. A good range value range for spring joints is 50 - 80 health.
 - **Force / Impact Force Threshold:** These values dictate how much force your object can receive without breaking. A value around 8 usually works for most gameplay scenarios.
 - **Take Damage Effect:** This is the particle effect that will play when the joint takes damage. It's a good idea to make this effect cheap and easy to render, due to how frequently it'll be played in normal gameplay.
 - **Take Damage Audio Effect:** Similar to the damage effect, this sound will play when the joint takes damage. Davigo likes to freak out if you parenet your audio to the main object. Instead, have the interpolation target be the parent.


## Overlapping Joints

Overlapping joints keep your object in place until they are pulled out from where they happen to be. These, for whatever reason, need 3 components, as opposed to the spring joint's simplier 2. Don't worry about it though, it's super simple!

(i'll work on this part later; am tired from explaining things. if someone wants to attempt to do this, feel free)
