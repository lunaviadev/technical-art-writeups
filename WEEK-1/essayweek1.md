
# [Exploring the evolution of technical art optimisation for indie games.]

**Liliana Bellas** | **2326296** | **2/10/25**

---

## Introduction

For much of the industry's history, indie games have often been percieved as trailing behind their triple-A counterparts, striving to meet benchmarks established years earlier by studios with greater budgets and resources. However in recent years this perception has begun to shift. Indie games have risen to prominence which was largely fuelled by growing consumer interest in their lower cost, multi-platform accessibility and their reputation for innovation and creative design. In this essay I will explore how indie games have evolved as a distant force within the industry to pushing technical and artistic boundaries while continuously advancing optimisation practices in technical art. 

## Background/Historical Context

To provide historical context, the early era of indie game development was shaped by limited access to professional-grade engines. Tools such as Unity (2005), Unreal Engine, and CryEngine were either unavailable, prohibitively expensive, or restricted in their licensing models, which made them less accessible to smaller studios and independent creators compared to today. Prior to Unreal Engine's shift toward a more open licensing model in 2015 and CryEngine's similar changes around 2011, many developers either relied on freeware engines with significant limitations or bypassed engines altogether, opting instead to code directly in C++. This reflected a broader industry transition in the early 2000s from C to C++ as the dominant language for game programming. Research from the period also shows how optimisation was a core technical concern. For example, (Roimela et al, 2006) demonstrated early approaches to texture compression that incorporated anti-aliasing and luminance adjustments to improve framerates and shader efficiency. Similarly, (Inada and McCool, 2006) examined block-based, lossless texture compression methods, which were increasingly adopted by smaller developers seeking to improve rendering performance without sacrificing visual fidelity.

## Critical Analysis

For many indie developers, the choice of rendering pipeline is a foundational optimisation decision. While Deferred Rendering allows for complex lighting with numerous dynamic lights, it comes with a significant memory bandwidth cost which is typically unoptimal for many indie titles due to their (on average) lower-end hardware requirements and general stylistic choices that make them able to run on many machines. For many indie titles, Forward Rendering remains the superior choice, offering lower overhead and sharper visuals, particularly for stylized games where realistic lighting is secondary to art direction. However, Forward rendering is not entirely positive due to its many overlapping linear lights that can often slow down performance in games. This is where Forward+ Rendering becomes (Technologies, s.d.) of use for many indie developers using engines like Unity's Universal Render Pipeline (URP). By culling lights in screen space, it allows for more dynamic lighting than traditional Forward rendering without the heavy G-buffer cost of Deferred. This makes it ideal for developers who plan on putting their games on multiple systems with varying hardware capabilities.

When talking in regards to the effects that indie developers use to create games, tools such as Unreal Engine 5's Material Editor system and Unity's Universal Render Pipeline options have become core essentials for indie developers to optimise and push their games to a new visual height. These tools often allow many artists in the indie space to create truly stunning visuals without having significant cost financially for third party software, or hardware costs when running their games. Though despite the many positives of these tools being widely accessible to indie developers, it also works as a double-edged sword. In which you often see many developers who lack the technical understanding of these tools creating shaders and visuals with them that are entirely unoptimised and frankly run horribly. This issue is only made worse by the fact you often see many developers who lack enough research going into these engines assuming everything will run fine. This article from IGN (Barrier, 2022) clearly demonstrates my point of the fact that certain developers are becoming "Lazy" due to the ease of access and tools that are created with these enhancements in engines. Leading to many buggy games with poorly optimised graphics.

Though despite all these drawbacks of developers becoming too comfortable with premade tools. There are also many instances in which we see these tools being used for optimistaion and to play into stylistic choices. The 2022 action-adventure game *Tunic* is a prime example of utilising modern tools with a simplier aesthetic to create something that can run on all platforms. Diving into this youtube video posted by the developers of Tunic (The Design Evolution of Tunic | Developer Breakdown, 2022), you can see how the game evolved over time to adapt to it's design choices and how things like a fixed camera angle and limited art style also played into optimisation methods so that things could be hidden from the player in order to allow the game to run better. This low poly art style you see in *Tunic* is also incredibly common amongst many other indie titles due to its ease to optimise and run well whilst also being able to be ported to many platforms without having to worry too much about changes in optimisation and graphics. These tools and evolutions of the indie spave have allowed for many indie developers to fight on part with bigger triple a companies, where historically they were always falling a bit behind when it came to the tools and technologies they had access to. This has allowed for many indie developers to create games that are not only visually stunning but also able to run on a wide range of hardware without any issues.

## Future Implications/Conclusion

It's pretty clear that moving forward indie games will continue to close the gap between Triple A and secure their spot in the gaming landscape. THis article (Wu, s.d.) goes into great detail on the big boom of the indie scene following games like *Hollow Knight* and *Undertale* making their way into mainstream gamers catalogues. This has allowed for many other indie developers to become inspired that their form of game creation can be as successful as companies with high budgets and many employees as many players often state that they actually prefer indie games to those created by bigger studios. This bodes well for the direction of indie studios and the future of the industry as a whole as we see more adaptions to these tools and more technologies being developed that places power into the hands of smaller developers. With engines like Godot (Engine, s.d.) also proving that community led engines can be as successful as those created by larger studios, it's clear that the future of indie development is bright and full of potential.

### Bibliogrpahy 

Roimela, K., Aarnio, T. and Itäranta, J. (2006) 'High dynamic range texture compression' In: ACM SIGGRAPH 2006 Papers. New York, NY, USA: Association for Computing Machinery. pp.707-712. At: https://doi.org/10.1145/1179352.1141945 (Accessed  02/10/2025).

Inada, T. and McCool, M. D. (2006) 'Compressed lossless texture representation and caching' In: Proceedings of the 21st ACM SIGGRAPH/EUROGRAPHICS symposium on Graphics hardware. New York, NY, USA: Association for Computing Machinery. pp.111-120. At: https://doi.org/10.1145/1283900.1283918 (Accessed  02/10/2025).

Technologies, U. (s.d.) Unity - Manual: Forward and Forward+ rendering paths in URP. At: https://docs.unity3d.com/6000.2/Documentation/Manual/urp/rendering/forward-rendering-paths.html (Accessed  02/10/2025).

Barrier, R. (2022) What Unreal Engine 5 Means for the Games Industry. At: https://www.ign.com/articles/what-unreal-engine-5-means-for-the-games-industry (Accessed  02/10/2025).

The Design Evolution of Tunic | Developer Breakdown (2022) Directed by noclip_2. At: https://www.youtube.com/watch?v=A5A7uoJAOvY (Accessed  02/10/2025).

Wu, J. (s.d.) The Rise of Indie Games: How Passion and Creativity are Revolutionizing the Industry. At: https://thesciencesurvey.com/arts-entertainment/2025/03/09/the-rise-of-indie-games-how-passion-and-creativity-are-revolutionizing-the-industry/ (Accessed  02/10/2025).

Engine, G. (s.d.) Godot Engine - Free and open source 2D and 3D game engine. At: https://godotengine.org/ (Accessed  02/10/2025).


