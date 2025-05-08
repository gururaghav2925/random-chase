# AI Random Roam - Unreal Engine

## Aim
To implement an AI character in Unreal Engine that roams randomly within a defined area using Behavior Trees and Navigation Mesh.

## Procedure

1. **Navigation Setup**
   - Add a `NavMeshBoundsVolume` to your level and scale it to cover the roamable area.
   - Ensure navigation is built (press **P** to visualize the navmesh).

2. **Create AI Character**
   - Create a new `Character` or `Pawn` Blueprint (e.g., `BP_AICharacter`).
   - Add an `AIController` Blueprint (e.g., `BP_AIController`) and assign it to your AI character.

3. **Set Up Behavior Tree**
   - Create a `Behavior Tree` (e.g., `BT_RandomRoam`) and a corresponding `Blackboard`.
   - Add a `Blackboard Key` (e.g., `TargetLocation`) of type Vector.

4. **Implement Roaming Logic**
   - In the Behavior Tree, use the following structure:
     - **Root** ➝ **Selector**
       - **Sequence**
         - `Find Random Location` (custom task to set `TargetLocation`)
         - `Move To` node (uses `TargetLocation`)
   - Create a custom `BTTask` Blueprint for finding a random location using `UNavigationSystemV1::GetRandomPointInNavigableRadius`.

5. **Place and Test**
   - Place your AI character in the level.
   - Assign the AI Controller and Behavior Tree.
   - Play the scene and observe the AI roaming randomly.



## Output


![Screenshot 2025-05-08 221444](https://github.com/user-attachments/assets/2bfed4fb-8a19-47e9-9b7f-23fbc1cee889)



![image](https://github.com/user-attachments/assets/286ac6c8-e8a1-4d75-b03f-c5bc78b75f17)



![image](https://github.com/user-attachments/assets/792fcfa6-da04-4187-9ea6-fa756a158de6)



![image](https://github.com/user-attachments/assets/479bd6be-0a5a-43cc-8d44-b5be25f5ee0e)


![image](https://github.com/user-attachments/assets/ce3e04b6-4581-4669-8225-01837f12f8f5)



## Result
The AI character successfully roams within the defined NavMesh area, choosing random destinations at intervals using the Behavior Tree logic.

