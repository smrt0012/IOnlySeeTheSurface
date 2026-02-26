# IOnlySeeTheSurface
<img width="958" height="214" alt="modbanner" src="https://github.com/user-attachments/assets/64dad40b-e90b-4c78-99ae-08cade56f598" />

Only render what you can see, Unload unseen segments of chunks.

/// A lightweight, aggressive vertical culling engine for modern Minecraft. ///
I Only See The Surface is a performance-focused utility that fundamentally changes how Minecraft handles hidden geometry. By intelligently "slicing" the world around the player, it eliminates the rendering of thousands of invisible blocks, providing a massive framerate boost—especially in the game's most demanding environments.


## 🚀 Optimization
Traditional culling only cares about what is behind you. I Only See The Surface cares about what is above and below you.

Vertical Geometry Elimination: In standard Minecraft, the game often renders chunks from the bedrock to the sky, even if you are standing on a solid grass plain. This mod aggressively culls chunks that are vertically out of your line of sight.

Massive FPS Gains: By reducing the "Render Batch" size, your GPU spends less time processing vertices that are buried under 60 blocks of stone.

Reduced Memory Overhead: By preventing the game from building render data for distant underground chunks while you’re on the surface, it lowers the strain on your system's RAM and CPU.


Example showing the outside chunk and inside chunk logic in real time.
https://github.com/user-attachments/assets/4352b6f0-a9be-4d5d-b17a-3fd726cfbe3f



## 💡 How does it work?
The mod utilizes a Dynamic Vertical Window logic that follows the player in real-time.

Surface Logic: While you are exploring the surface (above Y=40), the mod assumes the ground is solid. It culls everything deep underground, leaving only the immediate surface layer visible.

The "Mega Cave" Scanner: The mod constantly "pings" the area above the player’s head. If it detects a vertical air gap of 10 blocks or more, it recognizes you are in a massive cavern.Adaptive Rendering: Once a Mega Cave is detected, the "Vertical Window" automatically expands (up to 64 blocks high). This ensures that the epic scale of 1.18+ caverns is preserved, and you never see "holes" in the ceiling while exploring the deep dark.

Tiered Chunk Slicing: Chunks within a close radius are rendered more generously, while distant chunks are sliced to their absolute minimum to keep the horizon looking solid without the performance cost.
