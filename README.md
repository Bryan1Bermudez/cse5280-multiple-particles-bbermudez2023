**Name:** Bryan Bermudez
**NetID:** bbermudez2023

# Note

Inorder to submit it to github i had to lower the framerate this results in some 
details not being as visable, most noteably the purple particle osilation. if
you wish to see the effects more clearly, modify this line
anim = FuncAnimation(fig, update, frames=range(0, n_steps, x)
where the lower the x is the more frames it has

The animations are present, they simply dont show in github
I added a static image to show the fact that the calculations are being done.
Inorder to see the animations you have to download the notebook.


# Comparative Analysis

# 1. How does directional dependence affect the symmetry of the social force field?
 In isotropic, where directions don't matter, particles end up more bunched together
 and tend to be fairly symmetric in their force, only ever shifting left or right
 due to multiple particles. So in the final spread of the isotropic we can see a
 fairly symmetric distribution. Comparatively, in anisotropic we can see that
 direction influences the symmetry greatly. We see this most notably at the end
 once the particles start taking different directions and during the middle sections
 where they move around chaotically. The symmetry that was present originally is
 broken as particles move in vastly different directions to one another. This is
 because the dot product term weights repulsion based on alignment with the
 velocity direction.

# 2. Does the anisotropic model reduce oscillations or deadlocks? Why?
 Not really. Looking at the simulation both suffer from deadlock and cannot reach
 the goal properly. Though it is notable that in isotropic the particles are more
 bunched up than in anisotropic, at least when examining the quadratic repulsion
 formula. Deadlocks still persist because the shared goal forces all particles to
 converge to the same point regardless of social force model. As for oscillations,
 it does seem to still happen but less so in anisotropic, notably shown by the
 smaller size of the congestion circles.

# 3. How does each model behave in narrow corridors or near bottlenecks?
 Isotropic:
 - Quadratic: particles behave similar to jelly marbles, for the most part never
   entering the influence of each other and keeping their distance. Near deadlocks
   and narrow corridors they line up neatly one after another.
 - Inverse: more harsh than quadratic by a large margin, with particles barely
   getting close to each other. In bottlenecks they almost wait until the first
   particle is further in before entering the corridor.
 - Exponential: surprisingly similar to inverse until the last part, likely due to
   the range of influence found in exponential. Once that range hurdle is passed
   they line up similar to quadratic though much closer. Exponential seems to be
   between quadratic and inverse in terms of behaviors in tight corridors.

 Anisotropic:
 - Quadratic: behaves similar to isotropic quadratic until the bottleneck, where
   it suddenly starts to act similar to inverse, with no particle entering until
   the first particle is halfway through.
 - Inverse: a lot of modification was needed for anisotropic inverse to work, as
   too much force caused particles to phase through the walls. The force is visibly
   stronger in anisotropic than isotropic. Around the midpoint the purple particle
   rapidly oscillates before stabilizing, compared to isotropic where only minor
   oscillation happens.
 - Exponential: this one has the biggest change between isotropic and anisotropic.
   Exponential in anisotropic results in particles being very far apart, with them
   very rarely being forced together. Unlike inverse it does not vibrate when nearby,
   instead flowing naturally back into position. This is also visible in the ending
   where anisotropic particles are much further apart than in isotropic.

# 4. What trade-offs arise when introducing velocity-dependent interactions?
 A evident trade-off is computation time. Due to isotropic not needing to account
 for velocity it spends less time computing each iteration. While running the
 simulation it was evident that anisotropic took more time to render than isotropic.
 Another trade-off is sensitivity. Isotropic is more resistant to parameter changes
 than anisotropic. Parameter tuning was needed to ensure that particles would not
 fly off violently in anisotropic.
