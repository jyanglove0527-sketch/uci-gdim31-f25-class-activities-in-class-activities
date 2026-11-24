# in-class-activities
## Devlogs
### W1
Write your W1 activity Devlog here.

### W2
Create future Devlog sub-headers with the three # symbols, then write your Devlogs below them.

### W3
**Activity 1** (desk 17)
1. GetResponse: The parameters would be the player's friendship level (int) and a bool for whether the player knows the character's secret. The return type would be an int.
2. SetLightDimness: The parameter would be the color of the light. The return type would be a bool.
3. DidPlayerHitBeat: The parameter would be the time the player pressed the key (float). The return type would be an int, like a score.

**Activity 2**
A class is like a bungeoppang mold, and a Component is like an actual bungeoppang made from that mold. Member variables are like the filling inside each bungeoppang (red bean or custard), so every bungeoppang can have a different filling. Methods are things the bungeoppang can do, like being eaten.

**Activity 3**
I think the balls get brighter because the color is multiplied by 1.5 every time they bounce fast enough. Since the color keeps getting multiplied and the value never resets, it keeps getting bigger and bigger, so the balls become extremely 
bright after many bounces.

### W4
**Describing code activity** (Table 17)
- Line 17: _isGrounded is a member variable, and the type is bool. It keeps track of whether the cat is on the ground (true or false).
- Line 28: This is an if statement that calls the method Input.GetKeyDown with the parameter KeyCode.Space. If the player presses space AND the cat is on the ground, it runs the jump code.
- Line 32: This line sets _isGrounded to false after the cat jumps, so the cat can't jump twice in the air.

**Collision discussion activity** (Table 17)
I added Rigidbodies to the Cat and the SoccerBall, because both of them need to move with physics: the cat kicks the ball, and both of them bounce off the wall. I checked Is Trigger only on the Goal, because the ball needs to be detected when it's in the goal area but still pass through it.

My game did not work perfectly the first time. I accidentally added the SphereCollider and BoxCollider to the Cat instead of the SoccerBall and Goal, so I removed them and added them to the right objects. I also added a Rigidbody to the Goal at first, but I removed it because the Goal doesn't need to move and it could fall through the ground. Finally, my changes didn't show up until I saved the Scene.

### W5
**Activity 1: DeerW5 plan** (Table 17)
1. Member variables: The class needs one member variable, a Transform called _target. It has [SerializeField] so I can pick the GameObject the deer walks towards (like the red mushroom) in the Inspector.
2. Methods: The class needs the Start() method, which Unity provides. We only need to tell the deer where to go once, when the game begins, so we don't need Update().
3. What the method does: In Start(), the code uses GetComponent<NavMeshAgent>() to get the NavMeshAgent Component on the Deer. Then it calls SetDestination with _target.position, so the deer walks to the target using the NavMesh.

### W7
**Activity 1: Class resource guide** (worked solo)
I worked on this solo, so I covered all five categories: Unity engine, Unity coding, General C# coding, Math, and Other tools.
Google Doc: (https://docs.google.com/document/d/1TjnOc1VbgzegWC9C6DlKfWtkcqkQOYMobxgFTv75CLM/edit?usp=sharing)



**Activity 2: BatW6 plan** (Table 17, pair programming)
1. Member variables: a float _speed (tunable in the Inspector), a Transform _player for the cat the bat chases, and a bool _isChasing to remember if the bat is chasing right now.
2. Methods: two public methods we write ourselves, StartChase() and StopChase(), so BatManager can call them. We also use Unity's Update() method.
3. What they do: StartChase() sets _isChasing to true, and StopChase() sets it to false. Every frame, Update() checks _isChasing, and if it's true, the bat moves toward the player with Vector3.MoveTowards using _speed and Time.deltaTime.

### W8
**Activity 1** (Table 17)
What was wrong with the code in Step 2: it used Vector3.forward, which is the forward direction in world space (always the Z axis). So the Muskrat always moved along the same world direction, even after it turned. I fixed it by using transform.forward, which is the Muskrat's own forward direction in object space, so it moves the way it's facing.

I also had a problem where the Muskrat kept falling over and spinning. I fixed it by checking Freeze Rotation X, Y, and Z in the Rigidbody's Constraints. At first I accidentally checked Freeze Position, which stopped the Muskrat from jumping.

### W9
**Activity 1: Planning the final** (Table 17, 2D final)
- Google Drawing: https://docs.google.com/drawings/d/1VueSXfJZ0j5FzOOxjB7xZqciDOqmqtCt-GzcSZzlKcw/edit
- My plan has 4 main GameObjects: the Cat (player), the Item (prefab), the GameManager/UI, and the Grid with Tilemaps.

**Activity 2: Work on final**
- Played both final options and chose the 2D final.
- Read the Milestone 1 rubric.
- Drew a breakdown of the GameObjects, their Components, and how they connect (the Cat kicks Items, and Items tell the UI, which keeps a List of required items).
- Forked and cloned the 2D final project.

## Open-Source Assets
### W1
- Animals: https://assetstore.unity.com/packages/3d/characters/animals/animals-free-animated-low-poly-3d-models-260727 
- Low-poly environment: https://assetstore.unity.com/packages/3d/environments/landscapes/low-poly-simple-nature-pack-162153 