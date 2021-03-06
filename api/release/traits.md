This documentation is aimed at modders. It displays all traits with default values and developer commentary. Please do not edit it directly, but add new `[Desc("String")]` tags to the source code. This file has been automatically generated for version 20210517 of OpenHV.



### ChatCommands
Enables commands triggered by typing them into the chatbox. Attach this to the world actor.

### DebugVisualizationCommands
Enables visualization commands via the chatbox. Attach this to the world actor.

### DevCommands
Enables developer cheats via the chatbox. Attach this to the world actor.

### HelpCommand
Shows a list of available commands in the chatbox. Attach this to the world actor.

### PlayerCommands
Allows the player to pause or surrender the game via the chatbox. Attach this to the world actor.


### LuaScript
Part of the new Lua API.

Requires trait: [`SpawnMapActors`](#spawnmapactors).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Scripts</td><td></td><td>Set of System.String[]</td><td></td></tr>
</table>

### ScriptTriggers
Allows map scripts to attach triggers to this actor via the Triggers global.


### AcceptsDeliveredCash
Tag trait for actors with `DeliversCash`.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ValidTypes</td><td></td><td>Set of System.String[]</td><td>Accepted `DeliversCash` types. Leave empty to accept all types. </td></tr>
<tr><td>ValidRelationships</td><td>Ally</td><td>PlayerRelationship</td><td>Player relationships the owner of the delivering actor needs. </td></tr>
<tr><td>Sounds</td><td></td><td>Collection of String</td><td>Play a randomly selected sound from this list when accepting cash. </td></tr>
</table>

### AcceptsDeliveredExperience
Tag trait for actors with `DeliversExperience`.

Requires trait: [`GainsExperience`](#gainsexperience).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ValidTypes</td><td></td><td>Set of System.String[]</td><td>Accepted `DeliversExperience` types. Leave empty to accept all types. </td></tr>
<tr><td>ValidRelationships</td><td>Ally</td><td>PlayerRelationship</td><td>Player relationships the owner of the delivering actor needs. </td></tr>
</table>

### ActorSpawner
An actor with this trait indicates a valid spawn point for actors of ActorSpawnManager.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Types</td><td></td><td>Set of System.String[]</td><td>Type of ActorSpawner with which it connects. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### Aircraft
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>IdleBehavior</td><td>None</td><td>IdleBehaviorType</td><td>Behavior when aircraft becomes idle. Options are Land, ReturnToBase, LeaveMap, and None. 'Land' will behave like 'None' (hover or circle) if a suitable landing site is not available. </td></tr>
<tr><td>CruiseAltitude</td><td>1c256</td><td>1D World Distance</td><td></td></tr>
<tr><td>Repulsable</td><td>True</td><td>Boolean</td><td>Whether the aircraft can be repulsed. </td></tr>
<tr><td>IdealSeparation</td><td>1c682</td><td>1D World Distance</td><td>The distance it tries to maintain from other aircraft if repulsable. </td></tr>
<tr><td>RepulsionSpeed</td><td>-1</td><td>Integer</td><td>The speed at which the aircraft is repulsed from other aircraft. Specify -1 for normal movement speed. </td></tr>
<tr><td>InitialFacing</td><td>0</td><td>1D World Angle</td><td></td></tr>
<tr><td>TurnSpeed</td><td>512</td><td>1D World Angle</td><td>Speed at which the actor turns. </td></tr>
<tr><td>IdleTurnSpeed</td><td></td><td>1D World Angle (optional)</td><td>Turn speed to apply when aircraft flies in circles while idle. Defaults to TurnSpeed if undefined. </td></tr>
<tr><td>Speed</td><td>1</td><td>Integer</td><td>Maximum flight speed when cruising. </td></tr>
<tr><td>IdleSpeed</td><td>-1</td><td>Integer</td><td>If non-negative, force the aircraft to move in circles at this speed when idle (a speed of 0 means don't move), ignoring CanHover. </td></tr>
<tr><td>Pitch</td><td>0</td><td>1D World Angle</td><td>Body pitch when flying forwards. Only relevant for voxel aircraft. </td></tr>
<tr><td>PitchSpeed</td><td>0</td><td>1D World Angle</td><td>Pitch steps to apply each tick when starting/stopping. </td></tr>
<tr><td>Roll</td><td>0</td><td>1D World Angle</td><td>Body roll when turning. Only relevant for voxel aircraft. </td></tr>
<tr><td>IdleRoll</td><td></td><td>1D World Angle (optional)</td><td>Body roll to apply when aircraft flies in circles while idle. Defaults to Roll if undefined. Only relevant for voxel aircraft. </td></tr>
<tr><td>RollSpeed</td><td>0</td><td>1D World Angle</td><td>Roll steps to apply each tick when turning. </td></tr>
<tr><td>MinAirborneAltitude</td><td>1</td><td>Integer</td><td>Minimum altitude where this aircraft is considered airborne. </td></tr>
<tr><td>LandableTerrainTypes</td><td></td><td>Set of System.String[]</td><td></td></tr>
<tr><td>MoveIntoShroud</td><td>True</td><td>Boolean</td><td>Can the actor be ordered to move in to shroud? </td></tr>
<tr><td>Crushes</td><td></td><td>Collection of CrushClass</td><td>e.g. crate, wall, infantry </td></tr>
<tr><td>CrushDamageTypes</td><td></td><td>Collection of DamageType</td><td>Types of damage that are caused while crushing. Leave empty for no damage types. </td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>TargetLineColor</td><td>008000</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line for regular move orders. </td></tr>
<tr><td>AirborneCondition</td><td></td><td>String</td><td>The condition to grant to self while airborne. </td></tr>
<tr><td>CruisingCondition</td><td></td><td>String</td><td>The condition to grant to self while at cruise altitude. </td></tr>
<tr><td>CanHover</td><td>False</td><td>Boolean</td><td>Can the actor hover in place mid-air? If not, then the actor will have to remain in motion (circle around). </td></tr>
<tr><td>CanSlide</td><td>False</td><td>Boolean</td><td>Can the actor immediately change direction without turning first (doesn't need to fly in a curve)? </td></tr>
<tr><td>VTOL</td><td>False</td><td>Boolean</td><td>Does the actor land and take off vertically? </td></tr>
<tr><td>TurnToLand</td><td>False</td><td>Boolean</td><td>Does this VTOL actor need to turn before landing (on terrain)? </td></tr>
<tr><td>TakeOffOnResupply</td><td>False</td><td>Boolean</td><td>Does this actor automatically take off after resupplying? </td></tr>
<tr><td>TakeOffOnCreation</td><td>True</td><td>Boolean</td><td>Does this actor automatically take off after creation? </td></tr>
<tr><td>CanForceLand</td><td>True</td><td>Boolean</td><td>Can this actor be given an explicit land order using the force-move modifier? </td></tr>
<tr><td>LandAltitude</td><td>0c0</td><td>1D World Distance</td><td>Altitude at which the aircraft considers itself landed. </td></tr>
<tr><td>LandRange</td><td>5c0</td><td>1D World Distance</td><td>Range to search for an alternative landing location if the ordered cell is blocked. </td></tr>
<tr><td>MaximumPitch</td><td>28</td><td>1D World Angle</td><td>How fast this actor ascends or descends during horizontal movement. </td></tr>
<tr><td>AltitudeVelocity</td><td>0c43</td><td>1D World Distance</td><td>How fast this actor ascends or descends when moving vertically only (vertical take off/landing or hovering towards CruiseAltitude). </td></tr>
<tr><td>TakeoffSounds</td><td></td><td>Collection of String</td><td>Sounds to play when the actor is taking off. </td></tr>
<tr><td>LandingSounds</td><td></td><td>Collection of String</td><td>Sounds to play when the actor is landing. </td></tr>
<tr><td>WaitDistanceFromResupplyBase</td><td>3c0</td><td>1D World Distance</td><td>The distance of the resupply base that the aircraft will wait for its turn. </td></tr>
<tr><td>NumberOfTicksToVerifyAvailableAirport</td><td>150</td><td>Integer</td><td>The number of ticks that a airplane will wait to make a new search for an available airport. </td></tr>
<tr><td>PreviewFacing</td><td>384</td><td>1D World Angle</td><td>Facing to use for actor previews (map editor, color picker, etc) </td></tr>
<tr><td>EditorFacingDisplayOrder</td><td>3</td><td>Integer</td><td>Display order for the facing slider in the map editor </td></tr>
<tr><td>RequireForceMoveCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition under which the regular (non-force) move cursor is disabled. </td></tr>
<tr><td>Cursor</td><td>move</td><td>String</td><td>Cursor to display when a move order can be issued at target location. </td></tr>
<tr><td>BlockedCursor</td><td>move-blocked</td><td>String</td><td>Cursor to display when a move order cannot be issued at target location. </td></tr>
<tr><td>EnterCursor</td><td>enter</td><td>String</td><td>Cursor to display when able to land at target building. </td></tr>
<tr><td>EnterBlockedCursor</td><td>enter-blocked</td><td>String</td><td>Cursor to display when unable to land at target building. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### AttackAircraft

Requires trait: [`Aircraft`](#aircraft).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>AttackType</td><td>Default</td><td>AirAttackType</td><td>Attack behavior. Currently supported types are: Default: Attack while following the default movement rules. Hover: Hover, even if the Aircraft can't hover while idle. Strafe: Perform a fixed-length attack run on the target. </td></tr>
<tr><td>StrafeRunLength</td><td>0c0</td><td>1D World Distance</td><td>Distance the strafing aircraft makes to a target before turning for another pass. When set to WDist.Zero this defaults to the maximum armament range. </td></tr>
<tr><td>AbortOnResupply</td><td>True</td><td>Boolean</td><td>Does this actor cancel its attack activity when it needs to resupply? Setting this to 'false' will make the actor resume attack after reloading. </td></tr>
<tr><td>OpportunityFire</td><td>True</td><td>Boolean</td><td>Automatically acquire and fire on targets of opportunity when not actively attacking. </td></tr>
<tr><td>PersistentTargeting</td><td>True</td><td>Boolean</td><td>Keep firing on targets even after attack order is cancelled </td></tr>
<tr><td>RangeMargin</td><td>1c0</td><td>1D World Distance</td><td>Range to stay away from min and max ranges to give some leeway if the target starts moving. </td></tr>
<tr><td>Armaments</td><td>primary, secondary</td><td>Collection of String</td><td>Armament names </td></tr>
<tr><td>Cursor</td><td></td><td>String</td><td>Cursor to display when hovering over a valid target. </td></tr>
<tr><td>OutsideRangeCursor</td><td></td><td>String</td><td>Cursor to display when hovering over a valid target that is outside of range. </td></tr>
<tr><td>TargetLineColor</td><td>DC143C</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line. </td></tr>
<tr><td>AttackRequiresEnteringCell</td><td>False</td><td>Boolean</td><td>Does the attack type require the attacker to enter the target's cell? </td></tr>
<tr><td>TargetFrozenActors</td><td>False</td><td>Boolean</td><td>Allow firing into the fog to target frozen actors without requiring force-fire. </td></tr>
<tr><td>ForceFireIgnoresActors</td><td>False</td><td>Boolean</td><td>Force-fire mode ignores actors and targets the ground instead. </td></tr>
<tr><td>OutsideRangeRequiresForceFire</td><td>False</td><td>Boolean</td><td>Force-fire mode is required to enable targeting against targets outside of range. </td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>FacingTolerance</td><td>512</td><td>1D World Angle</td><td>Tolerance for attack angle. Range [0, 512], 512 covers 360 degrees. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### AttackBomber
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>FacingTolerance</td><td>8</td><td>1D World Angle</td><td>Tolerance for attack angle. Range [0, 512], 512 covers 360 degrees. </td></tr>
<tr><td>Armaments</td><td>primary, secondary</td><td>Collection of String</td><td>Armament names </td></tr>
<tr><td>Cursor</td><td></td><td>String</td><td>Cursor to display when hovering over a valid target. </td></tr>
<tr><td>OutsideRangeCursor</td><td></td><td>String</td><td>Cursor to display when hovering over a valid target that is outside of range. </td></tr>
<tr><td>TargetLineColor</td><td>DC143C</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line. </td></tr>
<tr><td>AttackRequiresEnteringCell</td><td>False</td><td>Boolean</td><td>Does the attack type require the attacker to enter the target's cell? </td></tr>
<tr><td>TargetFrozenActors</td><td>False</td><td>Boolean</td><td>Allow firing into the fog to target frozen actors without requiring force-fire. </td></tr>
<tr><td>ForceFireIgnoresActors</td><td>False</td><td>Boolean</td><td>Force-fire mode ignores actors and targets the ground instead. </td></tr>
<tr><td>OutsideRangeRequiresForceFire</td><td>False</td><td>Boolean</td><td>Force-fire mode is required to enable targeting against targets outside of range. </td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>FacingTolerance</td><td>8</td><td>1D World Angle</td><td>Tolerance for attack angle. Range [0, 512], 512 covers 360 degrees. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### FallsToEarth
Causes aircraft husks that are spawned in the air to crash to the ground.

Requires trait: [`Aircraft`](#aircraft).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Explosion</td><td>UnitExplode</td><td>String</td><td>Explosion weapon that triggers when hitting ground. </td></tr>
<tr><td>MaximumSpinSpeed</td><td></td><td>1D World Angle (optional)</td><td>Limit the maximum spin (in angle units per tick) that can be achieved while crashing. 0 disables spinning. Leave undefined for no limit. </td></tr>
<tr><td>Moves</td><td>False</td><td>Boolean</td><td>Does the aircraft (husk) move forward at aircraft speed? </td></tr>
<tr><td>Velocity</td><td>0c43</td><td>1D World Distance</td><td>Velocity (per tick) at which aircraft falls to ground. </td></tr>
</table>

### AmmoPool
Actor has a limited amount of ammo, after using it all the actor must reload in some way.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Name</td><td>primary</td><td>String</td><td>Name of this ammo pool, used to link reload traits to this pool. </td></tr>
<tr><td>Armaments</td><td>primary, secondary</td><td>Collection of String</td><td>Name(s) of armament(s) that use this pool. </td></tr>
<tr><td>Ammo</td><td>1</td><td>Integer</td><td>How much ammo does this pool contain when fully loaded. </td></tr>
<tr><td>InitialAmmo</td><td>-1</td><td>Integer</td><td>Initial ammo the actor is created with. Defaults to Ammo. </td></tr>
<tr><td>ReloadCount</td><td>1</td><td>Integer</td><td>How much ammo is reloaded after a certain period. </td></tr>
<tr><td>RearmSound</td><td></td><td>String</td><td>Sound to play for each reloaded ammo magazine. </td></tr>
<tr><td>ReloadDelay</td><td>50</td><td>Integer</td><td>Time to reload per ReloadCount on airfield etc. </td></tr>
<tr><td>AmmoCondition</td><td></td><td>String</td><td>The condition to grant to self for each ammo point in this pool. </td></tr>
</table>

### AppearsOnMapPreview
Render this actor when creating the minimap while saving the map.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Color</td><td>00000000</td><td>Color (RRGGBB[AA] notation)</td><td>Use this color to render the actor, instead of owner player color. </td></tr>
<tr><td>Terrain</td><td></td><td>String</td><td>Use this terrain color to render the actor, instead of owner player color. Overrides `Color` if both set. </td></tr>
</table>

### Armament
Allows you to attach weapons to the unit (use @IdentifierSuffix for > 1)

Requires trait: [`AttackBase`](#attackbase).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Name</td><td>primary</td><td>String</td><td></td></tr>
<tr><td>Weapon</td><td><em>(required)</em></td><td>String</td><td>Has to be defined in weapons.yaml as well. </td></tr>
<tr><td>Turret</td><td>primary</td><td>String</td><td>Which turret (if present) should this armament be assigned to. </td></tr>
<tr><td>FireDelay</td><td>0</td><td>Integer</td><td>Time (in frames) until the weapon can fire again. </td></tr>
<tr><td>LocalOffset</td><td></td><td>Collection of 3D World Vector</td><td>Muzzle position relative to turret or body, (forward, right, up) triples. If weapon Burst = 1, it cycles through all listed offsets, otherwise the offset corresponding to current burst is used. </td></tr>
<tr><td>LocalYaw</td><td></td><td>Collection of 1D World Angle</td><td>Muzzle yaw relative to turret or body. </td></tr>
<tr><td>Recoil</td><td>0c0</td><td>1D World Distance</td><td>Move the turret backwards when firing. </td></tr>
<tr><td>RecoilRecovery</td><td>0c9</td><td>1D World Distance</td><td>Recoil recovery per-frame </td></tr>
<tr><td>MuzzleSequence</td><td></td><td>String</td><td>Muzzle flash sequence to render </td></tr>
<tr><td>MuzzlePalette</td><td>effect</td><td>String</td><td>Palette to render Muzzle flash sequence in </td></tr>
<tr><td>ReloadingCondition</td><td></td><td>String</td><td>Condition to grant while reloading. </td></tr>
<tr><td>TargetRelationships</td><td>Enemy</td><td>PlayerRelationship</td><td></td></tr>
<tr><td>ForceTargetRelationships</td><td>Enemy, Neutral, Ally</td><td>PlayerRelationship</td><td></td></tr>
<tr><td>Cursor</td><td>attack</td><td>String</td><td>Cursor to display when hovering over a valid target. </td></tr>
<tr><td>OutsideRangeCursor</td><td>attackoutsiderange</td><td>String</td><td>Cursor to display when hovering over a valid target that is outside of range. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### Armor
Used to define weapon efficiency modifiers with different percentages per Type.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Type</td><td></td><td>String</td><td></td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### AttackCharges
Actor must charge up its armaments before firing.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ChargeLevel</td><td>25</td><td>Integer</td><td>Amount of charge required to attack. </td></tr>
<tr><td>ChargeRate</td><td>1</td><td>Integer</td><td>Amount to increase the charge level each tick with a valid target. </td></tr>
<tr><td>DischargeRate</td><td>1</td><td>Integer</td><td>Amount to decrease the charge level each tick without a valid target. </td></tr>
<tr><td>ChargingCondition</td><td></td><td>String</td><td>The condition to grant to self while the charge level is greater than zero. </td></tr>
<tr><td>Armaments</td><td>primary, secondary</td><td>Collection of String</td><td>Armament names </td></tr>
<tr><td>Cursor</td><td></td><td>String</td><td>Cursor to display when hovering over a valid target. </td></tr>
<tr><td>OutsideRangeCursor</td><td></td><td>String</td><td>Cursor to display when hovering over a valid target that is outside of range. </td></tr>
<tr><td>TargetLineColor</td><td>DC143C</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line. </td></tr>
<tr><td>AttackRequiresEnteringCell</td><td>False</td><td>Boolean</td><td>Does the attack type require the attacker to enter the target's cell? </td></tr>
<tr><td>TargetFrozenActors</td><td>False</td><td>Boolean</td><td>Allow firing into the fog to target frozen actors without requiring force-fire. </td></tr>
<tr><td>ForceFireIgnoresActors</td><td>False</td><td>Boolean</td><td>Force-fire mode ignores actors and targets the ground instead. </td></tr>
<tr><td>OutsideRangeRequiresForceFire</td><td>False</td><td>Boolean</td><td>Force-fire mode is required to enable targeting against targets outside of range. </td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>FacingTolerance</td><td>512</td><td>1D World Angle</td><td>Tolerance for attack angle. Range [0, 512], 512 covers 360 degrees. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### AttackFollow
Actor will follow units until in range to attack them.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>OpportunityFire</td><td>True</td><td>Boolean</td><td>Automatically acquire and fire on targets of opportunity when not actively attacking. </td></tr>
<tr><td>PersistentTargeting</td><td>True</td><td>Boolean</td><td>Keep firing on targets even after attack order is cancelled </td></tr>
<tr><td>RangeMargin</td><td>1c0</td><td>1D World Distance</td><td>Range to stay away from min and max ranges to give some leeway if the target starts moving. </td></tr>
<tr><td>Armaments</td><td>primary, secondary</td><td>Collection of String</td><td>Armament names </td></tr>
<tr><td>Cursor</td><td></td><td>String</td><td>Cursor to display when hovering over a valid target. </td></tr>
<tr><td>OutsideRangeCursor</td><td></td><td>String</td><td>Cursor to display when hovering over a valid target that is outside of range. </td></tr>
<tr><td>TargetLineColor</td><td>DC143C</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line. </td></tr>
<tr><td>AttackRequiresEnteringCell</td><td>False</td><td>Boolean</td><td>Does the attack type require the attacker to enter the target's cell? </td></tr>
<tr><td>TargetFrozenActors</td><td>False</td><td>Boolean</td><td>Allow firing into the fog to target frozen actors without requiring force-fire. </td></tr>
<tr><td>ForceFireIgnoresActors</td><td>False</td><td>Boolean</td><td>Force-fire mode ignores actors and targets the ground instead. </td></tr>
<tr><td>OutsideRangeRequiresForceFire</td><td>False</td><td>Boolean</td><td>Force-fire mode is required to enable targeting against targets outside of range. </td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>FacingTolerance</td><td>512</td><td>1D World Angle</td><td>Tolerance for attack angle. Range [0, 512], 512 covers 360 degrees. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### AttackFrontal
Unit got to face the target
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>FacingTolerance</td><td>0</td><td>1D World Angle</td><td>Tolerance for attack angle. Range [0, 512], 512 covers 360 degrees. </td></tr>
<tr><td>Armaments</td><td>primary, secondary</td><td>Collection of String</td><td>Armament names </td></tr>
<tr><td>Cursor</td><td></td><td>String</td><td>Cursor to display when hovering over a valid target. </td></tr>
<tr><td>OutsideRangeCursor</td><td></td><td>String</td><td>Cursor to display when hovering over a valid target that is outside of range. </td></tr>
<tr><td>TargetLineColor</td><td>DC143C</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line. </td></tr>
<tr><td>AttackRequiresEnteringCell</td><td>False</td><td>Boolean</td><td>Does the attack type require the attacker to enter the target's cell? </td></tr>
<tr><td>TargetFrozenActors</td><td>False</td><td>Boolean</td><td>Allow firing into the fog to target frozen actors without requiring force-fire. </td></tr>
<tr><td>ForceFireIgnoresActors</td><td>False</td><td>Boolean</td><td>Force-fire mode ignores actors and targets the ground instead. </td></tr>
<tr><td>OutsideRangeRequiresForceFire</td><td>False</td><td>Boolean</td><td>Force-fire mode is required to enable targeting against targets outside of range. </td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>FacingTolerance</td><td>0</td><td>1D World Angle</td><td>Tolerance for attack angle. Range [0, 512], 512 covers 360 degrees. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### AttackGarrisoned
Cargo can fire their weapons out of fire ports.

Requires trait: [`Cargo`](#cargo).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>PortOffsets</td><td><em>(required)</em></td><td>Collection of 3D World Vector</td><td>Fire port offsets in local coordinates. </td></tr>
<tr><td>PortYaws</td><td><em>(required)</em></td><td>Collection of 1D World Angle</td><td>Fire port yaw angles. </td></tr>
<tr><td>PortCones</td><td><em>(required)</em></td><td>Collection of 1D World Angle</td><td>Fire port yaw cone angle. </td></tr>
<tr><td>MuzzlePalette</td><td>effect</td><td>String</td><td></td></tr>
<tr><td>OpportunityFire</td><td>True</td><td>Boolean</td><td>Automatically acquire and fire on targets of opportunity when not actively attacking. </td></tr>
<tr><td>PersistentTargeting</td><td>True</td><td>Boolean</td><td>Keep firing on targets even after attack order is cancelled </td></tr>
<tr><td>RangeMargin</td><td>1c0</td><td>1D World Distance</td><td>Range to stay away from min and max ranges to give some leeway if the target starts moving. </td></tr>
<tr><td>Armaments</td><td>primary, secondary</td><td>Collection of String</td><td>Armament names </td></tr>
<tr><td>Cursor</td><td></td><td>String</td><td>Cursor to display when hovering over a valid target. </td></tr>
<tr><td>OutsideRangeCursor</td><td></td><td>String</td><td>Cursor to display when hovering over a valid target that is outside of range. </td></tr>
<tr><td>TargetLineColor</td><td>DC143C</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line. </td></tr>
<tr><td>AttackRequiresEnteringCell</td><td>False</td><td>Boolean</td><td>Does the attack type require the attacker to enter the target's cell? </td></tr>
<tr><td>TargetFrozenActors</td><td>False</td><td>Boolean</td><td>Allow firing into the fog to target frozen actors without requiring force-fire. </td></tr>
<tr><td>ForceFireIgnoresActors</td><td>False</td><td>Boolean</td><td>Force-fire mode ignores actors and targets the ground instead. </td></tr>
<tr><td>OutsideRangeRequiresForceFire</td><td>False</td><td>Boolean</td><td>Force-fire mode is required to enable targeting against targets outside of range. </td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>FacingTolerance</td><td>512</td><td>1D World Angle</td><td>Tolerance for attack angle. Range [0, 512], 512 covers 360 degrees. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### AttackOmni
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Armaments</td><td>primary, secondary</td><td>Collection of String</td><td>Armament names </td></tr>
<tr><td>Cursor</td><td></td><td>String</td><td>Cursor to display when hovering over a valid target. </td></tr>
<tr><td>OutsideRangeCursor</td><td></td><td>String</td><td>Cursor to display when hovering over a valid target that is outside of range. </td></tr>
<tr><td>TargetLineColor</td><td>DC143C</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line. </td></tr>
<tr><td>AttackRequiresEnteringCell</td><td>False</td><td>Boolean</td><td>Does the attack type require the attacker to enter the target's cell? </td></tr>
<tr><td>TargetFrozenActors</td><td>False</td><td>Boolean</td><td>Allow firing into the fog to target frozen actors without requiring force-fire. </td></tr>
<tr><td>ForceFireIgnoresActors</td><td>False</td><td>Boolean</td><td>Force-fire mode ignores actors and targets the ground instead. </td></tr>
<tr><td>OutsideRangeRequiresForceFire</td><td>False</td><td>Boolean</td><td>Force-fire mode is required to enable targeting against targets outside of range. </td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>FacingTolerance</td><td>512</td><td>1D World Angle</td><td>Tolerance for attack angle. Range [0, 512], 512 covers 360 degrees. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### AttackTurreted
Actor has a visual turret used to attack.

Requires trait: [`Turreted`](#turreted).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Turrets</td><td>primary</td><td>Collection of String</td><td>Turret names </td></tr>
<tr><td>OpportunityFire</td><td>True</td><td>Boolean</td><td>Automatically acquire and fire on targets of opportunity when not actively attacking. </td></tr>
<tr><td>PersistentTargeting</td><td>True</td><td>Boolean</td><td>Keep firing on targets even after attack order is cancelled </td></tr>
<tr><td>RangeMargin</td><td>1c0</td><td>1D World Distance</td><td>Range to stay away from min and max ranges to give some leeway if the target starts moving. </td></tr>
<tr><td>Armaments</td><td>primary, secondary</td><td>Collection of String</td><td>Armament names </td></tr>
<tr><td>Cursor</td><td></td><td>String</td><td>Cursor to display when hovering over a valid target. </td></tr>
<tr><td>OutsideRangeCursor</td><td></td><td>String</td><td>Cursor to display when hovering over a valid target that is outside of range. </td></tr>
<tr><td>TargetLineColor</td><td>DC143C</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line. </td></tr>
<tr><td>AttackRequiresEnteringCell</td><td>False</td><td>Boolean</td><td>Does the attack type require the attacker to enter the target's cell? </td></tr>
<tr><td>TargetFrozenActors</td><td>False</td><td>Boolean</td><td>Allow firing into the fog to target frozen actors without requiring force-fire. </td></tr>
<tr><td>ForceFireIgnoresActors</td><td>False</td><td>Boolean</td><td>Force-fire mode ignores actors and targets the ground instead. </td></tr>
<tr><td>OutsideRangeRequiresForceFire</td><td>False</td><td>Boolean</td><td>Force-fire mode is required to enable targeting against targets outside of range. </td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>FacingTolerance</td><td>512</td><td>1D World Angle</td><td>Tolerance for attack angle. Range [0, 512], 512 covers 360 degrees. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### AttackMove
Provides access to the attack-move command, which will make the actor automatically engage viable targets while moving to the destination.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>TargetLineColor</td><td>FF4500</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line. </td></tr>
<tr><td>AttackMoveCondition</td><td></td><td>String</td><td>The condition to grant to self while an attack-move is active. </td></tr>
<tr><td>AssaultMoveCondition</td><td></td><td>String</td><td>The condition to grant to self while an assault-move is active. </td></tr>
<tr><td>MoveIntoShroud</td><td>True</td><td>Boolean</td><td>Can the actor be ordered to move in to shroud? </td></tr>
<tr><td>AttackMoveCursor</td><td>attackmove</td><td>String</td><td></td></tr>
<tr><td>AttackMoveBlockedCursor</td><td>attackmove-blocked</td><td>String</td><td></td></tr>
<tr><td>AssaultMoveCursor</td><td>assaultmove</td><td>String</td><td></td></tr>
<tr><td>AssaultMoveBlockedCursor</td><td>assaultmove-blocked</td><td>String</td><td></td></tr>
</table>

### AttackWander
Will AttackMove to a random location within MoveRadius when idle.
This conflicts with player orders and should only be added to animal creeps.

Requires trait: [`AttackMove`](#attackmove).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>WanderMoveRadius</td><td>1</td><td>Integer</td><td></td></tr>
<tr><td>ReduceMoveRadiusDelay</td><td>5</td><td>Integer</td><td>Number of ticks to wait before decreasing the effective move radius. </td></tr>
<tr><td>MinMoveDelay</td><td>0</td><td>Integer</td><td>Minimum amount of ticks the actor will sit idly before starting to wander. </td></tr>
<tr><td>MaxMoveDelay</td><td>0</td><td>Integer</td><td>Maximum amount of ticks the actor will sit idly before starting to wander. </td></tr>
<tr><td>AvoidTerrainTypes</td><td></td><td>Set of System.String[]</td><td>The terrain types that this actor should avoid wandering on to. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### AutoCarryable
Can be carried by units with the trait `Carryall`.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>MinDistance</td><td>6c0</td><td>1D World Distance</td><td>Required distance away from destination before requesting a pickup. Default is 6 cells. </td></tr>
<tr><td>ReservedCondition</td><td></td><td>String</td><td>The condition to grant to self while a carryall has been reserved. </td></tr>
<tr><td>CarriedCondition</td><td></td><td>String</td><td>The condition to grant to self while being carried. </td></tr>
<tr><td>LockedCondition</td><td></td><td>String</td><td>The condition to grant to self while being locked for carry. </td></tr>
<tr><td>LocalOffset</td><td>0,0,0</td><td>3D World Vector</td><td>Carryall attachment point relative to body. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### AutoCarryall
Automatically transports harvesters with the Carryable trait between resource fields and refineries.

Requires traits: [`Aircraft`](#aircraft), [`BodyOrientation`](#bodyorientation).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>InitialActor</td><td></td><td>String</td><td>Actor type that is initially spawned into this actor. </td></tr>
<tr><td>BeforeLoadDelay</td><td>0</td><td>Integer</td><td>Delay (in ticks) on the ground while attaching an actor to the carryall. </td></tr>
<tr><td>BeforeUnloadDelay</td><td>0</td><td>Integer</td><td>Delay (in ticks) on the ground while detaching an actor from the carryall. </td></tr>
<tr><td>LocalOffset</td><td>0,0,0</td><td>3D World Vector</td><td>Carryable attachment point relative to body. </td></tr>
<tr><td>DropRange</td><td>5c0</td><td>1D World Distance</td><td>Radius around the target drop location that are considered if the target tile is blocked. </td></tr>
<tr><td>UnloadCursor</td><td>deploy</td><td>String</td><td>Cursor to display when able to unload the passengers. </td></tr>
<tr><td>UnloadBlockedCursor</td><td>deploy-blocked</td><td>String</td><td>Cursor to display when unable to unload the passengers. </td></tr>
<tr><td>AllowDropOff</td><td>False</td><td>Boolean</td><td>Allow moving and unloading with one order using force-move </td></tr>
<tr><td>DropOffCursor</td><td>ability</td><td>String</td><td>Cursor to display when able to drop off the passengers at location. </td></tr>
<tr><td>DropOffBlockedCursor</td><td>move-blocked</td><td>String</td><td>Cursor to display when unable to drop off the passengers at location. </td></tr>
<tr><td>PickUpCursor</td><td>ability</td><td>String</td><td>Cursor to display when picking up the passengers. </td></tr>
<tr><td>CarryCondition</td><td></td><td>String</td><td>Condition to grant to the Carryall while it is carrying something. </td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>TargetLineColor</td><td>FFFF00</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line. </td></tr>
</table>

### AutoTarget
The actor will automatically engage the enemy when it is in range.

Requires trait: [`AttackBase`](#attackbase).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>AllowMovement</td><td>True</td><td>Boolean</td><td>It will try to hunt down the enemy if it is set to AttackAnything. </td></tr>
<tr><td>AllowTurning</td><td>True</td><td>Boolean</td><td>It will try to pivot to face the enemy if stance is not HoldFire. </td></tr>
<tr><td>ScanOnIdle</td><td>True</td><td>Boolean</td><td>Scan for new targets when idle. </td></tr>
<tr><td>ScanRadius</td><td>-1</td><td>Integer</td><td>Set to a value >1 to override weapons maximum range for this. </td></tr>
<tr><td>InitialStanceAI</td><td>AttackAnything</td><td>UnitStance</td><td>Possible values are HoldFire, ReturnFire, Defend and AttackAnything. Used for computer-controlled players, both Lua-scripted and regular Skirmish AI alike. </td></tr>
<tr><td>InitialStance</td><td>Defend</td><td>UnitStance</td><td>Possible values are HoldFire, ReturnFire, Defend and AttackAnything. Used for human players. </td></tr>
<tr><td>HoldFireCondition</td><td></td><td>String</td><td>The condition to grant to self while in the HoldFire stance. </td></tr>
<tr><td>ReturnFireCondition</td><td></td><td>String</td><td>The condition to grant to self while in the ReturnFire stance. </td></tr>
<tr><td>DefendCondition</td><td></td><td>String</td><td>The condition to grant to self while in the Defend stance. </td></tr>
<tr><td>AttackAnythingCondition</td><td></td><td>String</td><td>The condition to grant to self while in the AttackAnything stance. </td></tr>
<tr><td>EnableStances</td><td>True</td><td>Boolean</td><td>Allow the player to change the unit stance. </td></tr>
<tr><td>MinimumScanTimeInterval</td><td>3</td><td>Integer</td><td>Ticks to wait until next AutoTarget: attempt. </td></tr>
<tr><td>MaximumScanTimeInterval</td><td>8</td><td>Integer</td><td>Ticks to wait until next AutoTarget: attempt. </td></tr>
<tr><td>EditorStanceDisplayOrder</td><td>1</td><td>Integer</td><td>Display order for the stance dropdown in the map editor </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### AutoTargetPriority
Specifies the target types and relative priority used by AutoTarget to decide what to target.

Requires trait: [`AutoTarget`](#autotarget).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ValidTargets</td><td>Ground, Water, Air</td><td>Collection of TargetableType</td><td>Target types that can be AutoTargeted. </td></tr>
<tr><td>InvalidTargets</td><td></td><td>Collection of TargetableType</td><td>Target types that can't be AutoTargeted. Overrules ValidTargets. </td></tr>
<tr><td>ValidRelationships</td><td>Enemy, Neutral, Ally</td><td>PlayerRelationship</td><td>Relationships between actor's and target's owner needed for AutoTargeting. </td></tr>
<tr><td>Priority</td><td>1</td><td>Integer</td><td>ValidTargets with larger priorities will be AutoTargeted before lower priorities. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### BlocksProjectiles
This actor blocks bullets and missiles with 'Blockable' property.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Height</td><td>1c0</td><td>1D World Distance</td><td></td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### BodyOrientation
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>QuantizedFacings</td><td>-1</td><td>Integer</td><td>Number of facings for gameplay calculations. -1 indicates auto-detection from another trait. </td></tr>
<tr><td>CameraPitch</td><td>113</td><td>1D World Angle</td><td>Camera pitch for rotation calculations. </td></tr>
<tr><td>UseClassicPerspectiveFudge</td><td>True</td><td>Boolean</td><td>Fudge the coordinate system angles to simulate non-top-down perspective in mods with square cells. </td></tr>
</table>

### BaseBuilderBotModule
Manages AI base construction.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ConstructionYardTypes</td><td></td><td>Set of System.String[]</td><td>Tells the AI what building types are considered construction yards. </td></tr>
<tr><td>VehiclesFactoryTypes</td><td></td><td>Set of System.String[]</td><td>Tells the AI what building types are considered vehicle production facilities. </td></tr>
<tr><td>RefineryTypes</td><td></td><td>Set of System.String[]</td><td>Tells the AI what building types are considered refineries. </td></tr>
<tr><td>PowerTypes</td><td></td><td>Set of System.String[]</td><td>Tells the AI what building types are considered power plants. </td></tr>
<tr><td>BarracksTypes</td><td></td><td>Set of System.String[]</td><td>Tells the AI what building types are considered infantry production facilities. </td></tr>
<tr><td>ProductionTypes</td><td></td><td>Set of System.String[]</td><td>Tells the AI what building types are considered production facilities. </td></tr>
<tr><td>NavalProductionTypes</td><td></td><td>Set of System.String[]</td><td>Tells the AI what building types are considered naval production facilities. </td></tr>
<tr><td>SiloTypes</td><td></td><td>Set of System.String[]</td><td>Tells the AI what building types are considered silos (resource storage). </td></tr>
<tr><td>BuildingQueues</td><td>Building</td><td>Set of System.String[]</td><td>Production queues AI uses for buildings. </td></tr>
<tr><td>DefenseQueues</td><td>Defense</td><td>Set of System.String[]</td><td>Production queues AI uses for defenses. </td></tr>
<tr><td>MinBaseRadius</td><td>2</td><td>Integer</td><td>Minimum distance in cells from center of the base when checking for building placement. </td></tr>
<tr><td>MaxBaseRadius</td><td>20</td><td>Integer</td><td>Radius in cells around the center of the base to expand. </td></tr>
<tr><td>MinimumExcessPower</td><td>0</td><td>Integer</td><td>Minimum excess power the AI should try to maintain. </td></tr>
<tr><td>MaximumExcessPower</td><td>0</td><td>Integer</td><td>The targeted excess power the AI tries to maintain cannot rise above this. </td></tr>
<tr><td>ExcessPowerIncrement</td><td>0</td><td>Integer</td><td>Increase maintained excess power by this amount for every ExcessPowerIncreaseThreshold of base buildings. </td></tr>
<tr><td>ExcessPowerIncreaseThreshold</td><td>1</td><td>Integer</td><td>Increase maintained excess power by ExcessPowerIncrement for every N base buildings. </td></tr>
<tr><td>InititalMinimumRefineryCount</td><td>1</td><td>Integer</td><td>Number of refineries to build before building a barracks. </td></tr>
<tr><td>AdditionalMinimumRefineryCount</td><td>1</td><td>Integer</td><td>Number of refineries to build additionally after building a barracks. </td></tr>
<tr><td>StructureProductionInactiveDelay</td><td>125</td><td>Integer</td><td>Additional delay (in ticks) between structure production checks when there is no active production. StructureProductionRandomBonusDelay is added to this. </td></tr>
<tr><td>StructureProductionActiveDelay</td><td>0</td><td>Integer</td><td>Additional delay (in ticks) added between structure production checks when actively building things. Note: The total delay is gamespeed OrderLatency x 4 + this + StructureProductionRandomBonusDelay. </td></tr>
<tr><td>StructureProductionRandomBonusDelay</td><td>10</td><td>Integer</td><td>A random delay (in ticks) of up to this is added to active/inactive production delays. </td></tr>
<tr><td>StructureProductionResumeDelay</td><td>1500</td><td>Integer</td><td>Delay (in ticks) until retrying to build structure after the last 3 consecutive attempts failed. </td></tr>
<tr><td>MaximumFailedPlacementAttempts</td><td>3</td><td>Integer</td><td>After how many failed attempts to place a structure should AI give up and wait for StructureProductionResumeDelay before retrying. </td></tr>
<tr><td>MaxResourceCellsToCheck</td><td>3</td><td>Integer</td><td>How many randomly chosen cells with resources to check when deciding refinery placement. </td></tr>
<tr><td>CheckForNewBasesDelay</td><td>1500</td><td>Integer</td><td>Delay (in ticks) until rechecking for new BaseProviders. </td></tr>
<tr><td>PlaceDefenseTowardsEnemyChance</td><td>100</td><td>Integer</td><td>Chance that the AI will place the defenses in the direction of the closest enemy building. </td></tr>
<tr><td>MinimumDefenseRadius</td><td>5</td><td>Integer</td><td>Minimum range at which to build defensive structures near a combat hotspot. </td></tr>
<tr><td>MaximumDefenseRadius</td><td>20</td><td>Integer</td><td>Maximum range at which to build defensive structures near a combat hotspot. </td></tr>
<tr><td>NewProductionCashThreshold</td><td>5000</td><td>Integer</td><td>Try to build another production building if there is too much cash. </td></tr>
<tr><td>RallyPointScanRadius</td><td>8</td><td>Integer</td><td>Radius in cells around a factory scanned for rally points by the AI. </td></tr>
<tr><td>CheckForWaterRadius</td><td>8</td><td>Integer</td><td>Radius in cells around each building with ProvideBuildableArea to check for a 3x3 area of water where naval structures can be built. Should match maximum adjacency of naval structures. </td></tr>
<tr><td>WaterTerrainTypes</td><td>Water</td><td>Set of System.String[]</td><td>Terrain types which are considered water for base building purposes. </td></tr>
<tr><td>BuildingFractions</td><td></td><td>Dictionary with Key: String, Value Integer</td><td>What buildings to the AI should build. What integer percentage of the total base must be this type of building. </td></tr>
<tr><td>BuildingLimits</td><td></td><td>Dictionary with Key: String, Value Integer</td><td>What buildings should the AI have a maximum limit to build. </td></tr>
<tr><td>BuildingDelays</td><td></td><td>Dictionary with Key: String, Value Integer</td><td>When should the AI start building specific buildings. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### BuildingRepairBotModule
Manages AI repairing base buildings.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### CaptureManagerBotModule
Manages AI capturing logic.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>CapturingActorTypes</td><td></td><td>Set of System.String[]</td><td>Actor types that can capture other actors (via `Captures`). Leave this empty to disable capturing. </td></tr>
<tr><td>CapturableActorTypes</td><td></td><td>Set of System.String[]</td><td>Actor types that can be targeted for capturing. Leave this empty to include all actors. </td></tr>
<tr><td>MinimumCaptureDelay</td><td>375</td><td>Integer</td><td>Minimum delay (in ticks) between trying to capture with CapturingActorTypes. </td></tr>
<tr><td>MaximumCaptureTargetOptions</td><td>10</td><td>Integer</td><td>Maximum number of options to consider for capturing. If a value less than 1 is given 1 will be used instead. </td></tr>
<tr><td>CheckCaptureTargetsForVisibility</td><td>True</td><td>Boolean</td><td>Should visibility (Shroud, Fog, Cloak, etc) be considered when searching for capturable targets? </td></tr>
<tr><td>CapturableRelationships</td><td>Enemy, Neutral</td><td>PlayerRelationship</td><td>Player relationships that capturers should attempt to target. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### HarvesterBotModule
Put this on the Player actor. Manages bot harvesters to ensure they always continue harvesting as long as there are resources on the map.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>HarvesterTypes</td><td></td><td>Set of System.String[]</td><td>Actor types that are considered harvesters. If harvester count drops below RefineryTypes count, a new harvester is built. Leave empty to disable harvester replacement. Currently only needed by harvester replacement system. </td></tr>
<tr><td>RefineryTypes</td><td></td><td>Set of System.String[]</td><td>Actor types that are counted as refineries. Currently only needed by harvester replacement system. </td></tr>
<tr><td>ScanForIdleHarvestersInterval</td><td>50</td><td>Integer</td><td>Interval (in ticks) between giving out orders to idle harvesters. </td></tr>
<tr><td>HarvesterEnemyAvoidanceRadius</td><td>8c0</td><td>1D World Distance</td><td>Avoid enemy actors nearby when searching for a new resource patch. Should be somewhere near the max weapon range. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### McvManagerBotModule
Manages AI MCVs.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>McvTypes</td><td></td><td>Set of System.String[]</td><td>Actor types that are considered MCVs (deploy into base builders). </td></tr>
<tr><td>ConstructionYardTypes</td><td></td><td>Set of System.String[]</td><td>Actor types that are considered construction yards (base builders). </td></tr>
<tr><td>McvFactoryTypes</td><td></td><td>Set of System.String[]</td><td>Actor types that are able to produce MCVs. </td></tr>
<tr><td>MinimumConstructionYardCount</td><td>1</td><td>Integer</td><td>Try to maintain at least this many ConstructionYardTypes, build an MCV if number is below this. </td></tr>
<tr><td>ScanForNewMcvInterval</td><td>20</td><td>Integer</td><td>Delay (in ticks) between looking for and giving out orders to new MCVs. </td></tr>
<tr><td>MinBaseRadius</td><td>2</td><td>Integer</td><td>Minimum distance in cells from center of the base when checking for MCV deployment location. </td></tr>
<tr><td>MaxBaseRadius</td><td>20</td><td>Integer</td><td>Maximum distance in cells from center of the base when checking for MCV deployment location. Only applies if RestrictMCVDeploymentFallbackToBase is enabled and there's at least one construction yard. </td></tr>
<tr><td>RestrictMCVDeploymentFallbackToBase</td><td>True</td><td>Boolean</td><td>Should deployment of additional MCVs be restricted to MaxBaseRadius if explicit deploy locations are missing or occupied? </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### SquadManagerBotModule
Manages AI squads.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>NavalUnitsTypes</td><td></td><td>Set of System.String[]</td><td>Actor types that are valid for naval squads. </td></tr>
<tr><td>ExcludeFromSquadsTypes</td><td></td><td>Set of System.String[]</td><td>Actor types that should generally be excluded from attack squads. </td></tr>
<tr><td>ConstructionYardTypes</td><td></td><td>Set of System.String[]</td><td>Actor types that are considered construction yards (base builders). </td></tr>
<tr><td>NavalProductionTypes</td><td></td><td>Set of System.String[]</td><td>Enemy building types around which to scan for targets for naval squads. </td></tr>
<tr><td>SquadSize</td><td>8</td><td>Integer</td><td>Minimum number of units AI must have before attacking. </td></tr>
<tr><td>SquadSizeRandomBonus</td><td>30</td><td>Integer</td><td>Random number of up to this many units is added to squad size when creating an attack squad. </td></tr>
<tr><td>AssignRolesInterval</td><td>50</td><td>Integer</td><td>Delay (in ticks) between giving out orders to units. </td></tr>
<tr><td>RushInterval</td><td>600</td><td>Integer</td><td>Delay (in ticks) between attempting rush attacks. </td></tr>
<tr><td>AttackForceInterval</td><td>75</td><td>Integer</td><td>Delay (in ticks) between updating squads. </td></tr>
<tr><td>MinimumAttackForceDelay</td><td>0</td><td>Integer</td><td>Minimum delay (in ticks) between creating squads. </td></tr>
<tr><td>RushAttackScanRadius</td><td>15</td><td>Integer</td><td>Radius in cells around enemy BaseBuilder (Construction Yard) where AI scans for targets to rush. </td></tr>
<tr><td>ProtectUnitScanRadius</td><td>15</td><td>Integer</td><td>Radius in cells around the base that should be scanned for units to be protected. </td></tr>
<tr><td>MaxBaseRadius</td><td>20</td><td>Integer</td><td>Maximum distance in cells from center of the base when checking for MCV deployment location. Only applies if RestrictMCVDeploymentFallbackToBase is enabled and there's at least one construction yard. </td></tr>
<tr><td>IdleScanRadius</td><td>10</td><td>Integer</td><td>Radius in cells that squads should scan for enemies around their position while idle. </td></tr>
<tr><td>DangerScanRadius</td><td>10</td><td>Integer</td><td>Radius in cells that squads should scan for danger around their position to make flee decisions. </td></tr>
<tr><td>AttackScanRadius</td><td>12</td><td>Integer</td><td>Radius in cells that attack squads should scan for enemies around their position when trying to attack. </td></tr>
<tr><td>ProtectionScanRadius</td><td>8</td><td>Integer</td><td>Radius in cells that protecting squads should scan for enemies around their position. </td></tr>
<tr><td>IgnoredEnemyTargetTypes</td><td></td><td>Collection of TargetableType</td><td>Enemy target types to never target. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### SupportPowerBotModule
Manages bot support power handling.

Requires trait: [`SupportPowerManager`](#supportpowermanager).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Decisions</td><td></td><td>Collection of SupportPowerDecision</td><td>Tells the AI how to use its support powers. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### UnitBuilderBotModule
Controls AI unit production.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>IdleBaseUnitsMaximum</td><td>12</td><td>Integer</td><td>Only produce units as long as there are less than this amount of units idling inside the base. </td></tr>
<tr><td>UnitQueues</td><td>Vehicle, Infantry, Plane, Ship, Aircraft</td><td>Set of System.String[]</td><td>Production queues AI uses for producing units. </td></tr>
<tr><td>UnitsToBuild</td><td></td><td>Dictionary with Key: String, Value Integer</td><td>What units to the AI should build. What relative share of the total army must be this type of unit. </td></tr>
<tr><td>UnitLimits</td><td></td><td>Dictionary with Key: String, Value Integer</td><td>What units should the AI have a maximum limit to train. </td></tr>
<tr><td>UnitDelays</td><td></td><td>Dictionary with Key: String, Value Integer</td><td>When should the AI start train specific units. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### Buildable
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Prerequisites</td><td></td><td>Collection of String</td><td>The prerequisite names that must be available before this can be built. This can be prefixed with ! to invert the prerequisite (disabling production if the prerequisite is available) and/or ~ to hide the actor from the production palette if the prerequisite is not available. Prerequisites are granted by actors with the ProvidesPrerequisite trait. </td></tr>
<tr><td>Queue</td><td></td><td>Set of System.String[]</td><td>Production queue(s) that can produce this. </td></tr>
<tr><td>BuildAtProductionType</td><td></td><td>String</td><td>Override the production structure type (from the Production Produces list) that this unit should be built at. </td></tr>
<tr><td>BuildLimit</td><td>0</td><td>Integer</td><td>Disable production when there are more than this many of this actor on the battlefield. Set to 0 to disable. </td></tr>
<tr><td>ForceFaction</td><td></td><td>String</td><td>Force a specific faction variant, overriding the faction of the producing actor. </td></tr>
<tr><td>Icon</td><td>icon</td><td>String</td><td>Sequence of the actor that contains the icon. </td></tr>
<tr><td>IconPalette</td><td>chrome</td><td>String</td><td>Palette used for the production icon. </td></tr>
<tr><td>IconPaletteIsPlayerPalette</td><td>False</td><td>Boolean</td><td>Custom palette is a player palette BaseName </td></tr>
<tr><td>BuildDuration</td><td>-1</td><td>Integer</td><td>Base build time in frames (-1 indicates to use the unit's Value). </td></tr>
<tr><td>BuildDurationModifier</td><td>60</td><td>Integer</td><td>Percentage modifier to apply to the build duration. </td></tr>
<tr><td>BuildPaletteOrder</td><td>9999</td><td>Integer</td><td>Sort order for the production palette. Smaller numbers are presented earlier. </td></tr>
<tr><td>Description</td><td></td><td>String</td><td>Text shown in the production tooltip. </td></tr>
</table>

### ActorPreviewPlaceBuildingPreview
Creates a building placement preview based on the map editor actor preview.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Animated</td><td>True</td><td>Boolean</td><td>Enable the building's idle animation. </td></tr>
<tr><td>PreviewAlpha</td><td>1</td><td>Real Number</td><td>Custom opacity to apply to the actor preview. </td></tr>
<tr><td>FootprintUnderPreview</td><td>Valid, LineBuild</td><td>PlaceBuildingCellType</td><td>Footprint types to draw underneath the actor preview. </td></tr>
<tr><td>FootprintOverPreview</td><td>Invalid</td><td>PlaceBuildingCellType</td><td>Footprint types to draw above the actor preview. </td></tr>
<tr><td>Palette</td><td>terrain</td><td>String</td><td>Palette to use for rendering the placement sprite. </td></tr>
<tr><td>FootprintAlpha</td><td>1</td><td>Real Number</td><td>Custom opacity to apply to the placement sprite. </td></tr>
<tr><td>LineBuildFootprintAlpha</td><td>1</td><td>Real Number</td><td>Custom opacity to apply to the line-build placement sprite. </td></tr>
</table>

### BaseBuilding
Tag trait for construction yard and MCVs. Used by the cycle bases hotkey to identify actors.

### BaseProvider
Limits the zone where buildings can be constructed to a radius around this actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Range</td><td>10c0</td><td>1D World Distance</td><td></td></tr>
<tr><td>Cooldown</td><td>0</td><td>Integer</td><td></td></tr>
<tr><td>InitialDelay</td><td>0</td><td>Integer</td><td></td></tr>
<tr><td>CircleReadyColor</td><td>FFFFFF80</td><td>Color (RRGGBB[AA] notation)</td><td>Range circle color when operational. </td></tr>
<tr><td>CircleBlockedColor</td><td>FF000080</td><td>Color (RRGGBB[AA] notation)</td><td>Range circle color when inactive. </td></tr>
<tr><td>CircleWidth</td><td>1</td><td>Real Number</td><td>Range circle line width. </td></tr>
<tr><td>CircleBorderColor</td><td>00000060</td><td>Color (RRGGBB[AA] notation)</td><td>Range circle border color. </td></tr>
<tr><td>CircleBorderWidth</td><td>3</td><td>Real Number</td><td>Range circle border width. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### Bridge
Requires traits: [`Building`](#building), [`Health`](#health).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Long</td><td>False</td><td>Boolean</td><td></td></tr>
<tr><td>RepairPropagationDelay</td><td>20</td><td>Integer</td><td>Delay (in ticks) between repairing adjacent spans in long bridges </td></tr>
<tr><td>Template</td><td>0</td><td>UInt16</td><td></td></tr>
<tr><td>DamagedTemplate</td><td>0</td><td>UInt16</td><td></td></tr>
<tr><td>DestroyedTemplate</td><td>0</td><td>UInt16</td><td></td></tr>
<tr><td>DestroyedPlusNorthTemplate</td><td>0</td><td>UInt16</td><td></td></tr>
<tr><td>DestroyedPlusSouthTemplate</td><td>0</td><td>UInt16</td><td></td></tr>
<tr><td>DestroyedPlusBothTemplate</td><td>0</td><td>UInt16</td><td></td></tr>
<tr><td>ShorePieces</td><td>br1, br2</td><td>Collection of String</td><td></td></tr>
<tr><td>NorthOffset</td><td></td><td>Collection of Integer</td><td></td></tr>
<tr><td>SouthOffset</td><td></td><td>Collection of Integer</td><td></td></tr>
<tr><td>DemolishWeapon</td><td>Demolish</td><td>String</td><td>The name of the weapon to use when demolishing the bridge </td></tr>
<tr><td>DamageTypes</td><td></td><td>Collection of DamageType</td><td>Types of damage that this bridge causes to units over/in path of it while being destroyed/repaired. Leave empty for no damage types. </td></tr>
</table>

### BridgeHut
Allows bridges to be targeted for demolition and repair.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Types</td><td>GroundLevelBridge</td><td>Collection of String</td><td>Bridge types to act on </td></tr>
<tr><td>NeighbourOffsets</td><td></td><td>Collection of 2D Cell Vector</td><td>Offsets to look for adjacent bridges to act on </td></tr>
<tr><td>RepairPropagationDelay</td><td>20</td><td>Integer</td><td>Delay between each segment repair step </td></tr>
<tr><td>DemolishPropagationDelay</td><td>5</td><td>Integer</td><td>Delay between each segment demolish step </td></tr>
<tr><td>RequireForceAttackForHeal</td><td>False</td><td>Boolean</td><td>Hide the repair cursor if the bridge is only damaged (not destroyed) </td></tr>
</table>

### BridgePlaceholder
Placeholder actor used for dead segments and bridge end ramps.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Type</td><td>GroundLevelBridge</td><td>String</td><td></td></tr>
<tr><td>DamageState</td><td>Undamaged</td><td>DamageState</td><td></td></tr>
<tr><td>ReplaceWithActor</td><td></td><td>String</td><td>Actor type to replace with on repair. </td></tr>
<tr><td>NeighbourOffsets</td><td></td><td>Collection of 2D Cell Vector</td><td></td></tr>
</table>

### Building
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>TerrainTypes</td><td></td><td>Set of System.String[]</td><td>Where you are allowed to place the building (Water, Clear, ...) </td></tr>
<tr><td>Footprint</td><td></td><td>Dictionary with Key: 2D Cell Vector, Value FootprintCellType</td><td>x means cell is blocked, capital X means blocked but not counting as targetable,  = means part of the footprint but passable, _ means completely empty. </td></tr>
<tr><td>Dimensions</td><td>1,1</td><td>2D Cell Vector</td><td></td></tr>
<tr><td>LocalCenterOffset</td><td>0,0,0</td><td>3D World Vector</td><td>Shift center of the actor by this offset. </td></tr>
<tr><td>RequiresBaseProvider</td><td>False</td><td>Boolean</td><td></td></tr>
<tr><td>AllowInvalidPlacement</td><td>False</td><td>Boolean</td><td></td></tr>
<tr><td>AllowPlacementOnResources</td><td>False</td><td>Boolean</td><td></td></tr>
<tr><td>RemoveSmudgesOnBuild</td><td>True</td><td>Boolean</td><td>Clear smudges from underneath the building footprint. </td></tr>
<tr><td>RemoveSmudgesOnSell</td><td>True</td><td>Boolean</td><td>Clear smudges from underneath the building footprint on sell. </td></tr>
<tr><td>RemoveSmudgesOnTransform</td><td>True</td><td>Boolean</td><td>Clear smudges from underneath the building footprint on transform. </td></tr>
<tr><td>BuildSounds</td><td></td><td>Collection of String</td><td></td></tr>
<tr><td>UndeploySounds</td><td></td><td>Collection of String</td><td></td></tr>
</table>

### BuildingInfluence
A dictionary of buildings placed on the map. Attach this to the world actor.

### Exit
Where the unit should leave the building. Multiples are allowed if IDs are added: Exit@2, ...
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>SpawnOffset</td><td>0,0,0</td><td>3D World Vector</td><td>Offset at which that the exiting actor is spawned relative to the center of the producing actor. </td></tr>
<tr><td>ExitCell</td><td>0,0</td><td>2D Cell Vector</td><td>Cell offset where the exiting actor enters the ActorMap relative to the topleft cell of the producing actor. </td></tr>
<tr><td>Facing</td><td></td><td>1D World Angle (optional)</td><td></td></tr>
<tr><td>ProductionTypes</td><td></td><td>Set of System.String[]</td><td>Type tags on this exit. </td></tr>
<tr><td>ExitDelay</td><td>0</td><td>Integer</td><td>Number of ticks to wait before moving into the world. </td></tr>
<tr><td>Priority</td><td>1</td><td>Integer</td><td>Exits with larger priorities will be used before lower priorities. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### FootprintPlaceBuildingPreview
Creates a building placement preview showing only the building footprint.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Palette</td><td>terrain</td><td>String</td><td>Palette to use for rendering the placement sprite. </td></tr>
<tr><td>FootprintAlpha</td><td>1</td><td>Real Number</td><td>Custom opacity to apply to the placement sprite. </td></tr>
<tr><td>LineBuildFootprintAlpha</td><td>1</td><td>Real Number</td><td>Custom opacity to apply to the line-build placement sprite. </td></tr>
</table>

### FreeActor
Player receives a unit for free once the building is placed. This also works for structures.
If you want more than one unit to appear copy this section and assign IDs like FreeActor@2, ...
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Actor</td><td><em>(required)</em></td><td>String</td><td>Name of the actor. </td></tr>
<tr><td>SpawnOffset</td><td>0,0</td><td>2D Cell Vector</td><td>Offset relative to the top-left cell of the building. </td></tr>
<tr><td>Facing</td><td>0</td><td>1D World Angle</td><td>Which direction the unit should face. </td></tr>
<tr><td>AllowRespawn</td><td>False</td><td>Boolean</td><td>Whether another actor should spawn upon re-enabling the trait. </td></tr>
<tr><td>EditorFreeActorDisplayOrder</td><td>4</td><td>Integer</td><td>Display order for the free actor checkbox in the map editor </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### FreeActorWithDelivery
Player receives a unit for free once the building is placed.
If you want more than one unit to be delivered, copy this section and assign IDs like FreeActorWithDelivery@2, ...
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>DeliveringActor</td><td><em>(required)</em></td><td>String</td><td>Name of the delivering actor. This actor must have the `Carryall` trait </td></tr>
<tr><td>SpawnLocation</td><td>0,0</td><td>2D Cell Position</td><td>Cell coordinates for spawning the delivering actor. If left blank, the closest edge cell will be chosen. </td></tr>
<tr><td>DeliveryOffset</td><td>0,0</td><td>2D Cell Vector</td><td>Offset relative to the top-left cell of the building. </td></tr>
<tr><td>DeliveryRange</td><td>0c0</td><td>1D World Distance</td><td>Range to search for an alternative delivery location if the DeliveryOffset cell is blocked. </td></tr>
<tr><td>Actor</td><td><em>(required)</em></td><td>String</td><td>Name of the actor. </td></tr>
<tr><td>SpawnOffset</td><td>0,0</td><td>2D Cell Vector</td><td>Offset relative to the top-left cell of the building. </td></tr>
<tr><td>Facing</td><td>0</td><td>1D World Angle</td><td>Which direction the unit should face. </td></tr>
<tr><td>AllowRespawn</td><td>False</td><td>Boolean</td><td>Whether another actor should spawn upon re-enabling the trait. </td></tr>
<tr><td>EditorFreeActorDisplayOrder</td><td>4</td><td>Integer</td><td>Display order for the free actor checkbox in the map editor </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### Gate
Will open and be passable for actors that appear friendly when there are no enemies in range.

Requires trait: [`Building`](#building).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>OpeningSound</td><td></td><td>String</td><td></td></tr>
<tr><td>ClosingSound</td><td></td><td>String</td><td></td></tr>
<tr><td>CloseDelay</td><td>150</td><td>Integer</td><td>Ticks until the gate closes. </td></tr>
<tr><td>TransitionDelay</td><td>33</td><td>Integer</td><td>Ticks until the gate is considered open. </td></tr>
<tr><td>BlocksProjectilesHeight</td><td>0c640</td><td>1D World Distance</td><td>Blocks bullets scaled to open value. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### GivesBuildableArea
This actor allows placement of other actors with 'RequiresBuildableArea' trait around it.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>AreaTypes</td><td><em>(required)</em></td><td>Set of System.String[]</td><td>Types of buildable area this actor gives. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### GroundLevelBridge
Bridge actor that can't be passed underneath.

Requires trait: [`Building`](#building).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>TerrainType</td><td>Bridge</td><td>String</td><td></td></tr>
<tr><td>Type</td><td>GroundLevelBridge</td><td>String</td><td></td></tr>
<tr><td>NeighbourOffsets</td><td></td><td>Collection of 2D Cell Vector</td><td></td></tr>
<tr><td>DemolishWeapon</td><td>Demolish</td><td>String</td><td>The name of the weapon to use when demolishing the bridge </td></tr>
<tr><td>DamageTypes</td><td></td><td>Collection of DamageType</td><td>Types of damage that this bridge causes to units over/in path of it while being destroyed/repaired. Leave empty for no damage types. </td></tr>
</table>

### LegacyBridgeHut
Allows bridges to be targeted for demolition and repair.

### LineBuild
Place the second actor in line to build more of the same at once (used for walls).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Range</td><td>5</td><td>Integer</td><td>The maximum allowed length of the line. </td></tr>
<tr><td>NodeTypes</td><td>wall</td><td>Set of System.String[]</td><td>LineBuildNode 'Types' to attach to. </td></tr>
<tr><td>SegmentType</td><td></td><td>String</td><td>Actor type for line-built segments (defaults to same actor). </td></tr>
<tr><td>SegmentsRequireNode</td><td>False</td><td>Boolean</td><td>Delete generated segments when destroyed or sold. </td></tr>
</table>

### LineBuildNode
LineBuild actors attach to LineBuildNodes.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Types</td><td>wall</td><td>Set of System.String[]</td><td>This actor is of LineBuild 'NodeType'... </td></tr>
<tr><td>Connections</td><td>1,0, 0,1, -1,0, 0,-1</td><td>Collection of 2D Cell Vector</td><td>Cells (outside the footprint) that contain cells that can connect to this actor. </td></tr>
</table>

### PlaceBuildingVariants
Place a different building when PlaceBuilding's ToggleVariantKey hotkey is pressed while the PlaceBuildingOrderGenerator is active.

Requires traits: [`Buildable`](#buildable), [`Building`](#building).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Actors</td><td><em>(required)</em></td><td>Collection of String</td><td>Variant actors that can be cycled between when placing a structure. </td></tr>
</table>

### PrimaryBuilding
Used together with ClassicProductionQueue.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>PrimaryCondition</td><td></td><td>String</td><td>The condition to grant to self while this is the primary building. </td></tr>
<tr><td>SelectionNotification</td><td></td><td>String</td><td>The speech notification to play when selecting a primary building. </td></tr>
<tr><td>ProductionQueues</td><td></td><td>Collection of String</td><td>List of production queues for which the primary flag should be set. If empty, the list given in the `Produces` property of the `Production` trait will be used. </td></tr>
<tr><td>Cursor</td><td>deploy</td><td>String</td><td>Cursor to display when setting the primary building. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ProductionAirdrop
Deliver the unit in production via skylift.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ReadyAudio</td><td>Reinforce</td><td>String</td><td></td></tr>
<tr><td>ActorType</td><td><em>(required)</em></td><td>String</td><td>Cargo aircraft used for delivery. Must have the `Aircraft` trait. </td></tr>
<tr><td>BaselineSpawn</td><td>False</td><td>Boolean</td><td>The cargo aircraft will spawn at the player baseline (map edge closest to the player spawn) </td></tr>
<tr><td>Facing</td><td>256</td><td>1D World Angle</td><td>Direction the aircraft should face to land. </td></tr>
<tr><td>Produces</td><td><em>(required)</em></td><td>Collection of String</td><td>e.g. Infantry, Vehicles, Aircraft, Buildings </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### RallyPoint
Used to waypoint units after production or repair is finished.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Image</td><td>rallypoint</td><td>String</td><td></td></tr>
<tr><td>LineWidth</td><td>1</td><td>Integer</td><td>Width (in pixels) of the rallypoint line. </td></tr>
<tr><td>FlagSequence</td><td>flag</td><td>String</td><td></td></tr>
<tr><td>CirclesSequence</td><td>circles</td><td>String</td><td></td></tr>
<tr><td>Cursor</td><td>ability</td><td>String</td><td>Cursor to display when rally point can be set. </td></tr>
<tr><td>Palette</td><td>player</td><td>String</td><td>Custom indicator palette name </td></tr>
<tr><td>IsPlayerPalette</td><td>True</td><td>Boolean</td><td>Custom palette is a player palette BaseName </td></tr>
<tr><td>Path</td><td></td><td>Collection of 2D Cell Vector</td><td>A list of 0 or more offsets defining the initial rally point path. </td></tr>
<tr><td>Notification</td><td></td><td>String</td><td>The speech notification to play when setting a new rallypoint. </td></tr>
</table>

### Refinery
Requires trait: [`WithSpriteBody`](#withspritebody).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>DockAngle</td><td>0</td><td>1D World Angle</td><td>Actual harvester facing when docking. </td></tr>
<tr><td>DockOffset</td><td>0,0</td><td>2D Cell Vector</td><td>Docking cell relative to top-left cell. </td></tr>
<tr><td>IsDragRequired</td><td>False</td><td>Boolean</td><td>Does the refinery require the harvester to be dragged in? </td></tr>
<tr><td>DragOffset</td><td>0,0,0</td><td>3D World Vector</td><td>Vector by which the harvester will be dragged when docking. </td></tr>
<tr><td>DragLength</td><td>0</td><td>Integer</td><td>In how many steps to perform the dragging? </td></tr>
<tr><td>UseStorage</td><td>True</td><td>Boolean</td><td>Store resources in silos. Adds cash directly without storing if set to false. </td></tr>
<tr><td>DiscardExcessResources</td><td>False</td><td>Boolean</td><td>Discard resources once silo capacity has been reached. </td></tr>
<tr><td>ShowTicks</td><td>True</td><td>Boolean</td><td></td></tr>
<tr><td>TickLifetime</td><td>30</td><td>Integer</td><td></td></tr>
<tr><td>TickVelocity</td><td>2</td><td>Integer</td><td></td></tr>
<tr><td>TickRate</td><td>10</td><td>Integer</td><td></td></tr>
</table>

### RepairableBuilding
Building can be repaired by the repair button.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>RepairPercent</td><td>20</td><td>Integer</td><td>Cost to fully repair the actor as a percent of its value. </td></tr>
<tr><td>RepairInterval</td><td>24</td><td>Integer</td><td>Number of ticks between each repair step. </td></tr>
<tr><td>RepairStep</td><td>7</td><td>Integer</td><td>The maximum amount of HP to repair each step. </td></tr>
<tr><td>RepairDamageTypes</td><td></td><td>Collection of DamageType</td><td>Damage types used for the repair. </td></tr>
<tr><td>RepairBonuses</td><td>100, 150, 175, 200, 220, 240, 260, 280, 300</td><td>Collection of Integer</td><td>The percentage repair bonus applied with increasing numbers of repairers. </td></tr>
<tr><td>CancelWhenDisabled</td><td>False</td><td>Boolean</td><td>Cancel the repair state when the trait is disabled. </td></tr>
<tr><td>PlayerExperience</td><td>0</td><td>Integer</td><td>Experience gained by a player for repairing structures of allied players. </td></tr>
<tr><td>RepairCondition</td><td></td><td>String</td><td>The condition to grant to self while being repaired. </td></tr>
<tr><td>RepairingNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### RequiresBuildableArea
This actor requires another actor with 'GivesBuildableArea' trait around to be placed.

Requires trait: [`Building`](#building).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>AreaTypes</td><td><em>(required)</em></td><td>Set of System.String[]</td><td>Types of buildable are this actor requires. </td></tr>
<tr><td>Adjacent</td><td>2</td><td>Integer</td><td>Maximum range from the actor with 'GivesBuildableArea' this can be placed at. </td></tr>
</table>

### Reservable
Reserve landing places for aircraft.

### SequencePlaceBuildingPreview
Creates a building placement preview based on a defined sequence.

Requires trait: [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Sequence</td><td>idle</td><td>String</td><td>Sequence name to use. </td></tr>
<tr><td>SequenceAlpha</td><td>1</td><td>Real Number</td><td>Custom opacity to apply to the sequence sprite. </td></tr>
<tr><td>FootprintUnderPreview</td><td>Valid, LineBuild</td><td>PlaceBuildingCellType</td><td>Footprint types to draw underneath the actor preview. </td></tr>
<tr><td>FootprintOverPreview</td><td>Invalid</td><td>PlaceBuildingCellType</td><td>Footprint types to draw above the actor preview. </td></tr>
<tr><td>Palette</td><td>terrain</td><td>String</td><td>Palette to use for rendering the placement sprite. </td></tr>
<tr><td>FootprintAlpha</td><td>1</td><td>Real Number</td><td>Custom opacity to apply to the placement sprite. </td></tr>
<tr><td>LineBuildFootprintAlpha</td><td>1</td><td>Real Number</td><td>Custom opacity to apply to the line-build placement sprite. </td></tr>
</table>

### TransformsIntoAircraft
Add to a building to expose a move cursor that triggers Transforms and issues a move order to the transformed actor.

Requires trait: [`Transforms`](#transforms).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>MoveIntoShroud</td><td>True</td><td>Boolean</td><td>Can the actor be ordered to move in to shroud? </td></tr>
<tr><td>DockActors</td><td><em>(required)</em></td><td>Set of System.String[]</td><td></td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>RequiresForceMove</td><td>False</td><td>Boolean</td><td>Require the force-move modifier to display the move cursor. </td></tr>
<tr><td>Cursor</td><td>move</td><td>String</td><td>Cursor to display when a move order can be issued at target location. </td></tr>
<tr><td>BlockedCursor</td><td>move-blocked</td><td>String</td><td>Cursor to display when a move order cannot be issued at target location. </td></tr>
<tr><td>EnterCursor</td><td>enter</td><td>String</td><td>Cursor to display when able to land at target building. </td></tr>
<tr><td>EnterBlockedCursor</td><td>enter-blocked</td><td>String</td><td>Cursor to display when unable to land at target building. </td></tr>
<tr><td>TargetLineColor</td><td>008000</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line for regular move orders. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### TransformsIntoEntersTunnels
Add to a building to expose a move cursor that triggers Transforms and issues an enter tunnel order to the transformed actor.

Requires trait: [`Transforms`](#transforms).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>EnterCursor</td><td>enter</td><td>String</td><td>Cursor to display when able to enter target tunnel. </td></tr>
<tr><td>EnterBlockedCursor</td><td>enter-blocked</td><td>String</td><td>Cursor to display when unable to enter target tunnel. </td></tr>
<tr><td>TargetLineColor</td><td>008000</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line while in tunnels. </td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>RequiresForceMove</td><td>False</td><td>Boolean</td><td>Require the force-move modifier to display the enter cursor. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### TransformsIntoMobile
Add to a building to expose a move cursor that triggers Transforms and issues a move order to the transformed actor.

Requires trait: [`Transforms`](#transforms).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Locomotor</td><td><em>(required)</em></td><td>String</td><td>Locomotor used by the transformed actor. Must be defined on the World actor. </td></tr>
<tr><td>Cursor</td><td>move</td><td>String</td><td>Cursor to display when a move order can be issued at target location. </td></tr>
<tr><td>TerrainCursors</td><td></td><td>Dictionary with Key: String, Value String</td><td>Cursor overrides to display for specific terrain types. A dictionary of [terrain type]: [cursor name]. </td></tr>
<tr><td>BlockedCursor</td><td>move-blocked</td><td>String</td><td>Cursor to display when a move order cannot be issued at target location. </td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>TargetLineColor</td><td>008000</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line for regular move orders. </td></tr>
<tr><td>RequiresForceMove</td><td>False</td><td>Boolean</td><td>Require the force-move modifier to display the move cursor. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### TransformsIntoPassenger
Add to a building to expose a move cursor that triggers Transforms and issues an EnterTransport order to the transformed actor.

Requires trait: [`Transforms`](#transforms).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>CargoType</td><td></td><td>String</td><td></td></tr>
<tr><td>Weight</td><td>1</td><td>Integer</td><td></td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>TargetLineColor</td><td>008000</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line. </td></tr>
<tr><td>RequiresForceMove</td><td>False</td><td>Boolean</td><td>Require the force-move modifier to display the enter cursor. </td></tr>
<tr><td>EnterCursor</td><td>enter</td><td>String</td><td>Cursor to display when able to enter target actor. </td></tr>
<tr><td>EnterBlockedCursor</td><td>enter-blocked</td><td>String</td><td>Cursor to display when unable to enter target actor. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### TransformsIntoRepairable
Add to a building to expose a move cursor that triggers Transforms and issues a repair order to the transformed actor.

Requires trait: [`Transforms`](#transforms).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>RepairActors</td><td><em>(required)</em></td><td>Set of System.String[]</td><td></td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>TargetLineColor</td><td>008000</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line. </td></tr>
<tr><td>RequiresForceMove</td><td>False</td><td>Boolean</td><td>Require the force-move modifier to display the enter cursor. </td></tr>
<tr><td>EnterCursor</td><td>enter</td><td>String</td><td>Cursor to display when able to be repaired at target actor. </td></tr>
<tr><td>EnterBlockedCursor</td><td>enter-blocked</td><td>String</td><td>Cursor to display when unable to be repaired at target actor. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### TransformsIntoTransforms
Add to a building to allow queued transform orders while undeploying.

Requires trait: [`Transforms`](#transforms).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### Capturable
This actor can be captured by a unit with Captures: trait.
This trait should not be disabled if the actor also uses FrozenUnderFog.

Requires trait: [`CaptureManager`](#capturemanager).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Types</td><td><em>(required)</em></td><td>Collection of CaptureType</td><td>CaptureTypes (from the Captures trait) that are able to capture this. </td></tr>
<tr><td>ValidRelationships</td><td>Enemy, Neutral</td><td>PlayerRelationship</td><td>What player relationships the target's owner needs to be captured by this actor. </td></tr>
<tr><td>CancelActivity</td><td>False</td><td>Boolean</td><td>Cancel the actor's current activity when getting captured. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### CapturableProgressBar
Visualize capture progress.

Requires trait: [`Capturable`](#capturable).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Color</td><td>FFA500</td><td>Color (RRGGBB[AA] notation)</td><td></td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### CapturableProgressBlink
Blinks the actor and captor when it is being captured.

Requires trait: [`Capturable`](#capturable).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Interval</td><td>50</td><td>Integer</td><td>Number of ticks to wait between repeating blinks. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### CaptureManager
Manages Captures and Capturable traits on an actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>CapturingCondition</td><td></td><td>String</td><td>Condition granted when capturing an actor. </td></tr>
<tr><td>BeingCapturedCondition</td><td></td><td>String</td><td>Condition granted when being captured by another actor. </td></tr>
<tr><td>PreventsAutoTarget</td><td>True</td><td>Boolean</td><td>Should units friendly to the capturing actor auto-target this actor while it is being captured? </td></tr>
</table>

### CaptureProgressBar
Visualize the progress of this actor being captured.

Requires trait: [`Captures`](#captures).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Color</td><td>FFA500</td><td>Color (RRGGBB[AA] notation)</td><td></td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### Captures
This actor can capture other actors which have the Capturable: trait.

Requires trait: [`CaptureManager`](#capturemanager).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>CaptureTypes</td><td><em>(required)</em></td><td>Collection of CaptureType</td><td>Types of actors that it can capture, as long as the type also exists in the Capturable Type: trait. </td></tr>
<tr><td>SabotageThreshold</td><td>0</td><td>Integer</td><td>Targets with health above this percentage will be sabotaged instead of captured. Set to 0 to disable sabotaging. </td></tr>
<tr><td>SabotageHPRemoval</td><td>50</td><td>Integer</td><td>Sabotage damage expressed as a percentage of maximum target health. </td></tr>
<tr><td>SabotageDamageTypes</td><td></td><td>Collection of DamageType</td><td>Damage types that applied with the sabotage damage. </td></tr>
<tr><td>CaptureDelay</td><td>0</td><td>Integer</td><td>Delay (in ticks) that to wait next to the target before initiating the capture. </td></tr>
<tr><td>ConsumedByCapture</td><td>True</td><td>Boolean</td><td>Enter the target actor and be consumed by the capture. </td></tr>
<tr><td>PlayerExperience</td><td>0</td><td>Integer</td><td>Experience granted to the capturing player. </td></tr>
<tr><td>PlayerExperienceRelationships</td><td>Enemy</td><td>PlayerRelationship</td><td>Relationships that the structure's previous owner needs to have for the capturing player to receive Experience. </td></tr>
<tr><td>SabotageCursor</td><td>capture</td><td>String</td><td>Cursor to display when the health of the target actor is above the sabotage threshold. </td></tr>
<tr><td>EnterCursor</td><td>enter</td><td>String</td><td>Cursor to display when able to capture the target actor. </td></tr>
<tr><td>EnterBlockedCursor</td><td>enter-blocked</td><td>String</td><td>Cursor to display when unable to capture the target actor. </td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>TargetLineColor</td><td>DC143C</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### Cargo
This actor can transport Passenger actors.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>MaxWeight</td><td>0</td><td>Integer</td><td>The maximum sum of Passenger.Weight that this actor can support. </td></tr>
<tr><td>Types</td><td></td><td>Set of System.String[]</td><td>`Passenger.CargoType`s that can be loaded into this actor. </td></tr>
<tr><td>InitialUnits</td><td></td><td>Collection of String</td><td>A list of actor types that are initially spawned into this actor. </td></tr>
<tr><td>EjectOnSell</td><td>True</td><td>Boolean</td><td>When this actor is sold should all of its passengers be unloaded? </td></tr>
<tr><td>EjectOnDeath</td><td>False</td><td>Boolean</td><td>When this actor dies should all of its passengers be unloaded? </td></tr>
<tr><td>UnloadTerrainTypes</td><td></td><td>Set of System.String[]</td><td>Terrain types that this actor is allowed to eject actors onto. Leave empty for all terrain types. </td></tr>
<tr><td>UnloadVoice</td><td>Action</td><td>String</td><td>Voice to play when ordered to unload the passengers. </td></tr>
<tr><td>LoadRange</td><td>5c0</td><td>1D World Distance</td><td>Radius to search for a load/unload location if the ordered cell is blocked. </td></tr>
<tr><td>PassengerFacing</td><td>512</td><td>1D World Angle</td><td>Which direction the passenger will face (relative to the transport) when unloading. </td></tr>
<tr><td>AfterLoadDelay</td><td>8</td><td>Integer</td><td>Delay (in ticks) before continuing after loading a passenger. </td></tr>
<tr><td>BeforeUnloadDelay</td><td>8</td><td>Integer</td><td>Delay (in ticks) before unloading the first passenger. </td></tr>
<tr><td>AfterUnloadDelay</td><td>25</td><td>Integer</td><td>Delay (in ticks) before continuing after unloading a passenger. </td></tr>
<tr><td>UnloadCursor</td><td>deploy</td><td>String</td><td>Cursor to display when able to unload the passengers. </td></tr>
<tr><td>UnloadBlockedCursor</td><td>deploy-blocked</td><td>String</td><td>Cursor to display when unable to unload the passengers. </td></tr>
<tr><td>LoadingCondition</td><td></td><td>String</td><td>The condition to grant to self while waiting for cargo to load. </td></tr>
<tr><td>LoadedCondition</td><td></td><td>String</td><td>The condition to grant to self while passengers are loaded. Condition can stack with multiple passengers. </td></tr>
<tr><td>PassengerConditions</td><td></td><td>Dictionary with Key: String, Value String</td><td>Conditions to grant when specified actors are loaded inside the transport. A dictionary of [actor id]: [condition]. </td></tr>
</table>

### Carryable
Can be carried by actors with the `Carryall` trait.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ReservedCondition</td><td></td><td>String</td><td>The condition to grant to self while a carryall has been reserved. </td></tr>
<tr><td>CarriedCondition</td><td></td><td>String</td><td>The condition to grant to self while being carried. </td></tr>
<tr><td>LockedCondition</td><td></td><td>String</td><td>The condition to grant to self while being locked for carry. </td></tr>
<tr><td>LocalOffset</td><td>0,0,0</td><td>3D World Vector</td><td>Carryall attachment point relative to body. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### CarryableHarvester

### Carryall
Transports actors with the `Carryable` trait.

Requires traits: [`Aircraft`](#aircraft), [`BodyOrientation`](#bodyorientation).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>InitialActor</td><td></td><td>String</td><td>Actor type that is initially spawned into this actor. </td></tr>
<tr><td>BeforeLoadDelay</td><td>0</td><td>Integer</td><td>Delay (in ticks) on the ground while attaching an actor to the carryall. </td></tr>
<tr><td>BeforeUnloadDelay</td><td>0</td><td>Integer</td><td>Delay (in ticks) on the ground while detaching an actor from the carryall. </td></tr>
<tr><td>LocalOffset</td><td>0,0,0</td><td>3D World Vector</td><td>Carryable attachment point relative to body. </td></tr>
<tr><td>DropRange</td><td>5c0</td><td>1D World Distance</td><td>Radius around the target drop location that are considered if the target tile is blocked. </td></tr>
<tr><td>UnloadCursor</td><td>deploy</td><td>String</td><td>Cursor to display when able to unload the passengers. </td></tr>
<tr><td>UnloadBlockedCursor</td><td>deploy-blocked</td><td>String</td><td>Cursor to display when unable to unload the passengers. </td></tr>
<tr><td>AllowDropOff</td><td>False</td><td>Boolean</td><td>Allow moving and unloading with one order using force-move </td></tr>
<tr><td>DropOffCursor</td><td>ability</td><td>String</td><td>Cursor to display when able to drop off the passengers at location. </td></tr>
<tr><td>DropOffBlockedCursor</td><td>move-blocked</td><td>String</td><td>Cursor to display when unable to drop off the passengers at location. </td></tr>
<tr><td>PickUpCursor</td><td>ability</td><td>String</td><td>Cursor to display when picking up the passengers. </td></tr>
<tr><td>CarryCondition</td><td></td><td>String</td><td>Condition to grant to the Carryall while it is carrying something. </td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>TargetLineColor</td><td>FFFF00</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line. </td></tr>
</table>

### CashTrickler
Lets the actor generate cash in a set periodic time.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Interval</td><td>50</td><td>Integer</td><td>Number of ticks to wait between giving money. </td></tr>
<tr><td>InitialDelay</td><td>0</td><td>Integer</td><td>Number of ticks to wait before giving first money. </td></tr>
<tr><td>Amount</td><td>15</td><td>Integer</td><td>Amount of money to give each time. </td></tr>
<tr><td>ShowTicks</td><td>True</td><td>Boolean</td><td>Whether to show the cash tick indicators rising from the actor. </td></tr>
<tr><td>DisplayDuration</td><td>30</td><td>Integer</td><td>How long to show the cash tick indicator when enabled. </td></tr>
<tr><td>UseResourceStorage</td><td>False</td><td>Boolean</td><td>Use resource storage for cash granted. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ChangesHealth
Attach this to actors which should regenerate or lose health points over time.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Step</td><td>5</td><td>Integer</td><td>Absolute amount of health points added in each step. Use negative values to apply damage. </td></tr>
<tr><td>PercentageStep</td><td>0</td><td>Integer</td><td>Relative percentages of health added in each step. Use negative values to apply damage. When both values are defined, their summary will be applied. </td></tr>
<tr><td>Delay</td><td>5</td><td>Integer</td><td>Time in ticks to wait between each health modification. </td></tr>
<tr><td>StartIfBelow</td><td>50</td><td>Integer</td><td>Heal if current health is below this percentage of full health. </td></tr>
<tr><td>DamageCooldown</td><td>0</td><td>Integer</td><td>Time in ticks to wait after taking damage. </td></tr>
<tr><td>DamageTypes</td><td></td><td>Collection of DamageType</td><td>Apply the health change when encountering these damage types. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ChangesTerrain
Modifies the terrain type underneath the actors location.

Requires trait: [`Immobile`](#immobile).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>TerrainType</td><td><em>(required)</em></td><td>String</td><td></td></tr>
</table>

### Cloak
This unit can cloak and uncloak in specific situations.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>InitialDelay</td><td>10</td><td>Integer</td><td>Measured in game ticks. </td></tr>
<tr><td>CloakDelay</td><td>30</td><td>Integer</td><td>Measured in game ticks. </td></tr>
<tr><td>UncloakOn</td><td>Attack, Unload, Infiltrate, Demolish, Dock</td><td>UncloakType</td><td>Events leading to the actor getting uncloaked. Possible values are: Attack, Move, Unload, Infiltrate, Demolish, Dock, Damage, Heal and SelfHeal. 'Dock' is triggered when docking to a refinery or resupplying. </td></tr>
<tr><td>CloakSound</td><td></td><td>String</td><td></td></tr>
<tr><td>UncloakSound</td><td></td><td>String</td><td></td></tr>
<tr><td>Palette</td><td>cloak</td><td>String</td><td></td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td></td></tr>
<tr><td>CloakTypes</td><td>Cloak</td><td>Collection of CloakType</td><td></td></tr>
<tr><td>CloakedCondition</td><td></td><td>String</td><td>The condition to grant to self while cloaked. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### CombatDebugOverlay
Displays fireports, muzzle offsets, and hit areas in developer mode.

### CommandBarBlacklist
Blacklist certain order types to disable on the command bar when this unit is selected.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>DisableStop</td><td>True</td><td>Boolean</td><td>Disable the 'Stop' button for this actor. </td></tr>
<tr><td>DisableWaypointMode</td><td>True</td><td>Boolean</td><td>Disable the 'Waypoint Mode' button for this actor. </td></tr>
</table>

### ExternalCondition
Allows a condition to be granted from an external source (Lua, warheads, etc).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td></td></tr>
<tr><td>SourceCap</td><td>0</td><td>Integer</td><td>If > 0, restrict the number of times that this condition can be granted by a single source. </td></tr>
<tr><td>TotalCap</td><td>0</td><td>Integer</td><td>If > 0, restrict the number of times that this condition can be granted by any source. </td></tr>
</table>

### GrantCondition
Grants a condition while the trait is active.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td>Condition to grant. </td></tr>
<tr><td>GrantPermanently</td><td>False</td><td>Boolean</td><td>Is the condition irrevocable once it has been activated? </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### GrantConditionOnAttack
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td>The condition type to grant. </td></tr>
<tr><td>ArmamentNames</td><td>primary</td><td>Set of System.String[]</td><td>Name of the armaments that grant this condition. </td></tr>
<tr><td>RequiredShotsPerInstance</td><td>1</td><td>Collection of Integer</td><td>Shots required to apply an instance of the condition. If there are more instances of the condition granted than values listed, the last value is used for all following instances beyond the defined range. </td></tr>
<tr><td>MaximumInstances</td><td>1</td><td>Integer</td><td>Maximum instances of the condition to grant. </td></tr>
<tr><td>IsCyclic</td><td>False</td><td>Boolean</td><td>Should all instances reset if the actor passes the final stage? </td></tr>
<tr><td>RevokeDelay</td><td>15</td><td>Integer</td><td>Amount of ticks required to pass without firing to revoke an instance. </td></tr>
<tr><td>RevokeOnNewTarget</td><td>False</td><td>Boolean</td><td>Should an instance be revoked if the actor changes target? </td></tr>
<tr><td>RevokeAll</td><td>False</td><td>Boolean</td><td>Should all instances be revoked instead of only one? </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### GrantConditionOnBotOwner
Grants a condition to this actor when it is owned by an AI bot.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td>Condition to grant. </td></tr>
<tr><td>Bots</td><td><em>(required)</em></td><td>Collection of String</td><td>Bot types that trigger the condition. </td></tr>
</table>

### GrantConditionOnCombatantOwner
Grants a condition if the owner is a combatant.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td>The condition to grant. </td></tr>
</table>

### GrantConditionOnDamageState
Applies a condition to the actor at specified damage states.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td>Condition to grant. </td></tr>
<tr><td>EnabledSounds</td><td></td><td>Collection of String</td><td>Play a random sound from this list when enabled. </td></tr>
<tr><td>DisabledSounds</td><td></td><td>Collection of String</td><td>Play a random sound from this list when disabled. </td></tr>
<tr><td>ValidDamageStates</td><td>Heavy, Critical</td><td>DamageState</td><td>Levels of damage at which to grant the condition. </td></tr>
<tr><td>GrantPermanently</td><td>False</td><td>Boolean</td><td>Is the condition irrevocable once it has been activated? </td></tr>
</table>

### GrantConditionOnDeploy
Grants a condition when a deploy order is issued.Can be paused with the granted condition to disable undeploying.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>UndeployedCondition</td><td></td><td>String</td><td>The condition to grant while the actor is undeployed. </td></tr>
<tr><td>DeployedCondition</td><td><em>(required)</em></td><td>String</td><td>The condition to grant after deploying and revoke before undeploying. </td></tr>
<tr><td>AllowedTerrainTypes</td><td></td><td>Set of System.String[]</td><td>The terrain types that this actor can deploy on. Leave empty to allow any. </td></tr>
<tr><td>CanDeployOnRamps</td><td>False</td><td>Boolean</td><td>Can this actor deploy on slopes? </td></tr>
<tr><td>DeployCursor</td><td>deploy</td><td>String</td><td>Cursor to display when able to (un)deploy the actor. </td></tr>
<tr><td>DeployBlockedCursor</td><td>deploy-blocked</td><td>String</td><td>Cursor to display when unable to (un)deploy the actor. </td></tr>
<tr><td>Facing</td><td></td><td>1D World Angle (optional)</td><td>Facing that the actor must face before deploying. Leave undefined to deploy regardless of facing. </td></tr>
<tr><td>DeploySounds</td><td></td><td>Collection of String</td><td>Play a randomly selected sound from this list when deploying. </td></tr>
<tr><td>UndeploySounds</td><td></td><td>Collection of String</td><td>Play a randomly selected sound from this list when undeploying. </td></tr>
<tr><td>SkipMakeAnimation</td><td>False</td><td>Boolean</td><td>Skip make/deploy animation? </td></tr>
<tr><td>UndeployOnMove</td><td>False</td><td>Boolean</td><td>Undeploy before the actor tries to move? </td></tr>
<tr><td>UndeployOnPickup</td><td>False</td><td>Boolean</td><td>Undeploy before the actor is picked up by a Carryall? </td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>EditorDeployedDisplayOrder</td><td>4</td><td>Integer</td><td>Display order for the deployed checkbox in the map editor </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### GrantConditionOnFaction
Grants a condition while the trait is active.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td>Condition to grant. </td></tr>
<tr><td>Factions</td><td></td><td>Set of System.String[]</td><td>Only grant this condition for certain factions. </td></tr>
<tr><td>ResetOnOwnerChange</td><td>False</td><td>Boolean</td><td>Should it recheck everything when it is captured? </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### GrantConditionOnHealth
Applies a condition to the actor at when its health is between 2 specific values.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td>Condition to grant. </td></tr>
<tr><td>EnabledSounds</td><td></td><td>Collection of String</td><td>Play a random sound from this list when enabled. </td></tr>
<tr><td>DisabledSounds</td><td></td><td>Collection of String</td><td>Play a random sound from this list when disabled. </td></tr>
<tr><td>MinHP</td><td>0</td><td>Integer</td><td>Minimum level of health at which to grant the condition. </td></tr>
<tr><td>MaxHP</td><td>0</td><td>Integer</td><td>Maximum level of health at which to grant the condition. Non-positive values will make it use Health.HP. </td></tr>
<tr><td>GrantPermanently</td><td>False</td><td>Boolean</td><td>Is the condition irrevokable once it has been granted? </td></tr>
</table>

### GrantConditionOnJumpjetLayer
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td>The condition to grant to self when changing to specific custom layer. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### GrantConditionOnLineBuildDirection
Requires trait: [`LineBuild`](#linebuild).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td>Condition to grant. </td></tr>
<tr><td>Direction</td><td><em>(required)</em></td><td>LineBuildDirection</td><td>Line build direction to trigger the condition. </td></tr>
</table>

### GrantConditionOnMovement
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td>Condition to grant. </td></tr>
<tr><td>ValidMovementTypes</td><td>Horizontal</td><td>MovementType</td><td>Apply condition on listed movement types. Available options are: None, Horizontal, Vertical, Turn. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### GrantConditionOnPlayerResources
Grants a condition to this actor when the player has stored resources.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td>Condition to grant. </td></tr>
<tr><td>Threshold</td><td>0</td><td>Integer</td><td>Enable condition when the amount of stored resources is greater than this. </td></tr>
</table>

### GrantConditionOnPowerState
Grants condition as long as a valid power state is maintained.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td>Condition to grant. </td></tr>
<tr><td>ValidPowerStates</td><td><em>(required)</em></td><td>PowerState</td><td>PowerStates at which the condition is granted. Options are Normal, Low and Critical. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### GrantConditionOnPrerequisite
Grants a condition to the actor this is attached to when prerequisites are available.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td>The condition to grant. </td></tr>
<tr><td>Prerequisites</td><td><em>(required)</em></td><td>Collection of String</td><td>List of required prerequisites. </td></tr>
</table>

### GrantConditionOnProduction
Grants a condition when this actor produces a specific actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td>The condition to grant </td></tr>
<tr><td>Actors</td><td></td><td>Set of System.String[]</td><td>The actors to grant condition for. If empty condition will be granted for all actors. </td></tr>
<tr><td>Duration</td><td>-1</td><td>Integer</td><td>How long condition is applies for. Use -1 for infinite. </td></tr>
<tr><td>ShowSelectionBar</td><td>True</td><td>Boolean</td><td>Show a selection bar while condition is applied if it has a duration. </td></tr>
<tr><td>SelectionBarColor</td><td>FF00FF</td><td>Color (RRGGBB[AA] notation)</td><td></td></tr>
</table>

### GrantConditionOnSubterraneanLayer
Grants Condition on subterranean layer. Also plays transition audio-visuals.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>SubterraneanTransitionImage</td><td></td><td>String</td><td>Dig animation image to play when transitioning. </td></tr>
<tr><td>SubterraneanTransitionSequence</td><td></td><td>String</td><td>Dig animation sequence to play when transitioning. </td></tr>
<tr><td>SubterraneanTransitionPalette</td><td>effect</td><td>String</td><td></td></tr>
<tr><td>SubterraneanTransitionSound</td><td></td><td>String</td><td>Dig sound to play when transitioning. </td></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td>The condition to grant to self when changing to specific custom layer. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### GrantConditionOnTerrain
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td>Condition to grant. </td></tr>
<tr><td>TerrainTypes</td><td><em>(required)</em></td><td>Collection of String</td><td>Terrain names to trigger the condition. </td></tr>
</table>

### GrantConditionOnTunnelLayer
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td>The condition to grant to self when changing to specific custom layer. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### GrantConditionWhileAiming
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td>The condition to grant while aiming. </td></tr>
</table>

### GrantExternalConditionToCrusher
Grant a condition to the crushing actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>WarnCrushCondition</td><td></td><td>String</td><td>The condition to apply on a crush attempt. Must be included among the crusher actor's ExternalCondition traits. </td></tr>
<tr><td>WarnCrushDuration</td><td>0</td><td>Integer</td><td>Duration of the condition applied on a crush attempt (in ticks). Set to 0 for a permanent condition. </td></tr>
<tr><td>OnCrushCondition</td><td></td><td>String</td><td>The condition to apply on a successful crush. Must be included among the crusher actor's ExternalCondition traits. </td></tr>
<tr><td>OnCrushDuration</td><td>0</td><td>Integer</td><td>Duration of the condition applied on a successful crush (in ticks). Set to 0 for a permanent condition. </td></tr>
</table>

### GrantExternalConditionToProduced
Grants a condition to actors produced by this actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td>The condition to apply. Must be included in the produced actor's ExternalConditions list. </td></tr>
<tr><td>Duration</td><td>0</td><td>Integer</td><td>Duration of the condition (in ticks). Set to 0 for a permanent condition. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### LineBuildSegmentExternalCondition
Applies a condition to connected line build segments.

Requires trait: [`LineBuild`](#linebuild).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td>The condition to apply. Must be included in the target actor's ExternalConditions list. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ProximityExternalCondition
Applies a condition to actors within a specified range.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td>The condition to apply. Must be included in the target actor's ExternalConditions list. </td></tr>
<tr><td>Range</td><td>3c0</td><td>1D World Distance</td><td>The range to search for actors. </td></tr>
<tr><td>MaximumVerticalOffset</td><td>0c0</td><td>1D World Distance</td><td>The maximum vertical range above terrain to search for actors. Ignored if 0 (actors are selected regardless of vertical distance). </td></tr>
<tr><td>ValidRelationships</td><td>Ally</td><td>PlayerRelationship</td><td>What player relationships are affected. </td></tr>
<tr><td>AffectsParent</td><td>False</td><td>Boolean</td><td>Condition is applied permanently to this actor. </td></tr>
<tr><td>EnableSound</td><td></td><td>String</td><td></td></tr>
<tr><td>DisableSound</td><td></td><td>String</td><td></td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ToggleConditionOnOrder
Toggles a condition on and off when a specified order type is received.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td>Condition to grant. </td></tr>
<tr><td>OrderName</td><td><em>(required)</em></td><td>String</td><td>Order name that toggles the condition. </td></tr>
<tr><td>EnabledSound</td><td></td><td>String</td><td></td></tr>
<tr><td>EnabledSpeech</td><td></td><td>String</td><td></td></tr>
<tr><td>DisabledSound</td><td></td><td>String</td><td></td></tr>
<tr><td>DisabledSpeech</td><td></td><td>String</td><td></td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### Crate
Requires trait: [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Duration</td><td>0</td><td>Integer</td><td>Length of time (in ticks) until the crate gets removed automatically. A value of zero disables auto-removal. </td></tr>
<tr><td>TerrainTypes</td><td></td><td>Set of System.String[]</td><td>Allowed to land on. </td></tr>
<tr><td>CrushClass</td><td>crate</td><td>String</td><td>Define actors that can collect crates by setting this into the Crushes field from the Mobile trait. </td></tr>
</table>

### CrateAction
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>SelectionShares</td><td>10</td><td>Integer</td><td>Chance of getting this crate, assuming the collector is compatible. </td></tr>
<tr><td>Image</td><td>crate-effects</td><td>String</td><td>Image containing the crate effect animation sequence. </td></tr>
<tr><td>Sequence</td><td></td><td>String</td><td>Animation sequence played when collected. Leave empty for no effect. </td></tr>
<tr><td>Palette</td><td>effect</td><td>String</td><td>Palette to draw the animation in. </td></tr>
<tr><td>Sound</td><td></td><td>String</td><td>Audio clip to play when the crate is collected. </td></tr>
<tr><td>Notification</td><td></td><td>String</td><td>Notification to play when the crate is collected. </td></tr>
<tr><td>TimeDelay</td><td>0</td><td>Integer</td><td>The earliest time (in ticks) that this crate action can occur on. </td></tr>
<tr><td>Prerequisites</td><td></td><td>Collection of String</td><td>Only allow this crate action when the collector has these prerequisites </td></tr>
<tr><td>ExcludedActorTypes</td><td></td><td>Collection of String</td><td>Actor types that this crate action will not occur for. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### DuplicateUnitCrateAction
Creates duplicates of the actor that collects the crate.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>MaxAmount</td><td>2</td><td>Integer</td><td>The maximum number of duplicates to make. </td></tr>
<tr><td>MinAmount</td><td>1</td><td>Integer</td><td>The minimum number of duplicates to make. Overrules MaxDuplicatesWorth. </td></tr>
<tr><td>MaxDuplicateValue</td><td>-1</td><td>Integer</td><td>The maximum total value allowed for the duplicates. Duplication stops if the total worth will exceed this number. -1 = no limit </td></tr>
<tr><td>MaxRadius</td><td>4</td><td>Integer</td><td>The maximum radius (in cells) that duplicates can be spawned. </td></tr>
<tr><td>ValidTargets</td><td>Ground, Water</td><td>Collection of TargetableType</td><td>The list of unit target types we are allowed to duplicate. </td></tr>
<tr><td>ValidFactions</td><td></td><td>Set of System.String[]</td><td>Which factions this crate action can occur for. </td></tr>
<tr><td>Owner</td><td></td><td>String</td><td>Is the new duplicates given to a specific owner, regardless of whom collected it? </td></tr>
<tr><td>SelectionShares</td><td>10</td><td>Integer</td><td>Chance of getting this crate, assuming the collector is compatible. </td></tr>
<tr><td>Image</td><td>crate-effects</td><td>String</td><td>Image containing the crate effect animation sequence. </td></tr>
<tr><td>Sequence</td><td></td><td>String</td><td>Animation sequence played when collected. Leave empty for no effect. </td></tr>
<tr><td>Palette</td><td>effect</td><td>String</td><td>Palette to draw the animation in. </td></tr>
<tr><td>Sound</td><td></td><td>String</td><td>Audio clip to play when the crate is collected. </td></tr>
<tr><td>Notification</td><td></td><td>String</td><td>Notification to play when the crate is collected. </td></tr>
<tr><td>TimeDelay</td><td>0</td><td>Integer</td><td>The earliest time (in ticks) that this crate action can occur on. </td></tr>
<tr><td>Prerequisites</td><td></td><td>Collection of String</td><td>Only allow this crate action when the collector has these prerequisites </td></tr>
<tr><td>ExcludedActorTypes</td><td></td><td>Collection of String</td><td>Actor types that this crate action will not occur for. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ExplodeCrateAction
Fires a weapon at the location when collected.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Weapon</td><td><em>(required)</em></td><td>String</td><td>The weapon to fire upon collection. </td></tr>
<tr><td>SelectionShares</td><td>10</td><td>Integer</td><td>Chance of getting this crate, assuming the collector is compatible. </td></tr>
<tr><td>Image</td><td>crate-effects</td><td>String</td><td>Image containing the crate effect animation sequence. </td></tr>
<tr><td>Sequence</td><td></td><td>String</td><td>Animation sequence played when collected. Leave empty for no effect. </td></tr>
<tr><td>Palette</td><td>effect</td><td>String</td><td>Palette to draw the animation in. </td></tr>
<tr><td>Sound</td><td></td><td>String</td><td>Audio clip to play when the crate is collected. </td></tr>
<tr><td>Notification</td><td></td><td>String</td><td>Notification to play when the crate is collected. </td></tr>
<tr><td>TimeDelay</td><td>0</td><td>Integer</td><td>The earliest time (in ticks) that this crate action can occur on. </td></tr>
<tr><td>Prerequisites</td><td></td><td>Collection of String</td><td>Only allow this crate action when the collector has these prerequisites </td></tr>
<tr><td>ExcludedActorTypes</td><td></td><td>Collection of String</td><td>Actor types that this crate action will not occur for. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### GiveCashCrateAction
Gives cash to the collector.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Amount</td><td>2000</td><td>Integer</td><td>Amount of cash to give. </td></tr>
<tr><td>UseCashTick</td><td>False</td><td>Boolean</td><td>Should the collected amount be displayed as a cash tick? </td></tr>
<tr><td>SelectionShares</td><td>10</td><td>Integer</td><td>Chance of getting this crate, assuming the collector is compatible. </td></tr>
<tr><td>Image</td><td>crate-effects</td><td>String</td><td>Image containing the crate effect animation sequence. </td></tr>
<tr><td>Sequence</td><td></td><td>String</td><td>Animation sequence played when collected. Leave empty for no effect. </td></tr>
<tr><td>Palette</td><td>effect</td><td>String</td><td>Palette to draw the animation in. </td></tr>
<tr><td>Sound</td><td></td><td>String</td><td>Audio clip to play when the crate is collected. </td></tr>
<tr><td>Notification</td><td></td><td>String</td><td>Notification to play when the crate is collected. </td></tr>
<tr><td>TimeDelay</td><td>0</td><td>Integer</td><td>The earliest time (in ticks) that this crate action can occur on. </td></tr>
<tr><td>Prerequisites</td><td></td><td>Collection of String</td><td>Only allow this crate action when the collector has these prerequisites </td></tr>
<tr><td>ExcludedActorTypes</td><td></td><td>Collection of String</td><td>Actor types that this crate action will not occur for. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### GiveMcvCrateAction
Spawns units when collected.
Adjust selection shares when player has no base.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>NoBaseSelectionShares</td><td>1000</td><td>Integer</td><td>The selection shares to use if the collector has no base. </td></tr>
<tr><td>Units</td><td><em>(required)</em></td><td>Collection of String</td><td>The list of units to spawn. </td></tr>
<tr><td>ValidFactions</td><td></td><td>Set of System.String[]</td><td>Factions that are allowed to trigger this action. </td></tr>
<tr><td>Owner</td><td></td><td>String</td><td>Override the owner of the newly spawned unit: e.g. Creeps or Neutral </td></tr>
<tr><td>SelectionShares</td><td>10</td><td>Integer</td><td>Chance of getting this crate, assuming the collector is compatible. </td></tr>
<tr><td>Image</td><td>crate-effects</td><td>String</td><td>Image containing the crate effect animation sequence. </td></tr>
<tr><td>Sequence</td><td></td><td>String</td><td>Animation sequence played when collected. Leave empty for no effect. </td></tr>
<tr><td>Palette</td><td>effect</td><td>String</td><td>Palette to draw the animation in. </td></tr>
<tr><td>Sound</td><td></td><td>String</td><td>Audio clip to play when the crate is collected. </td></tr>
<tr><td>Notification</td><td></td><td>String</td><td>Notification to play when the crate is collected. </td></tr>
<tr><td>TimeDelay</td><td>0</td><td>Integer</td><td>The earliest time (in ticks) that this crate action can occur on. </td></tr>
<tr><td>Prerequisites</td><td></td><td>Collection of String</td><td>Only allow this crate action when the collector has these prerequisites </td></tr>
<tr><td>ExcludedActorTypes</td><td></td><td>Collection of String</td><td>Actor types that this crate action will not occur for. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### GiveUnitCrateAction
Spawns units when collected.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Units</td><td><em>(required)</em></td><td>Collection of String</td><td>The list of units to spawn. </td></tr>
<tr><td>ValidFactions</td><td></td><td>Set of System.String[]</td><td>Factions that are allowed to trigger this action. </td></tr>
<tr><td>Owner</td><td></td><td>String</td><td>Override the owner of the newly spawned unit: e.g. Creeps or Neutral </td></tr>
<tr><td>SelectionShares</td><td>10</td><td>Integer</td><td>Chance of getting this crate, assuming the collector is compatible. </td></tr>
<tr><td>Image</td><td>crate-effects</td><td>String</td><td>Image containing the crate effect animation sequence. </td></tr>
<tr><td>Sequence</td><td></td><td>String</td><td>Animation sequence played when collected. Leave empty for no effect. </td></tr>
<tr><td>Palette</td><td>effect</td><td>String</td><td>Palette to draw the animation in. </td></tr>
<tr><td>Sound</td><td></td><td>String</td><td>Audio clip to play when the crate is collected. </td></tr>
<tr><td>Notification</td><td></td><td>String</td><td>Notification to play when the crate is collected. </td></tr>
<tr><td>TimeDelay</td><td>0</td><td>Integer</td><td>The earliest time (in ticks) that this crate action can occur on. </td></tr>
<tr><td>Prerequisites</td><td></td><td>Collection of String</td><td>Only allow this crate action when the collector has these prerequisites </td></tr>
<tr><td>ExcludedActorTypes</td><td></td><td>Collection of String</td><td>Actor types that this crate action will not occur for. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### GrantExternalConditionCrateAction
Grants a condition on the collector.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td>The condition to apply. Must be included in the target actor's ExternalConditions list. </td></tr>
<tr><td>Levels</td><td>1</td><td>Integer</td><td>How many times to grant the condition. </td></tr>
<tr><td>Duration</td><td>0</td><td>Integer</td><td>Duration of the condition (in ticks). Set to 0 for a permanent condition. </td></tr>
<tr><td>Range</td><td>0c3</td><td>1D World Distance</td><td>The range to search for extra collectors in. Extra collectors will also be granted the crate action. </td></tr>
<tr><td>MaxExtraCollectors</td><td>4</td><td>Integer</td><td>The maximum number of extra collectors to grant the crate action to. -1 = no limit </td></tr>
<tr><td>SelectionShares</td><td>10</td><td>Integer</td><td>Chance of getting this crate, assuming the collector is compatible. </td></tr>
<tr><td>Image</td><td>crate-effects</td><td>String</td><td>Image containing the crate effect animation sequence. </td></tr>
<tr><td>Sequence</td><td></td><td>String</td><td>Animation sequence played when collected. Leave empty for no effect. </td></tr>
<tr><td>Palette</td><td>effect</td><td>String</td><td>Palette to draw the animation in. </td></tr>
<tr><td>Sound</td><td></td><td>String</td><td>Audio clip to play when the crate is collected. </td></tr>
<tr><td>Notification</td><td></td><td>String</td><td>Notification to play when the crate is collected. </td></tr>
<tr><td>TimeDelay</td><td>0</td><td>Integer</td><td>The earliest time (in ticks) that this crate action can occur on. </td></tr>
<tr><td>Prerequisites</td><td></td><td>Collection of String</td><td>Only allow this crate action when the collector has these prerequisites </td></tr>
<tr><td>ExcludedActorTypes</td><td></td><td>Collection of String</td><td>Actor types that this crate action will not occur for. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### HealActorsCrateAction
Heals all actors that belong to the owner of the collector.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>TargetTypes</td><td></td><td>Collection of TargetableType</td><td>The target type(s) of the actors this crate action will heal. Leave empty to heal all actors. </td></tr>
<tr><td>SelectionShares</td><td>10</td><td>Integer</td><td>Chance of getting this crate, assuming the collector is compatible. </td></tr>
<tr><td>Image</td><td>crate-effects</td><td>String</td><td>Image containing the crate effect animation sequence. </td></tr>
<tr><td>Sequence</td><td></td><td>String</td><td>Animation sequence played when collected. Leave empty for no effect. </td></tr>
<tr><td>Palette</td><td>effect</td><td>String</td><td>Palette to draw the animation in. </td></tr>
<tr><td>Sound</td><td></td><td>String</td><td>Audio clip to play when the crate is collected. </td></tr>
<tr><td>Notification</td><td></td><td>String</td><td>Notification to play when the crate is collected. </td></tr>
<tr><td>TimeDelay</td><td>0</td><td>Integer</td><td>The earliest time (in ticks) that this crate action can occur on. </td></tr>
<tr><td>Prerequisites</td><td></td><td>Collection of String</td><td>Only allow this crate action when the collector has these prerequisites </td></tr>
<tr><td>ExcludedActorTypes</td><td></td><td>Collection of String</td><td>Actor types that this crate action will not occur for. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### HideMapCrateAction
Hides the entire map in shroud.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>IncludeAllies</td><td>False</td><td>Boolean</td><td>Should the map also be hidden for the allies of the collector's owner? </td></tr>
<tr><td>SelectionShares</td><td>10</td><td>Integer</td><td>Chance of getting this crate, assuming the collector is compatible. </td></tr>
<tr><td>Image</td><td>crate-effects</td><td>String</td><td>Image containing the crate effect animation sequence. </td></tr>
<tr><td>Sequence</td><td></td><td>String</td><td>Animation sequence played when collected. Leave empty for no effect. </td></tr>
<tr><td>Palette</td><td>effect</td><td>String</td><td>Palette to draw the animation in. </td></tr>
<tr><td>Sound</td><td></td><td>String</td><td>Audio clip to play when the crate is collected. </td></tr>
<tr><td>Notification</td><td></td><td>String</td><td>Notification to play when the crate is collected. </td></tr>
<tr><td>TimeDelay</td><td>0</td><td>Integer</td><td>The earliest time (in ticks) that this crate action can occur on. </td></tr>
<tr><td>Prerequisites</td><td></td><td>Collection of String</td><td>Only allow this crate action when the collector has these prerequisites </td></tr>
<tr><td>ExcludedActorTypes</td><td></td><td>Collection of String</td><td>Actor types that this crate action will not occur for. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### LevelUpCrateAction
Gives experience levels to the collector.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Levels</td><td>1</td><td>Integer</td><td>Number of experience levels to give. </td></tr>
<tr><td>Range</td><td>0c3</td><td>1D World Distance</td><td>The range to search for extra collectors in. Extra collectors will also be granted the crate action. </td></tr>
<tr><td>MaxExtraCollectors</td><td>4</td><td>Integer</td><td>The maximum number of extra collectors to grant the crate action to. </td></tr>
<tr><td>SelectionShares</td><td>10</td><td>Integer</td><td>Chance of getting this crate, assuming the collector is compatible. </td></tr>
<tr><td>Image</td><td>crate-effects</td><td>String</td><td>Image containing the crate effect animation sequence. </td></tr>
<tr><td>Sequence</td><td></td><td>String</td><td>Animation sequence played when collected. Leave empty for no effect. </td></tr>
<tr><td>Palette</td><td>effect</td><td>String</td><td>Palette to draw the animation in. </td></tr>
<tr><td>Sound</td><td></td><td>String</td><td>Audio clip to play when the crate is collected. </td></tr>
<tr><td>Notification</td><td></td><td>String</td><td>Notification to play when the crate is collected. </td></tr>
<tr><td>TimeDelay</td><td>0</td><td>Integer</td><td>The earliest time (in ticks) that this crate action can occur on. </td></tr>
<tr><td>Prerequisites</td><td></td><td>Collection of String</td><td>Only allow this crate action when the collector has these prerequisites </td></tr>
<tr><td>ExcludedActorTypes</td><td></td><td>Collection of String</td><td>Actor types that this crate action will not occur for. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### RevealMapCrateAction
Reveals the entire map.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>IncludeAllies</td><td>False</td><td>Boolean</td><td>Should the map also be revealed for the allies of the collector's owner? </td></tr>
<tr><td>SelectionShares</td><td>10</td><td>Integer</td><td>Chance of getting this crate, assuming the collector is compatible. </td></tr>
<tr><td>Image</td><td>crate-effects</td><td>String</td><td>Image containing the crate effect animation sequence. </td></tr>
<tr><td>Sequence</td><td></td><td>String</td><td>Animation sequence played when collected. Leave empty for no effect. </td></tr>
<tr><td>Palette</td><td>effect</td><td>String</td><td>Palette to draw the animation in. </td></tr>
<tr><td>Sound</td><td></td><td>String</td><td>Audio clip to play when the crate is collected. </td></tr>
<tr><td>Notification</td><td></td><td>String</td><td>Notification to play when the crate is collected. </td></tr>
<tr><td>TimeDelay</td><td>0</td><td>Integer</td><td>The earliest time (in ticks) that this crate action can occur on. </td></tr>
<tr><td>Prerequisites</td><td></td><td>Collection of String</td><td>Only allow this crate action when the collector has these prerequisites </td></tr>
<tr><td>ExcludedActorTypes</td><td></td><td>Collection of String</td><td>Actor types that this crate action will not occur for. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### SupportPowerCrateAction
Gives a supportpower to the collector.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Proxy</td><td><em>(required)</em></td><td>String</td><td>Which proxy actor, which grants the support power, to spawn. </td></tr>
<tr><td>SelectionShares</td><td>10</td><td>Integer</td><td>Chance of getting this crate, assuming the collector is compatible. </td></tr>
<tr><td>Image</td><td>crate-effects</td><td>String</td><td>Image containing the crate effect animation sequence. </td></tr>
<tr><td>Sequence</td><td></td><td>String</td><td>Animation sequence played when collected. Leave empty for no effect. </td></tr>
<tr><td>Palette</td><td>effect</td><td>String</td><td>Palette to draw the animation in. </td></tr>
<tr><td>Sound</td><td></td><td>String</td><td>Audio clip to play when the crate is collected. </td></tr>
<tr><td>Notification</td><td></td><td>String</td><td>Notification to play when the crate is collected. </td></tr>
<tr><td>TimeDelay</td><td>0</td><td>Integer</td><td>The earliest time (in ticks) that this crate action can occur on. </td></tr>
<tr><td>Prerequisites</td><td></td><td>Collection of String</td><td>Only allow this crate action when the collector has these prerequisites </td></tr>
<tr><td>ExcludedActorTypes</td><td></td><td>Collection of String</td><td>Actor types that this crate action will not occur for. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### CreatesShroud
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ValidRelationships</td><td>Enemy, Neutral</td><td>PlayerRelationship</td><td>Relationship the watching player needs to see the generated shroud. </td></tr>
<tr><td>MinRange</td><td>0c0</td><td>1D World Distance</td><td></td></tr>
<tr><td>Range</td><td>0c0</td><td>1D World Distance</td><td></td></tr>
<tr><td>MaxHeightDelta</td><td>-1</td><td>Integer</td><td>If >= 0, prevent cells that are this much higher than the actor from being revealed. </td></tr>
<tr><td>MoveRecalculationThreshold</td><td>0c256</td><td>1D World Distance</td><td>If > 0, force visibility to be recalculated if the unit moves within a cell by more than this distance. </td></tr>
<tr><td>Type</td><td>Footprint</td><td>VisibilityType</td><td>Possible values are CenterPosition (measure range from the center) and  Footprint (measure range from the footprint) </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### Crushable
This actor is crushable.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>CrushSound</td><td></td><td>String</td><td>Sound to play when being crushed. </td></tr>
<tr><td>CrushClasses</td><td>infantry</td><td>Collection of CrushClass</td><td>Which crush classes does this actor belong to. </td></tr>
<tr><td>WarnProbability</td><td>75</td><td>Integer</td><td>Probability of mobile actors noticing and evading a crush attempt. </td></tr>
<tr><td>CrushedByFriendlies</td><td>False</td><td>Boolean</td><td>Will friendly units just crush me instead of pathing around. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### CustomSellValue
Allow a non-standard sell/repair value to avoid buy-sell exploits.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Value</td><td><em>(required)</em></td><td>Integer</td><td></td></tr>
</table>

### DamagedByTerrain
This actor receives damage from the given weapon when on the specified terrain type.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Damage</td><td><em>(required)</em></td><td>Integer</td><td>Amount of damage received per DamageInterval ticks. </td></tr>
<tr><td>DamageInterval</td><td>0</td><td>Integer</td><td>Delay between receiving damage. </td></tr>
<tr><td>DamageTypes</td><td></td><td>Collection of DamageType</td><td>Apply the damage using these damagetypes. </td></tr>
<tr><td>Terrain</td><td><em>(required)</em></td><td>Collection of String</td><td>Terrain types where the actor will take damage. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### DeliversCash
Donate money to actors with the `AcceptsDeliveredCash` trait.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Payload</td><td>500</td><td>Integer</td><td>The amount of cash the owner receives. </td></tr>
<tr><td>PlayerExperience</td><td>0</td><td>Integer</td><td>The amount of experience the donating player receives. </td></tr>
<tr><td>Type</td><td></td><td>String</td><td>Identifier checked against AcceptsDeliveredCash.ValidTypes. Only needed if the latter is not empty. </td></tr>
<tr><td>Sounds</td><td></td><td>Collection of String</td><td>Sound to play when delivering cash </td></tr>
<tr><td>Cursor</td><td>enter</td><td>String</td><td>Cursor to display when hovering over a valid actor to deliver cash to. </td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>TargetLineColor</td><td>FFFF00</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line. </td></tr>
</table>

### DeliversExperience
This actor can grant experience levels equal to it's own current level via entering to other actors with the `AcceptsDeliveredExperience` trait.

Requires trait: [`GainsExperience`](#gainsexperience).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>PlayerExperience</td><td>0</td><td>Integer</td><td>The amount of experience the donating player receives. </td></tr>
<tr><td>Type</td><td></td><td>String</td><td>Identifier checked against AcceptsDeliveredExperience.ValidTypes. Only needed if the latter is not empty. </td></tr>
<tr><td>Cursor</td><td>enter</td><td>String</td><td>Cursor to display when hovering over a valid actor to deliver experience to. </td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>TargetLineColor</td><td>FFFF00</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line. </td></tr>
</table>

### Demolishable
Handle demolitions from C4 explosives.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td></td><td>String</td><td>Condition to grant during demolition countdown. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### Demolition
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>DetonationDelay</td><td>45</td><td>Integer</td><td>Delay to demolish the target once the explosive device is planted. Measured in game ticks. Default is 1.8 seconds. </td></tr>
<tr><td>Flashes</td><td>3</td><td>Integer</td><td>Number of times to flash the target. </td></tr>
<tr><td>FlashesDelay</td><td>4</td><td>Integer</td><td>Delay before the flashing starts. </td></tr>
<tr><td>FlashInterval</td><td>4</td><td>Integer</td><td>Interval between each flash. </td></tr>
<tr><td>EnterBehaviour</td><td>Exit</td><td>EnterBehaviour</td><td>Behaviour when entering the structure. Possible values are Exit, Suicide, Dispose. </td></tr>
<tr><td>DamageTypes</td><td></td><td>Collection of DamageType</td><td>Types of damage that this trait causes. Leave empty for no damage types. </td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td>Voice string when planting explosive charges. </td></tr>
<tr><td>TargetLineColor</td><td>DC143C</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line. </td></tr>
<tr><td>TargetRelationships</td><td>Enemy, Neutral</td><td>PlayerRelationship</td><td></td></tr>
<tr><td>ForceTargetRelationships</td><td>Enemy, Neutral, Ally</td><td>PlayerRelationship</td><td></td></tr>
<tr><td>Cursor</td><td>c4</td><td>String</td><td>Cursor to display when hovering over a demolishable target. </td></tr>
</table>

### DetectCloaked
Actor can reveal Cloak actors in a specified range.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>CloakTypes</td><td>Cloak</td><td>Collection of CloakType</td><td>Specific cloak classifications I can reveal. </td></tr>
<tr><td>Range</td><td>5c0</td><td>1D World Distance</td><td></td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### EjectOnDeath
Eject a ground soldier or a paratrooper while in the air.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>PilotActor</td><td>E1</td><td>String</td><td>Name of the unit to eject. This actor type needs to have the Parachutable trait defined. </td></tr>
<tr><td>SuccessRate</td><td>50</td><td>Integer</td><td>Probability that the aircraft's pilot gets ejected once the aircraft is destroyed. </td></tr>
<tr><td>ChuteSound</td><td></td><td>String</td><td>Sound to play when ejecting the pilot from the aircraft. </td></tr>
<tr><td>EjectInAir</td><td>False</td><td>Boolean</td><td>Can a destroyed aircraft eject its pilot while it has not yet fallen to ground level? </td></tr>
<tr><td>EjectOnGround</td><td>False</td><td>Boolean</td><td>Can a destroyed aircraft eject its pilot when it falls to ground level? </td></tr>
<tr><td>AllowUnsuitableCell</td><td>False</td><td>Boolean</td><td>Risks stuck units when they don't have the Paratrooper trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### EngineerRepair
Can instantly repair other actors, but gets consumed afterwards.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Types</td><td></td><td>Collection of EngineerRepairType</td><td>Uses the "EngineerRepairable" trait to determine repairability. </td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>TargetLineColor</td><td>FFFF00</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line. </td></tr>
<tr><td>EnterBehaviour</td><td>Dispose</td><td>EnterBehaviour</td><td>Behaviour when entering the structure. Possible values are Exit, Suicide, Dispose. </td></tr>
<tr><td>ValidRelationships</td><td>Ally</td><td>PlayerRelationship</td><td>What player relationship the target's owner needs to be repaired by this actor. </td></tr>
<tr><td>RepairSound</td><td></td><td>String</td><td>Sound to play when repairing is done. </td></tr>
<tr><td>Cursor</td><td>goldwrench</td><td>String</td><td>Cursor to display when hovering over a valid actor to repair. </td></tr>
<tr><td>RepairBlockedCursor</td><td>goldwrench-blocked</td><td>String</td><td>Cursor to display when target actor has full health so it can't be repaired. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### EngineerRepairable
Eligible for instant repair.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Types</td><td></td><td>Collection of EngineerRepairType</td><td>Actors with these Types under EngineerRepair trait can repair me. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### EntersTunnels
This actor can interact with TunnelEntrances to move through TerrainTunnels.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>EnterCursor</td><td>enter</td><td>String</td><td>Cursor to display when able to enter target tunnel. </td></tr>
<tr><td>EnterBlockedCursor</td><td>enter-blocked</td><td>String</td><td>Cursor to display when unable to enter target tunnel. </td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>TargetLineColor</td><td>008000</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line while in tunnels. </td></tr>
<tr><td>RequireForceMoveCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition under which the regular (non-force) enter cursor is disabled. </td></tr>
</table>

### ExitsDebugOverlay
Displays `Exit` data for factories.

Requires trait: [`Exit`](#exit).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>DrawPerimiterCellVectors</td><td>True</td><td>Boolean</td><td>Should cell vectors be drawn for each perimeter cell? </td></tr>
<tr><td>DrawExitCellVectors</td><td>True</td><td>Boolean</td><td>Should cell vectors be drawn for each exit cell? </td></tr>
<tr><td>DrawSpawnOffsetLines</td><td>True</td><td>Boolean</td><td>Should lines be drawn for each exit (from spawn offset to the center of the exit cell)? </td></tr>
</table>

### ExperienceTrickler
Lets the actor gain experience in a set periodic time.

Requires trait: [`GainsExperience`](#gainsexperience).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Interval</td><td>50</td><td>Integer</td><td>Number of ticks to wait between giving experience. </td></tr>
<tr><td>InitialDelay</td><td>0</td><td>Integer</td><td>Number of ticks to wait before giving first experience. </td></tr>
<tr><td>Amount</td><td>15</td><td>Integer</td><td>Amount of experience to give each time. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### Explodes
This actor explodes when killed.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Weapon</td><td><em>(required)</em></td><td>String</td><td>Default weapon to use for explosion if ammo/payload is loaded. </td></tr>
<tr><td>EmptyWeapon</td><td>UnitExplode</td><td>String</td><td>Fallback weapon to use for explosion if empty (no ammo/payload). </td></tr>
<tr><td>LoadedChance</td><td>100</td><td>Integer</td><td>Chance that the explosion will use Weapon instead of EmptyWeapon when exploding, provided the actor has ammo/payload. </td></tr>
<tr><td>Chance</td><td>100</td><td>Integer</td><td>Chance that this actor will explode at all. </td></tr>
<tr><td>DamageThreshold</td><td>0</td><td>Integer</td><td>Health level at which actor will explode. </td></tr>
<tr><td>DeathTypes</td><td></td><td>Collection of DamageType</td><td>DeathType(s) that trigger the explosion. Leave empty to always trigger an explosion. </td></tr>
<tr><td>DamageSource</td><td>Self</td><td>DamageSource</td><td>Who is counted as source of damage for explosion. Possible values are Self and Killer. </td></tr>
<tr><td>Type</td><td>CenterPosition</td><td>ExplosionType</td><td>Possible values are CenterPosition (explosion at the actors' center) and  Footprint (explosion on each occupied cell). </td></tr>
<tr><td>Offset</td><td>0,0,0</td><td>3D World Vector</td><td>Offset of the explosion from the center of the exploding actor (or cell). </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ExplosionOnDamageTransition
This actor triggers an explosion on itself when transitioning to a specific damage state.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Weapon</td><td><em>(required)</em></td><td>String</td><td>Weapon to use for explosion. </td></tr>
<tr><td>DamageState</td><td>Heavy</td><td>DamageState</td><td>At which damage state explosion will trigger. </td></tr>
<tr><td>TriggerOnlyOnce</td><td>False</td><td>Boolean</td><td>Should the explosion only be triggered once? </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### GainsExperience
This actor's experience increases when it has killed a GivesExperience actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Conditions</td><td><em>(required)</em></td><td>Dictionary with Key: Integer, Value String</td><td>Condition to grant at each level. Key is the XP requirements for each level as a percentage of our own value. Value is the condition to grant. </td></tr>
<tr><td>LevelUpImage</td><td></td><td>String</td><td>Image for the level up sprite. </td></tr>
<tr><td>LevelUpSequence</td><td>levelup</td><td>String</td><td>Sequence for the level up sprite. Needs to be present on LevelUpImage. </td></tr>
<tr><td>LevelUpPalette</td><td>effect</td><td>String</td><td>Palette for the level up sprite. </td></tr>
<tr><td>ExperienceModifier</td><td>-1</td><td>Integer</td><td>Multiplier to apply to the Conditions keys. Defaults to the actor's value. </td></tr>
<tr><td>SuppressLevelupAnimation</td><td>True</td><td>Boolean</td><td>Should the level-up animation be suppressed when actor is created? </td></tr>
<tr><td>LevelUpNotification</td><td></td><td>String</td><td></td></tr>
</table>

### GivesBounty
When killed, this actor causes the attacking player to receive money.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Percentage</td><td>10</td><td>Integer</td><td>Percentage of the killed actor's Cost or CustomSellValue to be given. </td></tr>
<tr><td>ValidRelationships</td><td>Enemy, Neutral</td><td>PlayerRelationship</td><td>Player relationships the attacking player needs to receive the bounty. </td></tr>
<tr><td>ShowBounty</td><td>True</td><td>Boolean</td><td>Whether to show a floating text announcing the won bounty. </td></tr>
<tr><td>DeathTypes</td><td></td><td>Collection of DamageType</td><td>DeathTypes for which a bounty should be granted. Use an empty list (the default) to allow all DeathTypes. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### GivesCashOnCapture
Lets the actor grant cash when captured.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ShowTicks</td><td>True</td><td>Boolean</td><td>Whether to show the cash tick indicators rising from the actor. </td></tr>
<tr><td>DisplayDuration</td><td>30</td><td>Integer</td><td>How long to show the Amount tick indicator when enabled. </td></tr>
<tr><td>Amount</td><td>0</td><td>Integer</td><td>Amount of money awarded for capturing the actor. </td></tr>
<tr><td>CaptureTypes</td><td></td><td>Collection of CaptureType</td><td>Award cash only if the capturer's CaptureTypes overlap with these types. Leave empty to allow all types. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### GivesExperience
This actor gives experience to a GainsExperience actor when they are killed.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Experience</td><td>-1</td><td>Integer</td><td>If -1, use the value of the unit cost. </td></tr>
<tr><td>ValidRelationships</td><td>Enemy, Neutral</td><td>PlayerRelationship</td><td>Player relationships the attacking player needs to receive the experience. </td></tr>
<tr><td>ActorExperienceModifier</td><td>10000</td><td>Integer</td><td>Percentage of the `Experience` value that is being granted to the killing actor. </td></tr>
<tr><td>PlayerExperienceModifier</td><td>0</td><td>Integer</td><td>Percentage of the `Experience` value that is being granted to the player owning the killing actor. </td></tr>
</table>

### Guard
The player can give this unit the order to follow and protect friendly units with the Guardable trait.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>TargetLineColor</td><td>FF4500</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line. </td></tr>
</table>

### Guardable
This unit can be guarded (followed and protected) by a Guard unit.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Range</td><td>2c0</td><td>1D World Distance</td><td>Maximum range that guarding actors will maintain. </td></tr>
</table>

### Harvester
Requires trait: [`Mobile`](#mobile).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>DeliveryBuildings</td><td></td><td>Set of System.String[]</td><td></td></tr>
<tr><td>SearchForDeliveryBuildingDelay</td><td>125</td><td>Integer</td><td>How long (in ticks) to wait until (re-)checking for a nearby available DeliveryBuilding if not yet linked to one. </td></tr>
<tr><td>UnblockCell</td><td>0,4</td><td>2D Cell Vector</td><td>Cell to move to when automatically unblocking DeliveryBuilding. </td></tr>
<tr><td>Capacity</td><td>28</td><td>Integer</td><td>How much resources it can carry. </td></tr>
<tr><td>BaleLoadDelay</td><td>4</td><td>Integer</td><td></td></tr>
<tr><td>BaleUnloadDelay</td><td>4</td><td>Integer</td><td>How fast it can dump it's carryage. </td></tr>
<tr><td>BaleUnloadAmount</td><td>1</td><td>Integer</td><td>How many bales can it dump at once. </td></tr>
<tr><td>HarvestFacings</td><td>0</td><td>Integer</td><td></td></tr>
<tr><td>Resources</td><td></td><td>Set of System.String[]</td><td>Which resources it can harvest. </td></tr>
<tr><td>FullyLoadedSpeed</td><td>85</td><td>Integer</td><td>Percentage of maximum speed when fully loaded. </td></tr>
<tr><td>SearchOnCreation</td><td>True</td><td>Boolean</td><td>Automatically scan for resources when created. </td></tr>
<tr><td>SearchFromProcRadius</td><td>24</td><td>Integer</td><td>Initial search radius (in cells) from the refinery that created us. </td></tr>
<tr><td>SearchFromHarvesterRadius</td><td>12</td><td>Integer</td><td>Search radius (in cells) from the last harvest order location to find more resources. </td></tr>
<tr><td>WaitDuration</td><td>25</td><td>Integer</td><td>Interval to wait between searches when there are no resources nearby. </td></tr>
<tr><td>MaxUnloadQueue</td><td>3</td><td>Integer</td><td>Find a new refinery to unload at if more than this many harvesters are already waiting. </td></tr>
<tr><td>UnloadQueueCostModifier</td><td>12</td><td>Integer</td><td>The pathfinding cost penalty applied for each harvester waiting to unload at a refinery. </td></tr>
<tr><td>ResourceRefineryDirectionPenalty</td><td>200</td><td>Integer</td><td>The pathfinding cost penalty applied for cells directly away from the refinery. </td></tr>
<tr><td>QueueFullLoad</td><td>False</td><td>Boolean</td><td>Does the unit queue harvesting runs instead of individual harvest actions? </td></tr>
<tr><td>EmptyCondition</td><td></td><td>String</td><td>Condition to grant while empty. </td></tr>
<tr><td>HarvestVoice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>DeliverVoice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>HarvestLineColor</td><td>DC143C</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line of harvest orders. </td></tr>
<tr><td>DeliverLineColor</td><td>008000</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line of harvest orders. </td></tr>
<tr><td>EnterCursor</td><td>enter</td><td>String</td><td>Cursor to display when able to unload at target actor. </td></tr>
<tr><td>EnterBlockedCursor</td><td>enter-blocked</td><td>String</td><td>Cursor to display when unable to unload at target actor. </td></tr>
<tr><td>HarvestCursor</td><td>harvest</td><td>String</td><td>Cursor to display when ordering to harvest resources. </td></tr>
</table>

### Health
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>HP</td><td>0</td><td>Integer</td><td>HitPoints </td></tr>
<tr><td>NotifyAppliedDamage</td><td>True</td><td>Boolean</td><td>Trigger interfaces such as AnnounceOnKill? </td></tr>
<tr><td>EditorHealthDisplayOrder</td><td>2</td><td>Integer</td><td>Display order for the health slider in the map editor </td></tr>
</table>

### HitShape
Shape of actor for targeting and damage calculations.

Requires trait: [`BodyOrientation`](#bodyorientation).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Turret</td><td></td><td>String</td><td>Name of turret this shape is linked to. Leave empty to link shape to body. </td></tr>
<tr><td>TargetableOffsets</td><td>0,0,0</td><td>Collection of 3D World Vector</td><td>Create a targetable position for each offset listed here (relative to CenterPosition). </td></tr>
<tr><td>UseTargetableCellsOffsets</td><td>False</td><td>Boolean</td><td>Create a targetable position at the center of each occupied cell. Stacks with TargetableOffsets. </td></tr>
<tr><td>ArmorTypes</td><td></td><td>Collection of ArmorType</td><td>Defines which Armor types apply when the actor receives damage to this HitShape. If none specified, all armor types the actor has are valid. </td></tr>
<tr><td>Type</td><td></td><td>IHitShape</td><td>Engine comes with support for `Circle`, `Capsule`, `Polygon` and `Rectangle`. Defaults to `Circle` when left empty. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### Huntable
This actor can be targeted by the Hunt activity.

### Husk
Spawns remains of a husk actor with the correct facing.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>AllowedTerrain</td><td></td><td>Set of System.String[]</td><td></td></tr>
<tr><td>PreviewFacing</td><td>384</td><td>1D World Angle</td><td>Facing to use for actor previews (map editor, color picker, etc) </td></tr>
</table>

### IgnoresCloak
This actor does not care about any type of cloak its targets might have, regardless of distance.

### IgnoresDisguise
Allows automatic targeting of disguised actors.

### Immobile
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>OccupiesSpace</td><td>True</td><td>Boolean</td><td></td></tr>
</table>

### ScaredyCat
Makes the unit automatically run around when taking damage.

Requires trait: [`Mobile`](#mobile).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>PanicChance</td><td>100</td><td>Integer</td><td>Chance (out of 100) the unit has to enter panic mode when attacked. </td></tr>
<tr><td>PanicDuration</td><td>250</td><td>Integer</td><td>How long (in ticks) the actor should panic for. </td></tr>
<tr><td>PanicSpeedModifier</td><td>200</td><td>Integer</td><td>Panic movement speed as a percentage of the normal speed. </td></tr>
<tr><td>AttackPanicChance</td><td>20</td><td>Integer</td><td>Chance (out of 100) the unit has to enter panic mode when attacking. </td></tr>
<tr><td>AvoidTerrainTypes</td><td></td><td>Set of System.String[]</td><td>The terrain types that this actor should avoid running on to while panicking. </td></tr>
<tr><td>PanicSequencePrefix</td><td>panic-</td><td>String</td><td></td></tr>
</table>

### TakeCover
Make the unit go prone when under attack, in an attempt to reduce damage.

Requires trait: [`BodyOrientation`](#bodyorientation).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Duration</td><td>100</td><td>Integer</td><td>How long (in ticks) the actor remains prone. Negative values mean actor remains prone permanently. </td></tr>
<tr><td>SpeedModifier</td><td>50</td><td>Integer</td><td>Prone movement speed as a percentage of the normal speed. </td></tr>
<tr><td>DamageTriggers</td><td></td><td>Collection of DamageType</td><td>Damage types that trigger prone state. Defined on the warheads. If Duration is negative (permanent), you can leave this empty to trigger prone state immediately. </td></tr>
<tr><td>DamageModifiers</td><td></td><td>Dictionary with Key: String, Value Integer</td><td>Damage modifiers for each damage type (defined on the warheads) while the unit is prone. </td></tr>
<tr><td>ProneOffset</td><td>500,0,0</td><td>3D World Vector</td><td>Muzzle offset modifier to apply while prone. </td></tr>
<tr><td>ProneSequencePrefix</td><td>prone-</td><td>String</td><td>Sequence prefix to apply while prone. </td></tr>
<tr><td>Turret</td><td>primary</td><td>String</td><td></td></tr>
<tr><td>TurnSpeed</td><td>512</td><td>1D World Angle</td><td>Speed at which the turret turns. </td></tr>
<tr><td>InitialFacing</td><td>0</td><td>1D World Angle</td><td></td></tr>
<tr><td>RealignDelay</td><td>40</td><td>Integer</td><td>Number of ticks before turret is realigned. (-1 turns off realignment) </td></tr>
<tr><td>Offset</td><td>0,0,0</td><td>3D World Vector</td><td>Muzzle position relative to turret or body. (forward, right, up) triples </td></tr>
<tr><td>EditorTurretFacingDisplayOrder</td><td>4</td><td>Integer</td><td>Display order for the turret facing slider in the map editor </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### TerrainModifiesDamage
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>TerrainModifier</td><td><em>(required)</em></td><td>Dictionary with Key: String, Value Integer</td><td>Damage percentage for specific terrain types. 120 = 120%, 80 = 80%, etc. </td></tr>
<tr><td>ModifyHealing</td><td>False</td><td>Boolean</td><td>Modify healing damage? For example: A friendly medic. </td></tr>
</table>

### Interactable
Used to enable mouse interaction on actors that are not Selectable.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Bounds</td><td></td><td>Collection of 1D World Distance</td><td>Defines a custom rectangle for mouse interaction with the actor. If null, the engine will guess an appropriate size based on the With*Body trait. The first two numbers define the width and height of the rectangle as a world distance. The (optional) second two numbers define an x and y offset from the actor center. </td></tr>
<tr><td>DecorationBounds</td><td></td><td>Collection of 1D World Distance</td><td>Defines a custom rectangle for Decorations (e.g. the selection box). If null, Bounds will be used instead </td></tr>
</table>

### IsometricSelectable
This actor is selectable. Defines bounds of selectable area, selection class, selection priority and selection priority modifiers.

Requires trait: [`Building`](#building).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Bounds</td><td></td><td>Collection of Integer</td><td>Defines a custom rectangle for mouse interaction with the actor. If null, the engine will guess an appropriate size based on the building's footprint. The first two numbers define the width and depth of the footprint rectangle. The (optional) second two numbers define an x and y offset from the actor center. </td></tr>
<tr><td>Height</td><td>24</td><td>Integer</td><td>Height above the footprint for the top of the interaction rectangle. </td></tr>
<tr><td>DecorationBounds</td><td></td><td>Collection of Integer</td><td>Defines a custom rectangle for Decorations (e.g. the selection box). If null, Bounds will be used instead. </td></tr>
<tr><td>DecorationHeight</td><td>-1</td><td>Integer</td><td>Defines a custom height for Decorations (e.g. the selection box). If < 0, Height will be used instead. If Height is 0, this must be defined with a value greater than 0. </td></tr>
<tr><td>Priority</td><td>10</td><td>Integer</td><td></td></tr>
<tr><td>PriorityModifiers</td><td>None</td><td>SelectionPriorityModifiers</td><td>Allow selection priority to be modified using a hotkey. Valid values are None (priority is not affected by modifiers) Ctrl (priority is raised when Ctrl pressed) and Alt (priority is raised when Alt pressed). </td></tr>
<tr><td>Class</td><td></td><td>String</td><td>All units having the same selection class specified will be selected with select-by-type commands (e.g. double-click).  Defaults to the actor name when not defined or inherited. </td></tr>
<tr><td>Voice</td><td>Select</td><td>String</td><td></td></tr>
</table>

### JamsMissiles
This actor deflects missiles.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Range</td><td>0c0</td><td>1D World Distance</td><td>Range of the deflection. </td></tr>
<tr><td>DeflectionRelationships</td><td>Enemy, Neutral, Ally</td><td>PlayerRelationship</td><td>What player relationships are affected. </td></tr>
<tr><td>Chance</td><td>100</td><td>Integer</td><td>Chance of deflecting missiles. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### KillsSelf
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>RemoveInstead</td><td>False</td><td>Boolean</td><td>Remove the actor from the world (and destroy it) instead of killing it. </td></tr>
<tr><td>Delay</td><td>0</td><td>Collection of Integer</td><td>The amount of time (in ticks) before the actor dies. Two values indicate a range between which a random value is chosen. </td></tr>
<tr><td>DamageTypes</td><td></td><td>Collection of DamageType</td><td>Types of damage that this trait causes. Leave empty for no damage types. </td></tr>
<tr><td>GrantsCondition</td><td></td><td>String</td><td>The condition to grant moments before suiciding. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### MapEditorData
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>RequireTilesets</td><td></td><td>Set of System.String[]</td><td></td></tr>
<tr><td>ExcludeTilesets</td><td></td><td>Set of System.String[]</td><td></td></tr>
<tr><td>Categories</td><td></td><td>Collection of String</td><td></td></tr>
</table>

### Mobile
Unit is able to move.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Locomotor</td><td><em>(required)</em></td><td>String</td><td>Which Locomotor does this trait use. Must be defined on the World actor. </td></tr>
<tr><td>InitialFacing</td><td>0</td><td>1D World Angle</td><td></td></tr>
<tr><td>TurnSpeed</td><td>512</td><td>1D World Angle</td><td>Speed at which the actor turns. </td></tr>
<tr><td>Speed</td><td>1</td><td>Integer</td><td></td></tr>
<tr><td>AlwaysTurnInPlace</td><td>False</td><td>Boolean</td><td>If set to true, this unit will always turn in place instead of following a curved trajectory (like infantry). </td></tr>
<tr><td>Cursor</td><td>move</td><td>String</td><td>Cursor to display when a move order can be issued at target location. </td></tr>
<tr><td>TerrainCursors</td><td></td><td>Dictionary with Key: String, Value String</td><td>Cursor overrides to display for specific terrain types. A dictionary of [terrain type]: [cursor name]. </td></tr>
<tr><td>BlockedCursor</td><td>move-blocked</td><td>String</td><td>Cursor to display when a move order cannot be issued at target location. </td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>TargetLineColor</td><td>008000</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line for regular move orders. </td></tr>
<tr><td>PreviewFacing</td><td>384</td><td>1D World Angle</td><td>Facing to use for actor previews (map editor, color picker, etc) </td></tr>
<tr><td>EditorFacingDisplayOrder</td><td>3</td><td>Integer</td><td>Display order for the facing slider in the map editor </td></tr>
<tr><td>RequireForceMoveCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition under which the regular (non-force) move cursor is disabled. </td></tr>
<tr><td>ImmovableCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition under which this actor cannot be nudged by other actors. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### AlwaysVisible
The actor is always considered visible for targeting and rendering purposes.

### FrozenUnderFog
This actor will remain visible (but not updated visually) under fog, once discovered.

Requires trait: [`Building`](#building).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>AlwaysVisibleRelationships</td><td>Ally</td><td>PlayerRelationship</td><td>Players with these relationships can always see the actor. </td></tr>
</table>

### HiddenUnderFog
The actor stays invisible under fog of war.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>AlwaysVisibleRelationships</td><td>Ally</td><td>PlayerRelationship</td><td>Players with these relationships can always see the actor. </td></tr>
<tr><td>Type</td><td>Footprint</td><td>VisibilityType</td><td>Possible values are CenterPosition (reveal when the center is visible) and  Footprint (reveal when any footprint cell is visible). </td></tr>
</table>

### HiddenUnderShroud
The actor stays invisible under the shroud.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>AlwaysVisibleRelationships</td><td>Ally</td><td>PlayerRelationship</td><td>Players with these relationships can always see the actor. </td></tr>
<tr><td>Type</td><td>Footprint</td><td>VisibilityType</td><td>Possible values are CenterPosition (reveal when the center is visible) and  Footprint (reveal when any footprint cell is visible). </td></tr>
</table>

### WithColoredOverlay
Display a colored overlay when a timed condition is active.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Color</td><td>80000080</td><td>Color (RRGGBB[AA] notation)</td><td>Color to overlay. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### CashTricklerMultiplier
Modifies the cash given by cash tricker traits of this actor.

Requires trait: [`CashTrickler`](#cashtrickler).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Modifier</td><td><em>(required)</em></td><td>Integer</td><td>Percentage modifier to apply. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### CreatesShroudMultiplier
Modifies the shroud range created by this actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Modifier</td><td><em>(required)</em></td><td>Integer</td><td>Percentage modifier to apply. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### DamageMultiplier
Modifies the damage applied to this actor.
Use 0 to make actor invulnerable.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Modifier</td><td><em>(required)</em></td><td>Integer</td><td>Percentage modifier to apply. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### DetectCloakedMultiplier
Modifies the cloak detection range of this actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Modifier</td><td><em>(required)</em></td><td>Integer</td><td>Percentage modifier to apply. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### FirepowerMultiplier
Modifies the damage applied by this actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Modifier</td><td><em>(required)</em></td><td>Integer</td><td>Percentage modifier to apply. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### GainsExperienceMultiplier
Modifies the experience gathered by this actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Modifier</td><td><em>(required)</em></td><td>Integer</td><td>Percentage modifier to apply. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### GivesExperienceMultiplier
Modifies the experience given by this actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Modifier</td><td><em>(required)</em></td><td>Integer</td><td>Percentage modifier to apply. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### HandicapDamageMultiplier
Modifies the damage applied to this actor based on the owner's handicap.

### HandicapFirepowerMultiplier
Modifies the damage applied by this actor based on the owner's handicap.

### HandicapProductionTimeMultiplier
Modifies the production time of this actor based on the producer's handicap.

### InaccuracyMultiplier
Modifies the inaccuracy of weapons fired by this actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Modifier</td><td><em>(required)</em></td><td>Integer</td><td>Percentage modifier to apply. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### PowerMultiplier
Modifies the power usage/output of this actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Modifier</td><td><em>(required)</em></td><td>Integer</td><td>Percentage modifier to apply. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ProductionCostMultiplier
Modifies the production cost of this actor for a specific queue or when a prerequisite is granted.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Multiplier</td><td>100</td><td>Integer</td><td>Percentage modifier to apply. </td></tr>
<tr><td>Prerequisites</td><td></td><td>Collection of String</td><td>Only apply this cost change if owner has these prerequisites. </td></tr>
<tr><td>Queue</td><td></td><td>Set of System.String[]</td><td>Queues that this cost will apply. </td></tr>
</table>

### ProductionTimeMultiplier
Modifies the production time of this actor for a specific queue or when a prerequisite is granted.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Multiplier</td><td>100</td><td>Integer</td><td>Percentage modifier to apply. </td></tr>
<tr><td>Prerequisites</td><td></td><td>Collection of String</td><td>Only apply this time change if owner has these prerequisites. </td></tr>
<tr><td>Queue</td><td></td><td>Set of System.String[]</td><td>Queues that this time will apply. </td></tr>
</table>

### RangeMultiplier
Modifies the range of weapons fired by this actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Modifier</td><td><em>(required)</em></td><td>Integer</td><td>Percentage modifier to apply. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ReloadAmmoDelayMultiplier
Modifies the reload time of ammo pools on this actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Modifier</td><td><em>(required)</em></td><td>Integer</td><td>Percentage modifier to apply. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ReloadDelayMultiplier
Modifies the reload time of weapons fired by this actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Modifier</td><td><em>(required)</em></td><td>Integer</td><td>Percentage modifier to apply. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ResourceValueMultiplier
Modifies the value of resources delivered to this actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Modifier</td><td><em>(required)</em></td><td>Integer</td><td>Percentage modifier to apply. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### RevealsShroudMultiplier
Modifies the shroud range revealed by this actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Modifier</td><td><em>(required)</em></td><td>Integer</td><td>Percentage modifier to apply. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### SpeedMultiplier
Modifies the movement speed of this actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Modifier</td><td><em>(required)</em></td><td>Integer</td><td>Percentage modifier to apply. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### MustBeDestroyed
Actors with this trait must be destroyed for a game to end.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>RequiredForShortGame</td><td>False</td><td>Boolean</td><td>In a short game only actors that have this value set to true need to be destroyed. </td></tr>
</table>

### OwnerLostAction
Perform an action when the actor's owner is defeated.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Action</td><td><em>(required)</em></td><td>OwnerLostActionType</td><td>What does this unit do when its owner loses. Allowed values are 'ChangeOwner', 'Dispose', 'Kill' </td></tr>
<tr><td>Owner</td><td>Neutral</td><td>String</td><td>Map player to use when 'Action' is 'ChangeOwner'. </td></tr>
<tr><td>DeathTypes</td><td></td><td>Collection of DamageType</td><td>The deathtypes used when 'Action' is 'Kill'. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### CloakPaletteEffect

### FlashPaletteEffect
Used for bursted one-colored whole screen effects. Add this to the world actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ExcludePalettes</td><td>cursor, chrome, colorpicker, fog, shroud</td><td>Set of System.String[]</td><td></td></tr>
<tr><td>Length</td><td>20</td><td>Integer</td><td>Measured in ticks. </td></tr>
<tr><td>Color</td><td>FFFFFF</td><td>Color (RRGGBB[AA] notation)</td><td></td></tr>
<tr><td>Type</td><td></td><td>String</td><td>Set this when using multiple independent flash effects. </td></tr>
</table>

### GlobalLightingPaletteEffect
Used for day/night effects.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ExcludePalettes</td><td>cursor, chrome, colorpicker, fog, shroud, alpha</td><td>Set of System.String[]</td><td>Do not modify graphics that use any palette in this list. </td></tr>
<tr><td>ExcludePalettePrefixes</td><td></td><td>Set of System.String[]</td><td>Do not modify graphics that start with these letters. </td></tr>
<tr><td>Red</td><td>1</td><td>Real Number</td><td></td></tr>
<tr><td>Green</td><td>1</td><td>Real Number</td><td></td></tr>
<tr><td>Blue</td><td>1</td><td>Real Number</td><td></td></tr>
<tr><td>Ambient</td><td>1</td><td>Real Number</td><td></td></tr>
</table>

### MenuPaletteEffect
Fades the world from/to black at the start/end of the game, and can (optionally) desaturate the world
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>FadeLength</td><td>10</td><td>Integer</td><td>Time (in ticks) to fade between states </td></tr>
<tr><td>Effect</td><td>None</td><td>EffectType</td><td>Effect style to fade to during gameplay. Accepts values of None or Desaturated. </td></tr>
<tr><td>MenuEffect</td><td>None</td><td>EffectType</td><td>Effect style to fade to when opening the in-game menu. Accepts values of None, Black or Desaturated. </td></tr>
</table>

### RotationPaletteEffect
Palette effect used for sprinkle "animations".
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Palettes</td><td></td><td>Set of System.String[]</td><td>Defines to which palettes this effect should be applied to. If none specified, it applies to all palettes not explicitly excluded. </td></tr>
<tr><td>Tilesets</td><td></td><td>Set of System.String[]</td><td>Defines for which tileset IDs this effect should be loaded. If none specified, it applies to all tileset IDs not explicitly excluded. </td></tr>
<tr><td>ExcludePalettes</td><td></td><td>Set of System.String[]</td><td>Defines which palettes should be excluded from this effect. </td></tr>
<tr><td>ExcludeTilesets</td><td></td><td>Set of System.String[]</td><td>Don't apply the effect for these tileset IDs. </td></tr>
<tr><td>RotationBase</td><td>96</td><td>Integer</td><td>Palette index of first RotationRange color. </td></tr>
<tr><td>RotationRange</td><td>7</td><td>Integer</td><td>Range of colors to rotate. </td></tr>
<tr><td>RotationStep</td><td>0.25</td><td>Real Number</td><td>Step towards next color index per tick. </td></tr>
</table>

### ColorPickerPalette
Create a color picker palette from another palette.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Name</td><td><em>(required)</em></td><td>String</td><td>Internal palette name. </td></tr>
<tr><td>BasePalette</td><td><em>(required)</em></td><td>String</td><td>The name of the palette to base off. </td></tr>
<tr><td>RemapIndex</td><td><em>(required)</em></td><td>Collection of Integer</td><td>Remap these indices to player colors. </td></tr>
<tr><td>AllowModifiers</td><td>True</td><td>Boolean</td><td>Allow palette modifiers to change the palette. </td></tr>
</table>

### FixedColorPalette
Add this to the World actor definition.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Base</td><td>terrain</td><td>String</td><td>The name of the palette to base off. </td></tr>
<tr><td>Name</td><td>resources</td><td>String</td><td>The name of the resulting palette </td></tr>
<tr><td>RemapIndex</td><td></td><td>Collection of Integer</td><td>Remap these indices to pre-defined colors. </td></tr>
<tr><td>Color</td><td>00000000</td><td>Color (RRGGBB[AA] notation)</td><td>The fixed color to remap. </td></tr>
<tr><td>AllowModifiers</td><td>True</td><td>Boolean</td><td>Allow palette modifiers to change the palette. </td></tr>
</table>

### IndexedPalette
Define a palette by swapping palette indices.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Name</td><td><em>(required)</em></td><td>String</td><td>Internal palette name </td></tr>
<tr><td>BasePalette</td><td></td><td>String</td><td>The name of the palette to base off. </td></tr>
<tr><td>Index</td><td><em>(required)</em></td><td>Collection of Integer</td><td>Indices from BasePalette to be swapped with ReplaceIndex. </td></tr>
<tr><td>ReplaceIndex</td><td><em>(required)</em></td><td>Collection of Integer</td><td>Indices from BasePalette to replace from Index. </td></tr>
<tr><td>AllowModifiers</td><td>True</td><td>Boolean</td><td>Allow palette modifiers to change the palette. </td></tr>
</table>

### IndexedPlayerPalette
Define a player palette by swapping palette indices.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>BasePalette</td><td></td><td>String</td><td>The name of the palette to base off. </td></tr>
<tr><td>BaseName</td><td>player</td><td>String</td><td>The prefix for the resulting player palettes </td></tr>
<tr><td>RemapIndex</td><td></td><td>Collection of Integer</td><td>Remap these indices to player colors. </td></tr>
<tr><td>AllowModifiers</td><td>True</td><td>Boolean</td><td>Allow palette modifiers to change the palette. </td></tr>
<tr><td>PlayerIndex</td><td></td><td>Dictionary with Key: String, Value Collection of Integer</td><td></td></tr>
</table>

### PaletteFromEmbeddedSpritePalette
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Name</td><td><em>(required)</em></td><td>String</td><td>Internal palette name </td></tr>
<tr><td>Image</td><td><em>(required)</em></td><td>String</td><td>Sequence image holding the palette definition </td></tr>
<tr><td>Sequence</td><td><em>(required)</em></td><td>String</td><td>Sequence holding the palette definition </td></tr>
<tr><td>AllowModifiers</td><td>True</td><td>Boolean</td><td>Allow palette modifiers to change the palette. </td></tr>
<tr><td>CursorPalette</td><td>False</td><td>Boolean</td><td>Whether this palette is available for cursors. </td></tr>
</table>

### PaletteFromFile
Load VGA palette (.pal) registers.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Name</td><td><em>(required)</em></td><td>String</td><td>internal palette name </td></tr>
<tr><td>Tileset</td><td></td><td>String</td><td>If defined, load the palette only for this tileset. </td></tr>
<tr><td>Filename</td><td><em>(required)</em></td><td>String</td><td>filename to load </td></tr>
<tr><td>TransparentIndex</td><td>0</td><td>Collection of Integer</td><td>Map listed indices to transparent. Ignores previous color. </td></tr>
<tr><td>ShadowIndex</td><td></td><td>Collection of Integer</td><td>Map listed indices to shadow. Ignores previous color. </td></tr>
<tr><td>AllowModifiers</td><td>True</td><td>Boolean</td><td></td></tr>
<tr><td>CursorPalette</td><td>False</td><td>Boolean</td><td>Whether this palette is available for cursors. </td></tr>
</table>

### PaletteFromGimpOrJascFile
Load a GIMP .gpl or JASC .pal palette file. Supports per-color alpha.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Name</td><td><em>(required)</em></td><td>String</td><td>Palette name used internally. </td></tr>
<tr><td>Tilesets</td><td></td><td>Set of System.String[]</td><td>Defines for which tileset IDs this palette should be loaded. If none specified, it applies to all tileset IDs not explicitly excluded. </td></tr>
<tr><td>ExcludeTilesets</td><td></td><td>Set of System.String[]</td><td>Don't load palette for these tileset IDs. </td></tr>
<tr><td>Filename</td><td><em>(required)</em></td><td>String</td><td>Name of the file to load. </td></tr>
<tr><td>Premultiply</td><td>True</td><td>Boolean</td><td>Premultiply colors with their alpha values. </td></tr>
<tr><td>AllowModifiers</td><td>True</td><td>Boolean</td><td></td></tr>
<tr><td>TransparentIndex</td><td>0</td><td>Integer</td><td>Index set to be fully transparent/invisible. </td></tr>
<tr><td>CursorPalette</td><td>False</td><td>Boolean</td><td>Whether this palette is available for cursors. </td></tr>
</table>

### PaletteFromPaletteWithAlpha
Create a palette by applying alpha transparency to another palette.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Name</td><td><em>(required)</em></td><td>String</td><td>Internal palette name </td></tr>
<tr><td>BasePalette</td><td><em>(required)</em></td><td>String</td><td>The name of the palette to base off. </td></tr>
<tr><td>AllowModifiers</td><td>True</td><td>Boolean</td><td>Allow palette modifiers to change the palette. </td></tr>
<tr><td>Alpha</td><td>1</td><td>Real Number</td><td>Alpha component that is applied to the base palette. </td></tr>
<tr><td>Premultiply</td><td>True</td><td>Boolean</td><td>Premultiply color by the alpha component. </td></tr>
</table>

### PaletteFromPlayerPaletteWithAlpha
Create player palettes by applying alpha transparency to another player palette.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>BaseName</td><td><em>(required)</em></td><td>String</td><td>The prefix for the resulting player palettes </td></tr>
<tr><td>BasePalette</td><td><em>(required)</em></td><td>String</td><td>The name of the player palette to base off. </td></tr>
<tr><td>AllowModifiers</td><td>True</td><td>Boolean</td><td>Allow palette modifiers to change the palette. </td></tr>
<tr><td>Alpha</td><td>1</td><td>Real Number</td><td>Alpha component that is applied to the base palette. </td></tr>
<tr><td>Premultiply</td><td>True</td><td>Boolean</td><td>Premultiply color by the alpha component. </td></tr>
</table>

### PaletteFromPng
Load a PNG and use its embedded palette.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Name</td><td><em>(required)</em></td><td>String</td><td>Internal palette name </td></tr>
<tr><td>Tileset</td><td></td><td>String</td><td>If defined, load the palette only for this tileset. </td></tr>
<tr><td>Filename</td><td><em>(required)</em></td><td>String</td><td>Filename to load </td></tr>
<tr><td>ShadowIndex</td><td></td><td>Collection of Integer</td><td>Map listed indices to shadow. Ignores previous color. </td></tr>
<tr><td>AllowModifiers</td><td>True</td><td>Boolean</td><td></td></tr>
<tr><td>CursorPalette</td><td>False</td><td>Boolean</td><td>Whether this palette is available for cursors. </td></tr>
</table>

### PaletteFromRGBA
Creates a single color palette without any base palette file.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Name</td><td><em>(required)</em></td><td>String</td><td>internal palette name </td></tr>
<tr><td>Tileset</td><td></td><td>String</td><td>If defined, load the palette only for this tileset. </td></tr>
<tr><td>R</td><td>0</td><td>Integer</td><td>red color component </td></tr>
<tr><td>G</td><td>0</td><td>Integer</td><td>green color component </td></tr>
<tr><td>B</td><td>0</td><td>Integer</td><td>blue color component </td></tr>
<tr><td>A</td><td>255</td><td>Integer</td><td>alpha channel (transparency) </td></tr>
<tr><td>AllowModifiers</td><td>True</td><td>Boolean</td><td></td></tr>
<tr><td>TransparentIndex</td><td>0</td><td>Integer</td><td>Index set to be fully transparent/invisible. </td></tr>
</table>

### PlayerColorPalette
Add this to the World actor definition.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>BasePalette</td><td></td><td>String</td><td>The name of the palette to base off. </td></tr>
<tr><td>BaseName</td><td>player</td><td>String</td><td>The prefix for the resulting player palettes </td></tr>
<tr><td>RemapIndex</td><td></td><td>Collection of Integer</td><td>Remap these indices to player colors. </td></tr>
<tr><td>AllowModifiers</td><td>True</td><td>Boolean</td><td>Allow palette modifiers to change the palette. </td></tr>
</table>

### Parachutable
Can be paradropped by a ParaDrop actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>KilledOnImpassableTerrain</td><td>True</td><td>Boolean</td><td>If we land on invalid terrain for my actor type should we be killed? </td></tr>
<tr><td>DamageTypes</td><td></td><td>Collection of DamageType</td><td>Types of damage that this trait causes to self when 'KilledOnImpassableTerrain' is true. Leave empty for no damage types. </td></tr>
<tr><td>Image</td><td>explosion</td><td>String</td><td>Image where Ground/WaterCorpseSequence is looked up. </td></tr>
<tr><td>GroundCorpseSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>GroundCorpsePalette</td><td>effect</td><td>String</td><td></td></tr>
<tr><td>GroundImpactSound</td><td></td><td>String</td><td></td></tr>
<tr><td>WaterCorpseSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>WaterCorpsePalette</td><td>effect</td><td>String</td><td></td></tr>
<tr><td>WaterTerrainTypes</td><td>Water</td><td>Set of System.String[]</td><td>Terrain types on which to display WaterCorpseSequence. </td></tr>
<tr><td>WaterImpactSound</td><td></td><td>String</td><td></td></tr>
<tr><td>FallRate</td><td>13</td><td>Integer</td><td></td></tr>
<tr><td>ParachutingCondition</td><td></td><td>String</td><td>The condition to grant to self while parachuting. </td></tr>
</table>

### ParaDrop
This unit can spawn and eject other actors while flying.

Requires trait: [`Cargo`](#cargo).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>DropRange</td><td>4c0</td><td>1D World Distance</td><td>Distance around the drop-point to unload troops. </td></tr>
<tr><td>DropInterval</td><td>5</td><td>Integer</td><td>Wait at least this many ticks between each drop. </td></tr>
<tr><td>ChuteSound</td><td></td><td>String</td><td>Sound to play when dropping. </td></tr>
</table>

### Passenger
This actor can enter Cargo actors.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>CargoType</td><td></td><td>String</td><td></td></tr>
<tr><td>CustomPipType</td><td></td><td>String</td><td>If defined, use a custom pip type defined on the transport's WithCargoPipsDecoration.CustomPipSequences list. </td></tr>
<tr><td>Weight</td><td>1</td><td>Integer</td><td></td></tr>
<tr><td>CargoCondition</td><td></td><td>String</td><td>The condition to grant to when this actor is loaded inside any transport. </td></tr>
<tr><td>CargoConditions</td><td></td><td>Dictionary with Key: String, Value String</td><td>Conditions to grant when this actor is loaded inside specified transport. A dictionary of [actor id]: [condition]. </td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>TargetLineColor</td><td>008000</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line. </td></tr>
<tr><td>RequireForceMoveCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition under which the regular (non-force) enter cursor is disabled. </td></tr>
<tr><td>EnterCursor</td><td>enter</td><td>String</td><td>Cursor to display when able to enter target actor. </td></tr>
<tr><td>EnterBlockedCursor</td><td>enter-blocked</td><td>String</td><td>Cursor to display when unable to enter target actor. </td></tr>
</table>

### AllyRepair
Attach this to the player actor to allow building repair by team mates.

### BaseAttackNotifier
Plays an audio notification and shows a radar ping when a building is attacked.
Attach this to the player actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>NotifyInterval</td><td>30000</td><td>Integer</td><td>Minimum duration (in milliseconds) between notification events. </td></tr>
<tr><td>RadarPingColor</td><td>FF0000</td><td>Color (RRGGBB[AA] notation)</td><td></td></tr>
<tr><td>RadarPingDuration</td><td>250</td><td>Integer</td><td>Length of time (in ticks) to display a location ping in the minimap. </td></tr>
<tr><td>Notification</td><td>BaseAttack</td><td>String</td><td>The audio notification type to play. </td></tr>
<tr><td>AllyNotification</td><td></td><td>String</td><td>The audio notification to play to allies when under attack. Won't play a notification to allies if this is null. </td></tr>
</table>

### ClassicParallelProductionQueue
Attach this to the player actor (not a building!) to define a new shared build queue.
Will only work together with the Production: trait on the actor that actually does the production.
You will also want to add PrimaryBuildings: to let the user choose where new units should exit.
The production speed depends on the number of production buildings and units queued at the same time.

Requires traits: [`PlayerResources`](#playerresources), [`TechTree`](#techtree).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>SpeedUp</td><td>False</td><td>Boolean</td><td>If you build more actors of the same type, the same queue will get its build time lowered for every actor produced there. </td></tr>
<tr><td>BuildingCountBuildTimeMultipliers</td><td>100, 85, 75, 65, 60, 55, 50</td><td>Collection of Integer</td><td>Every time another production building of the same queue is constructed, the build times of all actors in the queue modified by a percentage of the original time. </td></tr>
<tr><td>ParallelPenaltyBuildTimeMultipliers</td><td>100, 116, 133, 150, 166, 183, 200, 216, 233, 250</td><td>Collection of Integer</td><td>Build time modifier multiplied by the number of parallel production for producing different actors at the same time. </td></tr>
<tr><td>Type</td><td><em>(required)</em></td><td>String</td><td>What kind of production will be added (e.g. Building, Infantry, Vehicle, ...) </td></tr>
<tr><td>DisplayOrder</td><td>0</td><td>Integer</td><td>The value used when ordering this for display (e.g. in the Spectator UI). </td></tr>
<tr><td>Group</td><td></td><td>String</td><td>Group queues from separate buildings together into the same tab. </td></tr>
<tr><td>Factions</td><td></td><td>Set of System.String[]</td><td>Only enable this queue for certain factions. </td></tr>
<tr><td>Sticky</td><td>True</td><td>Boolean</td><td>Should the prerequisite remain enabled if the owner changes? </td></tr>
<tr><td>DisallowPaused</td><td>False</td><td>Boolean</td><td>Should right clicking on the icon instantly cancel the production instead of putting it on hold? </td></tr>
<tr><td>BuildDurationModifier</td><td>100</td><td>Integer</td><td>This percentage value is multiplied with actor cost to translate into build time (lower means faster). </td></tr>
<tr><td>ItemLimit</td><td>999</td><td>Integer</td><td>Maximum number of a single actor type that can be queued (0 = infinite). </td></tr>
<tr><td>QueueLimit</td><td>0</td><td>Integer</td><td>Maximum number of items that can be queued across all actor types (0 = infinite). </td></tr>
<tr><td>LowPowerModifier</td><td>100</td><td>Integer</td><td>The build time is multiplied with this percentage on low power. </td></tr>
<tr><td>InfiniteBuildLimit</td><td>-1</td><td>Integer</td><td>Production items that have more than this many items in the queue will be produced in a loop. </td></tr>
<tr><td>ReadyAudio</td><td></td><td>String</td><td>Notification played when production is complete. The filename of the audio is defined per faction in notifications.yaml. </td></tr>
<tr><td>BlockedAudio</td><td></td><td>String</td><td>Notification played when you can't train another actor when the build limit exceeded or the exit is jammed. The filename of the audio is defined per faction in notifications.yaml. </td></tr>
<tr><td>LimitedAudio</td><td></td><td>String</td><td>Notification played when you can't queue another actor when the queue length limit is exceeded. The filename of the audio is defined per faction in notifications.yaml. </td></tr>
<tr><td>QueuedAudio</td><td></td><td>String</td><td>Notification played when user clicks on the build palette icon. The filename of the audio is defined per faction in notifications.yaml. </td></tr>
<tr><td>OnHoldAudio</td><td></td><td>String</td><td>Notification played when player right-clicks on the build palette icon. The filename of the audio is defined per faction in notifications.yaml. </td></tr>
<tr><td>CancelledAudio</td><td></td><td>String</td><td>Notification played when player right-clicks on a build palette icon that is already on hold. The filename of the audio is defined per faction in notifications.yaml. </td></tr>
</table>

### ClassicProductionQueue
Attach this to the player actor (not a building!) to define a new shared build queue.
Will only work together with the Production: trait on the actor that actually does the production.
You will also want to add PrimaryBuildings: to let the user choose where new units should exit.

Requires traits: [`PlayerResources`](#playerresources), [`TechTree`](#techtree).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>SpeedUp</td><td>False</td><td>Boolean</td><td>If you build more actors of the same type, the same queue will get its build time lowered for every actor produced there. </td></tr>
<tr><td>BuildTimeSpeedReduction</td><td>100, 85, 75, 65, 60, 55, 50</td><td>Collection of Integer</td><td>Every time another production building of the same queue is constructed, the build times of all actors in the queue decreased by a percentage of the original time. </td></tr>
<tr><td>Type</td><td><em>(required)</em></td><td>String</td><td>What kind of production will be added (e.g. Building, Infantry, Vehicle, ...) </td></tr>
<tr><td>DisplayOrder</td><td>0</td><td>Integer</td><td>The value used when ordering this for display (e.g. in the Spectator UI). </td></tr>
<tr><td>Group</td><td></td><td>String</td><td>Group queues from separate buildings together into the same tab. </td></tr>
<tr><td>Factions</td><td></td><td>Set of System.String[]</td><td>Only enable this queue for certain factions. </td></tr>
<tr><td>Sticky</td><td>True</td><td>Boolean</td><td>Should the prerequisite remain enabled if the owner changes? </td></tr>
<tr><td>DisallowPaused</td><td>False</td><td>Boolean</td><td>Should right clicking on the icon instantly cancel the production instead of putting it on hold? </td></tr>
<tr><td>BuildDurationModifier</td><td>100</td><td>Integer</td><td>This percentage value is multiplied with actor cost to translate into build time (lower means faster). </td></tr>
<tr><td>ItemLimit</td><td>999</td><td>Integer</td><td>Maximum number of a single actor type that can be queued (0 = infinite). </td></tr>
<tr><td>QueueLimit</td><td>0</td><td>Integer</td><td>Maximum number of items that can be queued across all actor types (0 = infinite). </td></tr>
<tr><td>LowPowerModifier</td><td>100</td><td>Integer</td><td>The build time is multiplied with this percentage on low power. </td></tr>
<tr><td>InfiniteBuildLimit</td><td>-1</td><td>Integer</td><td>Production items that have more than this many items in the queue will be produced in a loop. </td></tr>
<tr><td>ReadyAudio</td><td></td><td>String</td><td>Notification played when production is complete. The filename of the audio is defined per faction in notifications.yaml. </td></tr>
<tr><td>BlockedAudio</td><td></td><td>String</td><td>Notification played when you can't train another actor when the build limit exceeded or the exit is jammed. The filename of the audio is defined per faction in notifications.yaml. </td></tr>
<tr><td>LimitedAudio</td><td></td><td>String</td><td>Notification played when you can't queue another actor when the queue length limit is exceeded. The filename of the audio is defined per faction in notifications.yaml. </td></tr>
<tr><td>QueuedAudio</td><td></td><td>String</td><td>Notification played when user clicks on the build palette icon. The filename of the audio is defined per faction in notifications.yaml. </td></tr>
<tr><td>OnHoldAudio</td><td></td><td>String</td><td>Notification played when player right-clicks on the build palette icon. The filename of the audio is defined per faction in notifications.yaml. </td></tr>
<tr><td>CancelledAudio</td><td></td><td>String</td><td>Notification played when player right-clicks on a build palette icon that is already on hold. The filename of the audio is defined per faction in notifications.yaml. </td></tr>
</table>

### ConquestVictoryConditions
Requires trait: [`MissionObjectives`](#missionobjectives).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>NotificationDelay</td><td>1500</td><td>Integer</td><td>Delay for the end game notification in milliseconds. </td></tr>
<tr><td>Objective</td><td>Destroy all opposition!</td><td>String</td><td>Description of the objective. </td></tr>
<tr><td>SuppressNotifications</td><td>False</td><td>Boolean</td><td>Disable the win/loss messages and audio notifications? </td></tr>
</table>

### DeveloperMode
Attach this to the player actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>CheckboxLabel</td><td>Debug Menu</td><td>String</td><td>Descriptive label for the developer mode checkbox in the lobby. </td></tr>
<tr><td>CheckboxDescription</td><td>Enables cheats and developer commands</td><td>String</td><td>Tooltip description for the developer mode checkbox in the lobby. </td></tr>
<tr><td>CheckboxEnabled</td><td>False</td><td>Boolean</td><td>Default value of the developer mode checkbox in the lobby. </td></tr>
<tr><td>CheckboxLocked</td><td>False</td><td>Boolean</td><td>Prevent the developer mode state from being changed in the lobby. </td></tr>
<tr><td>CheckboxVisible</td><td>True</td><td>Boolean</td><td>Whether to display the developer mode checkbox in the lobby. </td></tr>
<tr><td>CheckboxDisplayOrder</td><td>0</td><td>Integer</td><td>Display order for the developer mode checkbox in the lobby. </td></tr>
<tr><td>Cash</td><td>20000</td><td>Integer</td><td>Default cash bonus granted by the give cash cheat. </td></tr>
<tr><td>ResourceGrowth</td><td>100</td><td>Integer</td><td>Growth steps triggered by the grow resources button. </td></tr>
<tr><td>FastBuild</td><td>False</td><td>Boolean</td><td>Enable the fast build cheat by default. </td></tr>
<tr><td>FastCharge</td><td>False</td><td>Boolean</td><td>Enable the fast support powers cheat by default. </td></tr>
<tr><td>DisableShroud</td><td>False</td><td>Boolean</td><td>Enable the disable visibility cheat by default. </td></tr>
<tr><td>UnlimitedPower</td><td>False</td><td>Boolean</td><td>Enable the unlimited power cheat by default. </td></tr>
<tr><td>BuildAnywhere</td><td>False</td><td>Boolean</td><td>Enable the build anywhere cheat by default. </td></tr>
<tr><td>PathDebug</td><td>False</td><td>Boolean</td><td>Enable the path debug overlay by default. </td></tr>
</table>

### DummyBot
A placeholder bot that doesn't do anything.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Name</td><td>Unnamed Bot</td><td>String</td><td>Human-readable name this bot uses. </td></tr>
<tr><td>Type</td><td><em>(required)</em></td><td>String</td><td>Internal id for this bot. </td></tr>
</table>

### EnemyWatcher
Tracks neutral and enemy actors' visibility and notifies the player.
Attach this to the player actor. The actors to track need the 'AnnounceOnSeen' trait.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ScanInterval</td><td>25</td><td>Integer</td><td>Interval in ticks between scanning for enemies. </td></tr>
<tr><td>NotificationInterval</td><td>750</td><td>Integer</td><td>Minimal ticks in-between notifications. </td></tr>
</table>

### GrantConditionOnPrerequisiteManager
Attach this to the player actor.

Requires trait: [`TechTree`](#techtree).

### HarvesterAttackNotifier
Plays an audio notification and shows a radar ping when a harvester is attacked.
Attach this to the player actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>NotifyInterval</td><td>30000</td><td>Integer</td><td>Minimum duration (in milliseconds) between notification events. </td></tr>
<tr><td>RadarPingColor</td><td>FF0000</td><td>Color (RRGGBB[AA] notation)</td><td></td></tr>
<tr><td>RadarPingDuration</td><td>250</td><td>Integer</td><td>Length of time (in ticks) to display a location ping in the minimap. </td></tr>
<tr><td>Notification</td><td>HarvesterAttack</td><td>String</td><td>The audio notification type to play. </td></tr>
</table>

### MissionObjectives
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Cooperative</td><td>False</td><td>Boolean</td><td>Set this to true if multiple cooperative players have a distinct set of objectives that each of them has to complete to win the game. This is mainly useful for multiplayer coop missions. Do not use this for skirmish team games. </td></tr>
<tr><td>EarlyGameOver</td><td>False</td><td>Boolean</td><td>If set to true, this setting causes the game to end immediately once the first player (or team of cooperative players) fails or completes his objectives.  If set to false, players that fail their objectives will stick around and become observers. </td></tr>
<tr><td>GameOverDelay</td><td>1500</td><td>Integer</td><td>Delay between the game over condition being met, and the game actually ending, in milliseconds. </td></tr>
<tr><td>WinNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>LoseNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>LeaveNotification</td><td></td><td>String</td><td></td></tr>
</table>

### ObjectivesPanel
Provides game mode progress information for players.
Goes on WorldActor - observers don't have a player it can live on.
Current options for PanelName are 'SKIRMISH_STATS' and 'MISSION_OBJECTIVES'.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>PanelName</td><td></td><td>String</td><td></td></tr>
<tr><td>ExitDelay</td><td>1400</td><td>Integer</td><td>in ms </td></tr>
</table>

### ModularBot
Bot that uses BotModules.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Type</td><td><em>(required)</em></td><td>String</td><td>Internal id for this bot. </td></tr>
<tr><td>Name</td><td>Unnamed Bot</td><td>String</td><td>Human-readable name this bot uses. </td></tr>
<tr><td>MinOrderQuotientPerTick</td><td>5</td><td>Integer</td><td>Minimum portion of pending orders to issue each tick (e.g. 5 issues at least 1/5th of all pending orders). Excess orders remain queued for subsequent ticks. </td></tr>
</table>

### ParallelProductionQueue
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Type</td><td><em>(required)</em></td><td>String</td><td>What kind of production will be added (e.g. Building, Infantry, Vehicle, ...) </td></tr>
<tr><td>DisplayOrder</td><td>0</td><td>Integer</td><td>The value used when ordering this for display (e.g. in the Spectator UI). </td></tr>
<tr><td>Group</td><td></td><td>String</td><td>Group queues from separate buildings together into the same tab. </td></tr>
<tr><td>Factions</td><td></td><td>Set of System.String[]</td><td>Only enable this queue for certain factions. </td></tr>
<tr><td>Sticky</td><td>True</td><td>Boolean</td><td>Should the prerequisite remain enabled if the owner changes? </td></tr>
<tr><td>DisallowPaused</td><td>False</td><td>Boolean</td><td>Should right clicking on the icon instantly cancel the production instead of putting it on hold? </td></tr>
<tr><td>BuildDurationModifier</td><td>100</td><td>Integer</td><td>This percentage value is multiplied with actor cost to translate into build time (lower means faster). </td></tr>
<tr><td>ItemLimit</td><td>999</td><td>Integer</td><td>Maximum number of a single actor type that can be queued (0 = infinite). </td></tr>
<tr><td>QueueLimit</td><td>0</td><td>Integer</td><td>Maximum number of items that can be queued across all actor types (0 = infinite). </td></tr>
<tr><td>LowPowerModifier</td><td>100</td><td>Integer</td><td>The build time is multiplied with this percentage on low power. </td></tr>
<tr><td>InfiniteBuildLimit</td><td>-1</td><td>Integer</td><td>Production items that have more than this many items in the queue will be produced in a loop. </td></tr>
<tr><td>ReadyAudio</td><td></td><td>String</td><td>Notification played when production is complete. The filename of the audio is defined per faction in notifications.yaml. </td></tr>
<tr><td>BlockedAudio</td><td></td><td>String</td><td>Notification played when you can't train another actor when the build limit exceeded or the exit is jammed. The filename of the audio is defined per faction in notifications.yaml. </td></tr>
<tr><td>LimitedAudio</td><td></td><td>String</td><td>Notification played when you can't queue another actor when the queue length limit is exceeded. The filename of the audio is defined per faction in notifications.yaml. </td></tr>
<tr><td>QueuedAudio</td><td></td><td>String</td><td>Notification played when user clicks on the build palette icon. The filename of the audio is defined per faction in notifications.yaml. </td></tr>
<tr><td>OnHoldAudio</td><td></td><td>String</td><td>Notification played when player right-clicks on the build palette icon. The filename of the audio is defined per faction in notifications.yaml. </td></tr>
<tr><td>CancelledAudio</td><td></td><td>String</td><td>Notification played when player right-clicks on a build palette icon that is already on hold. The filename of the audio is defined per faction in notifications.yaml. </td></tr>
</table>

### PlaceBeacon
A beacon that is constructed from a circle sprite that is animated once and a moving arrow sprite.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Duration</td><td>750</td><td>Integer</td><td></td></tr>
<tr><td>NotificationType</td><td>Sounds</td><td>String</td><td></td></tr>
<tr><td>Notification</td><td>Beacon</td><td>String</td><td></td></tr>
<tr><td>IsPlayerPalette</td><td>True</td><td>Boolean</td><td></td></tr>
<tr><td>Palette</td><td>player</td><td>String</td><td></td></tr>
<tr><td>BeaconImage</td><td>beacon</td><td>String</td><td></td></tr>
<tr><td>BeaconSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>ArrowSequence</td><td>arrow</td><td>String</td><td></td></tr>
<tr><td>CircleSequence</td><td>circles</td><td>String</td><td></td></tr>
</table>

### PlaceBuilding
Allows the player to execute build orders.
 Attach this to the player actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>NewOptionsNotificationDelay</td><td>10</td><td>Integer</td><td>Play NewOptionsNotification this many ticks after building placement. </td></tr>
<tr><td>NewOptionsNotification</td><td></td><td>String</td><td>Notification to play after building placement if new construction options are available. </td></tr>
<tr><td>CannotPlaceNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>ToggleVariantKey</td><td>OpenRA.HotkeyReference</td><td>HotkeyReference</td><td>Hotkey to toggle between PlaceBuildingVariants when placing a structure. </td></tr>
</table>

### PlayerExperience
This trait can be used to track player experience based on units killed with the `GivesExperience` trait.
It can also be used as a point score system in scripted maps, for example.
Attach this to the player actor.

### PlayerRadarTerrain
Requires trait: [`Shroud`](#shroud).

### PlayerResources
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>DefaultCashDropdownLabel</td><td>Starting Cash</td><td>String</td><td>Descriptive label for the starting cash option in the lobby. </td></tr>
<tr><td>DefaultCashDropdownDescription</td><td>Change the amount of cash that players start with</td><td>String</td><td>Tooltip description for the starting cash option in the lobby. </td></tr>
<tr><td>SelectableCash</td><td>2500, 5000, 10000, 20000</td><td>Collection of Integer</td><td>Starting cash options that are available in the lobby options. </td></tr>
<tr><td>DefaultCash</td><td>5000</td><td>Integer</td><td>Default starting cash option: should be one of the SelectableCash options. </td></tr>
<tr><td>DefaultCashDropdownLocked</td><td>False</td><td>Boolean</td><td>Force the DefaultCash option by disabling changes in the lobby. </td></tr>
<tr><td>DefaultCashDropdownVisible</td><td>True</td><td>Boolean</td><td>Whether to display the DefaultCash option in the lobby. </td></tr>
<tr><td>DefaultCashDropdownDisplayOrder</td><td>0</td><td>Integer</td><td>Display order for the DefaultCash option. </td></tr>
<tr><td>InsufficientFundsNotification</td><td></td><td>String</td><td>Speech notification to play when the player does not have any funds. </td></tr>
<tr><td>InsufficientFundsNotificationInterval</td><td>30000</td><td>Integer</td><td>Delay (in ticks) during which warnings will be muted. </td></tr>
<tr><td>CashTickUpNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>CashTickDownNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>ResourceValues</td><td></td><td>Dictionary with Key: String, Value Integer</td><td>Monetery value of each resource type. Dictionary of [resource type]: [value per unit]. </td></tr>
</table>

### PlayerStatistics
Attach this to the player actor to collect observer stats.

### UpdatesPlayerStatistics
Attach this to a unit to update observer stats.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>AddToArmyValue</td><td>False</td><td>Boolean</td><td>Add to army value in statistics </td></tr>
<tr><td>AddToAssetsValue</td><td>True</td><td>Boolean</td><td>Add to assets value in statistics </td></tr>
<tr><td>OverrideActor</td><td></td><td>String</td><td>Count this actor as a different type in the spectator army display. </td></tr>
</table>

### ProductionQueue
Attach this to an actor (usually a building) to let it produce units or construct buildings.
If one builds another actor of this type, he will get a separate queue to create two actors
at the same time. Will only work together with the Production: trait.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Type</td><td><em>(required)</em></td><td>String</td><td>What kind of production will be added (e.g. Building, Infantry, Vehicle, ...) </td></tr>
<tr><td>DisplayOrder</td><td>0</td><td>Integer</td><td>The value used when ordering this for display (e.g. in the Spectator UI). </td></tr>
<tr><td>Group</td><td></td><td>String</td><td>Group queues from separate buildings together into the same tab. </td></tr>
<tr><td>Factions</td><td></td><td>Set of System.String[]</td><td>Only enable this queue for certain factions. </td></tr>
<tr><td>Sticky</td><td>True</td><td>Boolean</td><td>Should the prerequisite remain enabled if the owner changes? </td></tr>
<tr><td>DisallowPaused</td><td>False</td><td>Boolean</td><td>Should right clicking on the icon instantly cancel the production instead of putting it on hold? </td></tr>
<tr><td>BuildDurationModifier</td><td>100</td><td>Integer</td><td>This percentage value is multiplied with actor cost to translate into build time (lower means faster). </td></tr>
<tr><td>ItemLimit</td><td>999</td><td>Integer</td><td>Maximum number of a single actor type that can be queued (0 = infinite). </td></tr>
<tr><td>QueueLimit</td><td>0</td><td>Integer</td><td>Maximum number of items that can be queued across all actor types (0 = infinite). </td></tr>
<tr><td>LowPowerModifier</td><td>100</td><td>Integer</td><td>The build time is multiplied with this percentage on low power. </td></tr>
<tr><td>InfiniteBuildLimit</td><td>-1</td><td>Integer</td><td>Production items that have more than this many items in the queue will be produced in a loop. </td></tr>
<tr><td>ReadyAudio</td><td></td><td>String</td><td>Notification played when production is complete. The filename of the audio is defined per faction in notifications.yaml. </td></tr>
<tr><td>BlockedAudio</td><td></td><td>String</td><td>Notification played when you can't train another actor when the build limit exceeded or the exit is jammed. The filename of the audio is defined per faction in notifications.yaml. </td></tr>
<tr><td>LimitedAudio</td><td></td><td>String</td><td>Notification played when you can't queue another actor when the queue length limit is exceeded. The filename of the audio is defined per faction in notifications.yaml. </td></tr>
<tr><td>QueuedAudio</td><td></td><td>String</td><td>Notification played when user clicks on the build palette icon. The filename of the audio is defined per faction in notifications.yaml. </td></tr>
<tr><td>OnHoldAudio</td><td></td><td>String</td><td>Notification played when player right-clicks on the build palette icon. The filename of the audio is defined per faction in notifications.yaml. </td></tr>
<tr><td>CancelledAudio</td><td></td><td>String</td><td>Notification played when player right-clicks on a build palette icon that is already on hold. The filename of the audio is defined per faction in notifications.yaml. </td></tr>
</table>

### ProvidesPrerequisite
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Prerequisite</td><td></td><td>String</td><td>The prerequisite type that this provides. If left empty it defaults to the actor's name. </td></tr>
<tr><td>RequiresPrerequisites</td><td></td><td>Collection of String</td><td>Only grant this prerequisite when you have these prerequisites. </td></tr>
<tr><td>Factions</td><td></td><td>Set of System.String[]</td><td>Only grant this prerequisite for certain factions. </td></tr>
<tr><td>ResetOnOwnerChange</td><td>False</td><td>Boolean</td><td>Should it recheck everything when it is captured? </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ProvidesTechPrerequisite
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Id</td><td></td><td>String</td><td>Internal id for this tech level. </td></tr>
<tr><td>Name</td><td></td><td>String</td><td>Name shown in the lobby options. </td></tr>
<tr><td>Prerequisites</td><td></td><td>Collection of String</td><td>Prerequisites to grant when this tech level is active. </td></tr>
</table>

### ResourceStorageWarning
Provides the player with an audible warning when their storage is nearing full.

Requires trait: [`PlayerResources`](#playerresources).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>AdviceInterval</td><td>20000</td><td>Integer</td><td>Interval (in milliseconds) at which to check if more storage is needed. </td></tr>
<tr><td>Threshold</td><td>80</td><td>Integer</td><td>The percentage threshold above which a warning is played. </td></tr>
<tr><td>Notification</td><td>SilosNeeded</td><td>String</td><td>The speech to play for the warning. </td></tr>
</table>

### StrategicPoint
Used to mark a place that needs to be in possession for StrategicVictoryConditions.

### StrategicVictoryConditions
Allows King of the Hill (KotH) style gameplay.

Requires trait: [`MissionObjectives`](#missionobjectives).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>HoldDuration</td><td>7500</td><td>Integer</td><td>Amount of time (in game ticks) that the player has to hold all the strategic points. Defaults to 7500 ticks (5 minutes at default speed). </td></tr>
<tr><td>ResetOnHoldLost</td><td>True</td><td>Boolean</td><td>Should the timer reset when the player loses hold of a strategic point. </td></tr>
<tr><td>RatioRequired</td><td>50</td><td>Integer</td><td>Percentage of all strategic points the player has to hold to win. </td></tr>
<tr><td>NotificationDelay</td><td>1500</td><td>Integer</td><td>Delay for the end game notification in milliseconds. </td></tr>
<tr><td>Objective</td><td>Hold all the strategic positions!</td><td>String</td><td>Description of the objective </td></tr>
<tr><td>SuppressNotifications</td><td>False</td><td>Boolean</td><td>Disable the win/loss messages and audio notifications? </td></tr>
</table>

### TechTree
Manages build limits and pre-requisites.
 Attach this to the player actor.

### TimeLimitManager
This trait allows setting a time limit on matches. Attach this to the World actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>TimeLimitLabel</td><td>Time Limit</td><td>String</td><td>Label that will be shown for the time limit option in the lobby. </td></tr>
<tr><td>TimeLimitDescription</td><td>Player or team with the highest score after this time wins</td><td>String</td><td>Tooltip description that will be shown for the time limit option in the lobby. </td></tr>
<tr><td>TimeLimitOptions</td><td>0, 10, 20, 30, 40, 60, 90</td><td>Collection of Integer</td><td>Time Limit options that will be shown in the lobby dropdown. Values are in minutes. </td></tr>
<tr><td>TimeLimitWarnings</td><td>1: 
2: 
3: 
4: 
5: 
10: 
</td><td>Dictionary with Key: Integer, Value String</td><td>List of remaining minutes of game time when a text and optional speech notification should be made to players. </td></tr>
<tr><td>TimeLimitDefault</td><td>0</td><td>Integer</td><td>Default selection for the time limit option in the lobby. Needs to use one of the TimeLimitOptions. </td></tr>
<tr><td>TimeLimitLocked</td><td>False</td><td>Boolean</td><td>Prevent the time limit option from being changed in the lobby. </td></tr>
<tr><td>TimeLimitDropdownVisible</td><td>True</td><td>Boolean</td><td>Whether to display the options dropdown in the lobby. </td></tr>
<tr><td>TimeLimitDisplayOrder</td><td>0</td><td>Integer</td><td>Display order for the time limit dropdown in the lobby. </td></tr>
<tr><td>Notification</td><td>{0} minute{1} remaining.</td><td>String</td><td>Notification text for time limit warnings. The string '{0}' will be replaced by the remaining time in minutes, '{1}' is used for the plural form. </td></tr>
<tr><td>CountdownLabel</td><td></td><td>String</td><td>ID of the LabelWidget used to display a text ingame that will be updated every second. </td></tr>
<tr><td>CountdownText</td><td></td><td>String</td><td>Text to be shown using the CountdownLabel. The string '{0}' will be replaced by the time in hh:mm:ss format. </td></tr>
<tr><td>SkipTimeRemainingNotifications</td><td>False</td><td>Boolean</td><td>Will prevent showing/playing the built-in time limit warnings when set to true. </td></tr>
<tr><td>SkipTimerExpiredNotification</td><td>False</td><td>Boolean</td><td>Will prevent showing/playing the built-in timer expired notification when set to true. </td></tr>
</table>

### Plug
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Type</td><td><em>(required)</em></td><td>String</td><td>Plug type (matched against Conditions in Pluggable) </td></tr>
</table>

### Pluggable
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Offset</td><td>0,0</td><td>2D Cell Vector</td><td>Footprint cell offset where a plug can be placed. </td></tr>
<tr><td>Conditions</td><td><em>(required)</em></td><td>Dictionary with Key: String, Value String</td><td>Conditions to grant for each accepted plug type. Key is the plug type. Value is the condition that is granted when the plug is enabled. </td></tr>
<tr><td>Requirements</td><td></td><td>Dictionary with Key: String, Value BooleanExpression</td><td>Requirements for accepting a plug type. Key is the plug type that the requirements applies to. Value is the condition expression defining the requirements to place the plug. </td></tr>
<tr><td>EditorOptions</td><td></td><td>Dictionary with Key: String, Value String</td><td>Options to display in the map editor. Key is the plug type that the requirements applies to. Value is the label that is displayed in the actor editor dropdown. </td></tr>
<tr><td>EmptyOption</td><td>Empty</td><td>String</td><td>Label to use for an empty plug socket. </td></tr>
<tr><td>EditorDisplayOrder</td><td>5</td><td>Integer</td><td>Display order for the dropdown in the map editor </td></tr>
</table>

### AffectedByPowerOutage
Disables the actor when a power outage is triggered (see `InfiltrateForPowerOutage` for more information).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td></td><td>String</td><td>The condition to grant while there is a power outage. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### PowerManager
Attach this to the player actor.

Requires trait: [`DeveloperMode`](#developermode).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>AdviceInterval</td><td>10000</td><td>Integer</td><td>Interval (in milliseconds) at which to warn the player of low power. </td></tr>
<tr><td>SpeechNotification</td><td></td><td>String</td><td></td></tr>
</table>

### Power
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Amount</td><td>0</td><td>Integer</td><td>If negative, it will drain power. If positive, it will provide power. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ScalePowerWithHealth
Scale power amount with the current health.

Requires trait: [`Power`](#power).

### PowerTooltip
Shown power info on the build palette widget.

### ProducibleWithLevel
Actors possessing this trait should define the GainsExperience trait. When the prerequisites are fulfilled, 
this trait grants a level-up to newly spawned actors. If additionally the actor's owning player defines the ProductionIconOverlay 
trait, the production queue icon renders with an overlay defined in that trait.

Requires trait: [`GainsExperience`](#gainsexperience).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Prerequisites</td><td></td><td>Collection of String</td><td></td></tr>
<tr><td>InitialLevels</td><td>1</td><td>Integer</td><td>Number of levels to give to the actor on creation. </td></tr>
<tr><td>SuppressLevelupAnimation</td><td>True</td><td>Boolean</td><td>Should the level-up animation be suppressed when actor is created? </td></tr>
</table>

### Production
This unit has access to build queues.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Produces</td><td><em>(required)</em></td><td>Collection of String</td><td>e.g. Infantry, Vehicles, Aircraft, Buildings </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ProductionFromMapEdge
Produce a unit on the closest map edge cell and move into the world.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Produces</td><td><em>(required)</em></td><td>Collection of String</td><td>e.g. Infantry, Vehicles, Aircraft, Buildings </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ProductionParadrop
Deliver the unit in production via paradrop.

Requires trait: [`Exit`](#exit).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ActorType</td><td>badr</td><td>String</td><td>Cargo aircraft used. Must have Aircraft trait. </td></tr>
<tr><td>ChuteSound</td><td></td><td>String</td><td>Sound to play when dropping the unit. </td></tr>
<tr><td>ReadyAudio</td><td></td><td>String</td><td>Notification to play when dropping the unit. </td></tr>
<tr><td>Produces</td><td><em>(required)</em></td><td>Collection of String</td><td>e.g. Infantry, Vehicles, Aircraft, Buildings </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ProductionQueueFromSelection
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ProductionTabsWidget</td><td></td><td>String</td><td></td></tr>
<tr><td>ProductionPaletteWidget</td><td></td><td>String</td><td></td></tr>
</table>

### ProximityCaptor
Actor can capture ProximityCapturable actors.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Types</td><td><em>(required)</em></td><td>Collection of CaptureType</td><td></td></tr>
</table>

### ProximityCapturable
Actor can be captured by units in a specified proximity.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Range</td><td>5c0</td><td>1D World Distance</td><td>Maximum range at which a ProximityCaptor actor can initiate the capture. </td></tr>
<tr><td>CaptorTypes</td><td>Player, Vehicle, Tank, Infantry</td><td>Collection of CaptureType</td><td>Allowed ProximityCaptor actors to capture this actor. </td></tr>
<tr><td>MustBeClear</td><td>False</td><td>Boolean</td><td>If set, the capturing process stops immediately after another player comes into Range. </td></tr>
<tr><td>Sticky</td><td>False</td><td>Boolean</td><td>If set, the ownership will not revert back when the captor leaves the area. </td></tr>
<tr><td>Permanent</td><td>False</td><td>Boolean</td><td>If set, the actor can only be captured via this logic once. This option implies the `Sticky` behaviour as well. </td></tr>
</table>

### QuantizeFacingsFromSequence
Derive facings from sprite body sequence.

Requires trait: [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Sequence</td><td>idle</td><td>String</td><td>Defines sequence to derive facings from. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### Rearmable
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>RearmActors</td><td><em>(required)</em></td><td>Set of System.String[]</td><td>Actors that this actor can dock to and get rearmed by. </td></tr>
<tr><td>AmmoPools</td><td>primary</td><td>Set of System.String[]</td><td>Name(s) of AmmoPool(s) that use this trait to rearm. </td></tr>
</table>

### RejectsOrders
Can be used to make a unit partly uncontrollable by the player.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Reject</td><td></td><td>Set of System.String[]</td><td>Explicit list of rejected orders. Leave empty to reject all minus those listed under Except. </td></tr>
<tr><td>Except</td><td></td><td>Set of System.String[]</td><td>List of orders that should *not* be rejected. Also overrides other instances of this trait's Reject fields. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ReloadAmmoPool
Reloads an ammo pool.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>AmmoPool</td><td>primary</td><td>String</td><td>Reload ammo pool with this name. </td></tr>
<tr><td>Delay</td><td>50</td><td>Integer</td><td>Reload time in ticks per Count. </td></tr>
<tr><td>Count</td><td>1</td><td>Integer</td><td>How much ammo is reloaded after Delay. </td></tr>
<tr><td>ResetOnFire</td><td>False</td><td>Boolean</td><td>Whether or not reload timer should be reset when ammo has been fired. </td></tr>
<tr><td>Sound</td><td></td><td>String</td><td>Play this sound each time ammo is reloaded. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### Contrail
Draw a colored contrail behind this actor when they move.

Requires trait: [`BodyOrientation`](#bodyorientation).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Offset</td><td>0,0,0</td><td>3D World Vector</td><td>Position relative to body </td></tr>
<tr><td>ZOffset</td><td>0</td><td>Integer</td><td>Offset for Z sorting. </td></tr>
<tr><td>TrailLength</td><td>25</td><td>Integer</td><td>Length of the trail (in ticks). </td></tr>
<tr><td>TrailWidth</td><td>0c64</td><td>1D World Distance</td><td>Width of the trail. </td></tr>
<tr><td>Color</td><td>FFFFFF</td><td>Color (RRGGBB[AA] notation)</td><td>RGB color of the contrail. </td></tr>
<tr><td>UsePlayerColor</td><td>True</td><td>Boolean</td><td>Use player remap color instead of a custom color? </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### CustomTerrainDebugOverlay
Displays custom terrain types.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Font</td><td>TinyBold</td><td>String</td><td></td></tr>
</table>

### DrawLineToTarget
Renders target lines between order waypoints.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Delay</td><td>2400</td><td>Integer</td><td>Delay (in milliseconds) before the target lines disappear. </td></tr>
<tr><td>LineWidth</td><td>1</td><td>Integer</td><td>Width (in pixels) of the target lines. </td></tr>
<tr><td>QueuedLineWidth</td><td>1</td><td>Integer</td><td>Width (in pixels) of the queued target lines. </td></tr>
<tr><td>MarkerWidth</td><td>2</td><td>Integer</td><td>Width (in pixels) of the end node markers. </td></tr>
<tr><td>QueuedMarkerWidth</td><td>2</td><td>Integer</td><td>Width (in pixels) of the queued end node markers. </td></tr>
</table>

### RenderJammerCircle
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Color</td><td>FF000080</td><td>Color (RRGGBB[AA] notation)</td><td>Range circle color. </td></tr>
<tr><td>Width</td><td>1</td><td>Real Number</td><td>Range circle line width. </td></tr>
<tr><td>BorderColor</td><td>00000060</td><td>Color (RRGGBB[AA] notation)</td><td>Range circle border color. </td></tr>
<tr><td>BorderWidth</td><td>3</td><td>Real Number</td><td>Range circle border width. </td></tr>
</table>

### RenderShroudCircle
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Color</td><td>00FFFF80</td><td>Color (RRGGBB[AA] notation)</td><td>Color of the circle. </td></tr>
<tr><td>Width</td><td>1</td><td>Real Number</td><td>Range circle line width. </td></tr>
<tr><td>BorderColor</td><td>00000060</td><td>Color (RRGGBB[AA] notation)</td><td>Border color of the circle. </td></tr>
<tr><td>BorderWidth</td><td>3</td><td>Real Number</td><td>Range circle border width. </td></tr>
</table>

### Repairable
This actor can be sent to a structure for repairs.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>RepairActors</td><td><em>(required)</em></td><td>Set of System.String[]</td><td></td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>HpPerStep</td><td>-1</td><td>Integer</td><td>The amount the unit will be repaired at each step. Use -1 for fallback behavior where HpPerStep from RepairsUnits trait will be used. </td></tr>
<tr><td>RequireForceMoveCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition under which the regular (non-force) enter cursor is disabled. </td></tr>
<tr><td>EnterCursor</td><td>enter</td><td>String</td><td>Cursor to display when able to be repaired at target actor. </td></tr>
<tr><td>EnterBlockedCursor</td><td>enter-blocked</td><td>String</td><td>Cursor to display when unable to be repaired at target actor. </td></tr>
</table>

### RepairableNear
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>RepairActors</td><td><em>(required)</em></td><td>Set of System.String[]</td><td></td></tr>
<tr><td>CloseEnough</td><td>4c0</td><td>1D World Distance</td><td></td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>RequireForceMoveCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition under which the regular (non-force) enter cursor is disabled. </td></tr>
<tr><td>EnterCursor</td><td>enter</td><td>String</td><td>Cursor to display when able to be repaired near target actor. </td></tr>
<tr><td>EnterBlockedCursor</td><td>enter-blocked</td><td>String</td><td>Cursor to display when unable to be repaired near target actor. </td></tr>
</table>

### RepairsBridges
Can enter a BridgeHut or LegacyBridgeHut to trigger a repair.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>TargetLineColor</td><td>FFFF00</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line. </td></tr>
<tr><td>EnterBehaviour</td><td>Dispose</td><td>EnterBehaviour</td><td>Behaviour when entering the structure. Possible values are Exit, Suicide, Dispose. </td></tr>
<tr><td>TargetCursor</td><td>goldwrench</td><td>String</td><td>Cursor to display when targeting an unrepaired bridge. </td></tr>
<tr><td>TargetBlockedCursor</td><td>goldwrench-blocked</td><td>String</td><td>Cursor to display when repairing is denied. </td></tr>
<tr><td>RepairNotification</td><td></td><td>String</td><td>Speech notification to play when a bridge is repaired. </td></tr>
</table>

### RepairsUnits
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ValuePercentage</td><td>20</td><td>Integer</td><td>Cost in % of the unit value to fully repair the unit. </td></tr>
<tr><td>HpPerStep</td><td>10</td><td>Integer</td><td></td></tr>
<tr><td>Interval</td><td>24</td><td>Integer</td><td>Time (in ticks) between two repair steps. </td></tr>
<tr><td>RepairDamageTypes</td><td></td><td>Collection of DamageType</td><td>Damage types used for the repair. </td></tr>
<tr><td>StartRepairingNotification</td><td></td><td>String</td><td>The sound played when starting to repair a unit. </td></tr>
<tr><td>FinishRepairingNotification</td><td></td><td>String</td><td>The sound played when repairing a unit is done. </td></tr>
<tr><td>PlayerExperience</td><td>0</td><td>Integer</td><td>Experience gained by the player owning this actor for repairing an allied unit. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### Replaceable
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Types</td><td><em>(required)</em></td><td>Set of System.String[]</td><td>Replacement types this Replaceable actor accepts. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### Replacement
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ReplaceableTypes</td><td><em>(required)</em></td><td>Set of System.String[]</td><td>Replacement type (matched against Types in Replaceable). </td></tr>
</table>

### RequiresSpecificOwners
Can be used to enforce specific owners (like 'Neutral' or 'Creeps') for this actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ValidOwnerNames</td><td><em>(required)</em></td><td>Set of System.String[]</td><td>Only allow players listed here as owners. </td></tr>
</table>

### RevealOnDeath
Reveal this actor's last position when killed.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>RevealForRelationships</td><td>Ally</td><td>PlayerRelationship</td><td>Relationships relative to the actors' owner that shroud will be revealed for. </td></tr>
<tr><td>Duration</td><td>25</td><td>Integer</td><td>Duration of the reveal. </td></tr>
<tr><td>Radius</td><td>1c512</td><td>1D World Distance</td><td>Radius of the reveal around this actor. </td></tr>
<tr><td>RevealGeneratedShroud</td><td>True</td><td>Boolean</td><td>Can this actor be revealed through shroud generated by the GeneratesShroud trait? </td></tr>
<tr><td>DeathTypes</td><td></td><td>Collection of DamageType</td><td>DeathTypes for which shroud will be revealed. Use an empty list (the default) to allow all DeathTypes. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### RevealOnFire
Reveal this actor to the target's owner when attacking.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ArmamentNames</td><td>primary, secondary</td><td>Collection of String</td><td>The armament types which trigger revealing. </td></tr>
<tr><td>RevealForRelationships</td><td>Ally</td><td>PlayerRelationship</td><td>Player relationships relative to the target player this actor will be revealed to during firing. </td></tr>
<tr><td>Duration</td><td>25</td><td>Integer</td><td>Duration of the reveal. </td></tr>
<tr><td>Radius</td><td>1c512</td><td>1D World Distance</td><td>Radius of the reveal around this actor. </td></tr>
<tr><td>RevealGeneratedShroud</td><td>True</td><td>Boolean</td><td>Can this actor be revealed through shroud generated by the GeneratesShroud trait? </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### RevealsMap
Reveals shroud and fog across the whole map while active.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ValidRelationships</td><td>Ally</td><td>PlayerRelationship</td><td>Relationships the watching player needs to see the shroud removed. </td></tr>
<tr><td>RevealGeneratedShroud</td><td>True</td><td>Boolean</td><td>Can this actor reveal shroud generated by the `GeneratesShroud` trait? </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### RevealsShroud
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ValidRelationships</td><td>Ally</td><td>PlayerRelationship</td><td>Relationships the watching player needs to see the shroud removed. </td></tr>
<tr><td>RevealGeneratedShroud</td><td>True</td><td>Boolean</td><td>Can this actor reveal shroud generated by the GeneratesShroud trait? </td></tr>
<tr><td>MinRange</td><td>0c0</td><td>1D World Distance</td><td></td></tr>
<tr><td>Range</td><td>0c0</td><td>1D World Distance</td><td></td></tr>
<tr><td>MaxHeightDelta</td><td>-1</td><td>Integer</td><td>If >= 0, prevent cells that are this much higher than the actor from being revealed. </td></tr>
<tr><td>MoveRecalculationThreshold</td><td>0c256</td><td>1D World Distance</td><td>If > 0, force visibility to be recalculated if the unit moves within a cell by more than this distance. </td></tr>
<tr><td>Type</td><td>Footprint</td><td>VisibilityType</td><td>Possible values are CenterPosition (measure range from the center) and  Footprint (measure range from the footprint) </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ScriptTags
Allows this actor to be 'tagged' with arbitrary strings. Tags must be unique or they will be rejected.

### SeedsResource
Lets the actor spread resources around it in a circle.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Interval</td><td>75</td><td>Integer</td><td></td></tr>
<tr><td>ResourceType</td><td>Ore</td><td>String</td><td></td></tr>
<tr><td>MaxRange</td><td>100</td><td>Integer</td><td></td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### Selectable
This actor is selectable. Defines bounds of selectable area, selection class, selection priority and selection priority modifiers.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Priority</td><td>10</td><td>Integer</td><td></td></tr>
<tr><td>PriorityModifiers</td><td>None</td><td>SelectionPriorityModifiers</td><td>Allow selection priority to be modified using a hotkey. Valid values are None (priority is not affected by modifiers) Ctrl (priority is raised when Ctrl pressed) and Alt (priority is raised when Alt pressed). </td></tr>
<tr><td>Class</td><td></td><td>String</td><td>All units having the same selection class specified will be selected with select-by-type commands (e.g. double-click). Defaults to the actor name when not defined or inherited. </td></tr>
<tr><td>Voice</td><td>Select</td><td>String</td><td></td></tr>
<tr><td>Bounds</td><td></td><td>Collection of 1D World Distance</td><td>Defines a custom rectangle for mouse interaction with the actor. If null, the engine will guess an appropriate size based on the With*Body trait. The first two numbers define the width and height of the rectangle as a world distance. The (optional) second two numbers define an x and y offset from the actor center. </td></tr>
<tr><td>DecorationBounds</td><td></td><td>Collection of 1D World Distance</td><td>Defines a custom rectangle for Decorations (e.g. the selection box). If null, Bounds will be used instead </td></tr>
</table>

### Sellable
Actor can be sold
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>RefundPercent</td><td>50</td><td>Integer</td><td>Percentage of units value to give back after selling. </td></tr>
<tr><td>SellSounds</td><td></td><td>Collection of String</td><td>List of audio clips to play when the actor is being sold. </td></tr>
<tr><td>Notification</td><td></td><td>String</td><td>The audio notification type to play. </td></tr>
<tr><td>ShowTicks</td><td>True</td><td>Boolean</td><td>Whether to show the cash tick indicators rising from the actor. </td></tr>
<tr><td>ShowTooltipText</td><td>True</td><td>Boolean</td><td>Whether to show the refund text on the tooltip, when actor is hovered over with sell order. </td></tr>
<tr><td>SkipMakeAnimation</td><td>False</td><td>Boolean</td><td>Skip playing (reversed) make animation. </td></tr>
<tr><td>Cursor</td><td>sell</td><td>String</td><td>Cursor to display when the sell order generator hovers over this actor. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ShakeOnDeath
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>DeathTypes</td><td></td><td>Collection of DamageType</td><td>DeathType(s) that trigger the shake. Leave empty to always trigger a shake. </td></tr>
<tr><td>Duration</td><td>10</td><td>Integer</td><td></td></tr>
<tr><td>Intensity</td><td>1</td><td>Integer</td><td></td></tr>
</table>

### SpawnActorOnDeath
Spawn another actor immediately upon death.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Actor</td><td><em>(required)</em></td><td>String</td><td>Actor to spawn on death. </td></tr>
<tr><td>Probability</td><td>100</td><td>Integer</td><td>Probability the actor spawns. </td></tr>
<tr><td>OwnerType</td><td>Victim</td><td>OwnerType</td><td>Owner of the spawned actor. Allowed keywords:'Victim', 'Killer' and 'InternalName'. Falls back to 'InternalName' if 'Victim' is used and the victim is defeated (see 'SpawnAfterDefeat'). </td></tr>
<tr><td>InternalOwner</td><td>Neutral</td><td>String</td><td>Map player to use when 'InternalName' is defined on 'OwnerType'. </td></tr>
<tr><td>EffectiveOwnerFromOwner</td><td>False</td><td>Boolean</td><td>Changes the effective (displayed) owner of the spawned actor to the old owner (victim). </td></tr>
<tr><td>DeathType</td><td></td><td>String</td><td>DeathType that triggers the actor spawn. Leave empty to spawn an actor ignoring the DeathTypes. </td></tr>
<tr><td>SkipMakeAnimations</td><td>True</td><td>Boolean</td><td>Skips the spawned actor's make animations if true. </td></tr>
<tr><td>RequiresLobbyCreeps</td><td>False</td><td>Boolean</td><td>Should an actor only be spawned when the 'Creeps' setting is true? </td></tr>
<tr><td>Offset</td><td>0,0</td><td>2D Cell Vector</td><td>Offset of the spawned actor relative to the dying actor's position. Warning: Spawning an actor outside the parent actor's footprint/influence might lead to unexpected behaviour. </td></tr>
<tr><td>SpawnAfterDefeat</td><td>True</td><td>Boolean</td><td>Should an actor spawn after the player has been defeated (e.g. after surrendering)? </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### SpawnActorsOnSell
Spawn new actors when sold.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ValuePercent</td><td>40</td><td>Integer</td><td></td></tr>
<tr><td>MinHpPercent</td><td>30</td><td>Integer</td><td></td></tr>
<tr><td>ActorTypes</td><td><em>(required)</em></td><td>Collection of String</td><td>Actor types to spawn on sell. Be sure to use lowercase. </td></tr>
<tr><td>Factions</td><td></td><td>Set of System.String[]</td><td>Spawns actors only if the selling player's faction is in this list. Leave empty to allow all factions by default. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### StoresResources
Adds capacity to a player's harvested resource limit.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Capacity</td><td><em>(required)</em></td><td>Integer</td><td></td></tr>
</table>

### AirstrikePower
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>UnitType</td><td>badr.bomber</td><td>String</td><td></td></tr>
<tr><td>SquadSize</td><td>1</td><td>Integer</td><td></td></tr>
<tr><td>SquadOffset</td><td>-1536,1536,0</td><td>3D World Vector</td><td></td></tr>
<tr><td>QuantizedFacings</td><td>32</td><td>Integer</td><td></td></tr>
<tr><td>Cordon</td><td>5c0</td><td>1D World Distance</td><td></td></tr>
<tr><td>CameraActor</td><td></td><td>String</td><td>Actor to spawn when the aircraft start attacking </td></tr>
<tr><td>CameraRemoveDelay</td><td>25</td><td>Integer</td><td>Amount of time to keep the camera alive after the aircraft have finished attacking </td></tr>
<tr><td>UseDirectionalTarget</td><td>False</td><td>Boolean</td><td>Enables the player directional targeting </td></tr>
<tr><td>DirectionArrowAnimation</td><td></td><td>String</td><td>Animation used to render the direction arrows. </td></tr>
<tr><td>DirectionArrowPalette</td><td>chrome</td><td>String</td><td>Palette for direction cursor animation. </td></tr>
<tr><td>BeaconDistanceOffset</td><td>6c0</td><td>1D World Distance</td><td>Weapon range offset to apply during the beacon clock calculation </td></tr>
<tr><td>ChargeInterval</td><td>0</td><td>Integer</td><td>Measured in ticks. </td></tr>
<tr><td>IconImage</td><td>icon</td><td>String</td><td></td></tr>
<tr><td>Icon</td><td></td><td>String</td><td>Icon sprite displayed in the support power palette. </td></tr>
<tr><td>IconPalette</td><td>chrome</td><td>String</td><td>Palette used for the icon. </td></tr>
<tr><td>Description</td><td></td><td>String</td><td></td></tr>
<tr><td>LongDesc</td><td></td><td>String</td><td></td></tr>
<tr><td>AllowMultiple</td><td>False</td><td>Boolean</td><td>Allow multiple instances of the same support power. </td></tr>
<tr><td>OneShot</td><td>False</td><td>Boolean</td><td>Allow this to be used only once. </td></tr>
<tr><td>Cursor</td><td>ability</td><td>String</td><td>Cursor to display for using this support power. </td></tr>
<tr><td>StartFullyCharged</td><td>False</td><td>Boolean</td><td>If set to true, the support power will be fully charged when it becomes available. Normal rules apply for subsequent charges. </td></tr>
<tr><td>Prerequisites</td><td></td><td>Collection of String</td><td></td></tr>
<tr><td>BeginChargeSound</td><td></td><td>String</td><td></td></tr>
<tr><td>BeginChargeSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>EndChargeSound</td><td></td><td>String</td><td></td></tr>
<tr><td>EndChargeSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>SelectTargetSound</td><td></td><td>String</td><td></td></tr>
<tr><td>SelectTargetSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>InsufficientPowerSound</td><td></td><td>String</td><td></td></tr>
<tr><td>InsufficientPowerSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>LaunchSound</td><td></td><td>String</td><td></td></tr>
<tr><td>LaunchSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>IncomingSound</td><td></td><td>String</td><td></td></tr>
<tr><td>IncomingSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>DisplayTimerRelationships</td><td>None</td><td>PlayerRelationship</td><td>Defines to which players the timer is shown. </td></tr>
<tr><td>DisplayBeacon</td><td>False</td><td>Boolean</td><td>Beacons are only supported on the Airstrike, Paratroopers, and Nuke powers </td></tr>
<tr><td>BeaconPaletteIsPlayerPalette</td><td>True</td><td>Boolean</td><td></td></tr>
<tr><td>BeaconPalette</td><td>player</td><td>String</td><td></td></tr>
<tr><td>BeaconImage</td><td>beacon</td><td>String</td><td></td></tr>
<tr><td>BeaconPoster</td><td></td><td>String</td><td></td></tr>
<tr><td>BeaconPosterPalette</td><td>chrome</td><td>String</td><td></td></tr>
<tr><td>ClockSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>BeaconSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>ArrowSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>CircleSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>BeaconDelay</td><td>0</td><td>Integer</td><td>Delay after launch, measured in ticks. </td></tr>
<tr><td>DisplayRadarPing</td><td>False</td><td>Boolean</td><td></td></tr>
<tr><td>RadarPingDuration</td><td>125</td><td>Integer</td><td>Measured in ticks. </td></tr>
<tr><td>OrderName</td><td>AirstrikePowerInfoOrder</td><td>String</td><td></td></tr>
<tr><td>SupportPowerPaletteOrder</td><td>9999</td><td>Integer</td><td>Sort order for the support power palette. Smaller numbers are presented earlier. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### GrantExternalConditionPower
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td>The condition to apply. Must be included in the target actor's ExternalConditions list. </td></tr>
<tr><td>Duration</td><td>0</td><td>Integer</td><td>Duration of the condition (in ticks). Set to 0 for a permanent condition. </td></tr>
<tr><td>Dimensions</td><td><em>(required)</em></td><td>2D Cell Vector</td><td>Size of the footprint of the affected area. </td></tr>
<tr><td>Footprint</td><td><em>(required)</em></td><td>String</td><td>Actual footprint. Cells marked as x will be affected. </td></tr>
<tr><td>OnFireSound</td><td></td><td>String</td><td>Sound to instantly play at the targeted area. </td></tr>
<tr><td>ValidRelationships</td><td>Ally</td><td>PlayerRelationship</td><td>Player relationships which condition can be applied to. </td></tr>
<tr><td>Sequence</td><td>active</td><td>String</td><td>Sequence to play for granting actor when activated. This requires the actor to have the WithSpriteBody trait or one of its derivatives. </td></tr>
<tr><td>BlockedCursor</td><td>move-blocked</td><td>String</td><td>Cursor to display when there are no units to apply the condition in range. </td></tr>
<tr><td>ChargeInterval</td><td>0</td><td>Integer</td><td>Measured in ticks. </td></tr>
<tr><td>IconImage</td><td>icon</td><td>String</td><td></td></tr>
<tr><td>Icon</td><td></td><td>String</td><td>Icon sprite displayed in the support power palette. </td></tr>
<tr><td>IconPalette</td><td>chrome</td><td>String</td><td>Palette used for the icon. </td></tr>
<tr><td>Description</td><td></td><td>String</td><td></td></tr>
<tr><td>LongDesc</td><td></td><td>String</td><td></td></tr>
<tr><td>AllowMultiple</td><td>False</td><td>Boolean</td><td>Allow multiple instances of the same support power. </td></tr>
<tr><td>OneShot</td><td>False</td><td>Boolean</td><td>Allow this to be used only once. </td></tr>
<tr><td>Cursor</td><td>ability</td><td>String</td><td>Cursor to display for using this support power. </td></tr>
<tr><td>StartFullyCharged</td><td>False</td><td>Boolean</td><td>If set to true, the support power will be fully charged when it becomes available. Normal rules apply for subsequent charges. </td></tr>
<tr><td>Prerequisites</td><td></td><td>Collection of String</td><td></td></tr>
<tr><td>BeginChargeSound</td><td></td><td>String</td><td></td></tr>
<tr><td>BeginChargeSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>EndChargeSound</td><td></td><td>String</td><td></td></tr>
<tr><td>EndChargeSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>SelectTargetSound</td><td></td><td>String</td><td></td></tr>
<tr><td>SelectTargetSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>InsufficientPowerSound</td><td></td><td>String</td><td></td></tr>
<tr><td>InsufficientPowerSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>LaunchSound</td><td></td><td>String</td><td></td></tr>
<tr><td>LaunchSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>IncomingSound</td><td></td><td>String</td><td></td></tr>
<tr><td>IncomingSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>DisplayTimerRelationships</td><td>None</td><td>PlayerRelationship</td><td>Defines to which players the timer is shown. </td></tr>
<tr><td>DisplayBeacon</td><td>False</td><td>Boolean</td><td>Beacons are only supported on the Airstrike, Paratroopers, and Nuke powers </td></tr>
<tr><td>BeaconPaletteIsPlayerPalette</td><td>True</td><td>Boolean</td><td></td></tr>
<tr><td>BeaconPalette</td><td>player</td><td>String</td><td></td></tr>
<tr><td>BeaconImage</td><td>beacon</td><td>String</td><td></td></tr>
<tr><td>BeaconPoster</td><td></td><td>String</td><td></td></tr>
<tr><td>BeaconPosterPalette</td><td>chrome</td><td>String</td><td></td></tr>
<tr><td>ClockSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>BeaconSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>ArrowSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>CircleSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>BeaconDelay</td><td>0</td><td>Integer</td><td>Delay after launch, measured in ticks. </td></tr>
<tr><td>DisplayRadarPing</td><td>False</td><td>Boolean</td><td></td></tr>
<tr><td>RadarPingDuration</td><td>125</td><td>Integer</td><td>Measured in ticks. </td></tr>
<tr><td>OrderName</td><td>GrantExternalConditionPowerInfoOrder</td><td>String</td><td></td></tr>
<tr><td>SupportPowerPaletteOrder</td><td>9999</td><td>Integer</td><td>Sort order for the support power palette. Smaller numbers are presented earlier. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### NukePower
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>MissileWeapon</td><td><em>(required)</em></td><td>String</td><td>Weapon to use for the impact. Also image to use for the missile. </td></tr>
<tr><td>MissileDelay</td><td>0</td><td>Integer</td><td>Delay (in ticks) after launch until the missile is spawned. </td></tr>
<tr><td>MissileUp</td><td>up</td><td>String</td><td>Sprite sequence for the ascending missile. </td></tr>
<tr><td>MissileDown</td><td>down</td><td>String</td><td>Sprite sequence for the descending missile. </td></tr>
<tr><td>SpawnOffset</td><td>0,0,0</td><td>3D World Vector</td><td>Offset from the actor the missile spawns on. </td></tr>
<tr><td>DetonationAltitude</td><td>0c0</td><td>1D World Distance</td><td>Altitude offset from the target position at which the warhead should detonate. </td></tr>
<tr><td>RemoveMissileOnDetonation</td><td>True</td><td>Boolean</td><td>Should nuke missile projectile be removed on detonation above ground. 'False' will make the missile continue until it hits the ground and disappears (without triggering another explosion). </td></tr>
<tr><td>MissilePalette</td><td>effect</td><td>String</td><td>Palette to use for the missile weapon image. </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Custom palette is a player palette BaseName. </td></tr>
<tr><td>TrailImage</td><td></td><td>String</td><td>Trail animation. </td></tr>
<tr><td>TrailSequences</td><td></td><td>Collection of String</td><td>Loop a randomly chosen sequence of TrailImage from this list while this projectile is moving. </td></tr>
<tr><td>TrailInterval</td><td>1</td><td>Integer</td><td>Interval in ticks between each spawned Trail animation. </td></tr>
<tr><td>TrailDelay</td><td>1</td><td>Integer</td><td>Delay in ticks until trail animation is spawned. </td></tr>
<tr><td>TrailPalette</td><td>effect</td><td>String</td><td>Palette used to render the trail sequence. </td></tr>
<tr><td>TrailUsePlayerPalette</td><td>False</td><td>Boolean</td><td>Use the Player Palette to render the trail sequence. </td></tr>
<tr><td>FlightDelay</td><td>400</td><td>Integer</td><td>Travel time - split equally between ascent and descent. </td></tr>
<tr><td>FlightVelocity</td><td>0c512</td><td>1D World Distance</td><td>Visual ascent velocity in WDist / tick. </td></tr>
<tr><td>SkipAscent</td><td>False</td><td>Boolean</td><td>Descend immediately on the target. </td></tr>
<tr><td>BeaconRemoveAdvance</td><td>25</td><td>Integer</td><td>Amount of time before detonation to remove the beacon. </td></tr>
<tr><td>CameraRange</td><td>0c0</td><td>1D World Distance</td><td>Range of cells the camera should reveal around target cell. </td></tr>
<tr><td>RevealGeneratedShroud</td><td>True</td><td>Boolean</td><td>Can the camera reveal shroud generated by the GeneratesShroud trait? </td></tr>
<tr><td>CameraRelationships</td><td>Ally</td><td>PlayerRelationship</td><td>Reveal cells to players with these relationships only. </td></tr>
<tr><td>CameraSpawnAdvance</td><td>25</td><td>Integer</td><td>Amount of time before detonation to spawn the camera. </td></tr>
<tr><td>CameraRemoveDelay</td><td>25</td><td>Integer</td><td>Amount of time after detonation to remove the camera. </td></tr>
<tr><td>CircleColor</td><td>FF000080</td><td>Color (RRGGBB[AA] notation)</td><td>Range circle color. </td></tr>
<tr><td>CircleWidth</td><td>1</td><td>Real Number</td><td>Range circle width in pixel. </td></tr>
<tr><td>CircleBorderColor</td><td>FF000040</td><td>Color (RRGGBB[AA] notation)</td><td>Range circle border color. </td></tr>
<tr><td>CircleBorderWidth</td><td>3</td><td>Real Number</td><td>Range circle border width in pixel. </td></tr>
<tr><td>CircleRanges</td><td></td><td>Collection of 1D World Distance</td><td>Render circles based on these distance ranges while targeting. </td></tr>
<tr><td>ChargeInterval</td><td>0</td><td>Integer</td><td>Measured in ticks. </td></tr>
<tr><td>IconImage</td><td>icon</td><td>String</td><td></td></tr>
<tr><td>Icon</td><td></td><td>String</td><td>Icon sprite displayed in the support power palette. </td></tr>
<tr><td>IconPalette</td><td>chrome</td><td>String</td><td>Palette used for the icon. </td></tr>
<tr><td>Description</td><td></td><td>String</td><td></td></tr>
<tr><td>LongDesc</td><td></td><td>String</td><td></td></tr>
<tr><td>AllowMultiple</td><td>False</td><td>Boolean</td><td>Allow multiple instances of the same support power. </td></tr>
<tr><td>OneShot</td><td>False</td><td>Boolean</td><td>Allow this to be used only once. </td></tr>
<tr><td>Cursor</td><td>ability</td><td>String</td><td>Cursor to display for using this support power. </td></tr>
<tr><td>StartFullyCharged</td><td>False</td><td>Boolean</td><td>If set to true, the support power will be fully charged when it becomes available. Normal rules apply for subsequent charges. </td></tr>
<tr><td>Prerequisites</td><td></td><td>Collection of String</td><td></td></tr>
<tr><td>BeginChargeSound</td><td></td><td>String</td><td></td></tr>
<tr><td>BeginChargeSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>EndChargeSound</td><td></td><td>String</td><td></td></tr>
<tr><td>EndChargeSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>SelectTargetSound</td><td></td><td>String</td><td></td></tr>
<tr><td>SelectTargetSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>InsufficientPowerSound</td><td></td><td>String</td><td></td></tr>
<tr><td>InsufficientPowerSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>LaunchSound</td><td></td><td>String</td><td></td></tr>
<tr><td>LaunchSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>IncomingSound</td><td></td><td>String</td><td></td></tr>
<tr><td>IncomingSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>DisplayTimerRelationships</td><td>None</td><td>PlayerRelationship</td><td>Defines to which players the timer is shown. </td></tr>
<tr><td>DisplayBeacon</td><td>False</td><td>Boolean</td><td>Beacons are only supported on the Airstrike, Paratroopers, and Nuke powers </td></tr>
<tr><td>BeaconPaletteIsPlayerPalette</td><td>True</td><td>Boolean</td><td></td></tr>
<tr><td>BeaconPalette</td><td>player</td><td>String</td><td></td></tr>
<tr><td>BeaconImage</td><td>beacon</td><td>String</td><td></td></tr>
<tr><td>BeaconPoster</td><td></td><td>String</td><td></td></tr>
<tr><td>BeaconPosterPalette</td><td>chrome</td><td>String</td><td></td></tr>
<tr><td>ClockSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>BeaconSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>ArrowSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>CircleSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>BeaconDelay</td><td>0</td><td>Integer</td><td>Delay after launch, measured in ticks. </td></tr>
<tr><td>DisplayRadarPing</td><td>False</td><td>Boolean</td><td></td></tr>
<tr><td>RadarPingDuration</td><td>125</td><td>Integer</td><td>Measured in ticks. </td></tr>
<tr><td>OrderName</td><td>NukePowerInfoOrder</td><td>String</td><td></td></tr>
<tr><td>SupportPowerPaletteOrder</td><td>9999</td><td>Integer</td><td>Sort order for the support power palette. Smaller numbers are presented earlier. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ParatroopersPower
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>UnitType</td><td>badr</td><td>String</td><td></td></tr>
<tr><td>SquadSize</td><td>1</td><td>Integer</td><td></td></tr>
<tr><td>SquadOffset</td><td>-1536,1536,0</td><td>3D World Vector</td><td></td></tr>
<tr><td>ReinforcementsArrivedSpeechNotification</td><td></td><td>String</td><td>Notification to play when entering the drop zone. </td></tr>
<tr><td>QuantizedFacings</td><td>32</td><td>Integer</td><td>Number of facings that the delivery aircraft may approach from. </td></tr>
<tr><td>Cordon</td><td>5c0</td><td>1D World Distance</td><td>Spawn and remove the plane this far outside the map. </td></tr>
<tr><td>DropItems</td><td></td><td>Collection of String</td><td>Troops to be delivered.  They will be distributed between the planes if SquadSize > 1. </td></tr>
<tr><td>AllowImpassableCells</td><td>False</td><td>Boolean</td><td>Risks stuck units when they don't have the Paratrooper trait. </td></tr>
<tr><td>CameraActor</td><td></td><td>String</td><td>Actor to spawn when the paradrop starts. </td></tr>
<tr><td>CameraRemoveDelay</td><td>85</td><td>Integer</td><td>Amount of time (in ticks) to keep the camera alive while the passengers drop. </td></tr>
<tr><td>UseDirectionalTarget</td><td>False</td><td>Boolean</td><td>Enables the player directional targeting </td></tr>
<tr><td>DirectionArrowAnimation</td><td></td><td>String</td><td>Animation used to render the direction arrows. </td></tr>
<tr><td>DirectionArrowPalette</td><td>chrome</td><td>String</td><td>Palette for direction cursor animation. </td></tr>
<tr><td>BeaconDistanceOffset</td><td>4c0</td><td>1D World Distance</td><td>Weapon range offset to apply during the beacon clock calculation. </td></tr>
<tr><td>ChargeInterval</td><td>0</td><td>Integer</td><td>Measured in ticks. </td></tr>
<tr><td>IconImage</td><td>icon</td><td>String</td><td></td></tr>
<tr><td>Icon</td><td></td><td>String</td><td>Icon sprite displayed in the support power palette. </td></tr>
<tr><td>IconPalette</td><td>chrome</td><td>String</td><td>Palette used for the icon. </td></tr>
<tr><td>Description</td><td></td><td>String</td><td></td></tr>
<tr><td>LongDesc</td><td></td><td>String</td><td></td></tr>
<tr><td>AllowMultiple</td><td>False</td><td>Boolean</td><td>Allow multiple instances of the same support power. </td></tr>
<tr><td>OneShot</td><td>False</td><td>Boolean</td><td>Allow this to be used only once. </td></tr>
<tr><td>Cursor</td><td>ability</td><td>String</td><td>Cursor to display for using this support power. </td></tr>
<tr><td>StartFullyCharged</td><td>False</td><td>Boolean</td><td>If set to true, the support power will be fully charged when it becomes available. Normal rules apply for subsequent charges. </td></tr>
<tr><td>Prerequisites</td><td></td><td>Collection of String</td><td></td></tr>
<tr><td>BeginChargeSound</td><td></td><td>String</td><td></td></tr>
<tr><td>BeginChargeSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>EndChargeSound</td><td></td><td>String</td><td></td></tr>
<tr><td>EndChargeSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>SelectTargetSound</td><td></td><td>String</td><td></td></tr>
<tr><td>SelectTargetSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>InsufficientPowerSound</td><td></td><td>String</td><td></td></tr>
<tr><td>InsufficientPowerSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>LaunchSound</td><td></td><td>String</td><td></td></tr>
<tr><td>LaunchSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>IncomingSound</td><td></td><td>String</td><td></td></tr>
<tr><td>IncomingSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>DisplayTimerRelationships</td><td>None</td><td>PlayerRelationship</td><td>Defines to which players the timer is shown. </td></tr>
<tr><td>DisplayBeacon</td><td>False</td><td>Boolean</td><td>Beacons are only supported on the Airstrike, Paratroopers, and Nuke powers </td></tr>
<tr><td>BeaconPaletteIsPlayerPalette</td><td>True</td><td>Boolean</td><td></td></tr>
<tr><td>BeaconPalette</td><td>player</td><td>String</td><td></td></tr>
<tr><td>BeaconImage</td><td>beacon</td><td>String</td><td></td></tr>
<tr><td>BeaconPoster</td><td></td><td>String</td><td></td></tr>
<tr><td>BeaconPosterPalette</td><td>chrome</td><td>String</td><td></td></tr>
<tr><td>ClockSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>BeaconSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>ArrowSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>CircleSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>BeaconDelay</td><td>0</td><td>Integer</td><td>Delay after launch, measured in ticks. </td></tr>
<tr><td>DisplayRadarPing</td><td>False</td><td>Boolean</td><td></td></tr>
<tr><td>RadarPingDuration</td><td>125</td><td>Integer</td><td>Measured in ticks. </td></tr>
<tr><td>OrderName</td><td>ParatroopersPowerInfoOrder</td><td>String</td><td></td></tr>
<tr><td>SupportPowerPaletteOrder</td><td>9999</td><td>Integer</td><td>Sort order for the support power palette. Smaller numbers are presented earlier. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ProduceActorPower
Produces an actor without using the standard production queue.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Actors</td><td><em>(required)</em></td><td>Collection of String</td><td>Actors to produce. </td></tr>
<tr><td>Type</td><td><em>(required)</em></td><td>String</td><td>Production queue type to use </td></tr>
<tr><td>ReadyAudio</td><td></td><td>String</td><td>Notification played when production is activated. The filename of the audio is defined per faction in notifications.yaml. </td></tr>
<tr><td>BlockedAudio</td><td></td><td>String</td><td>Notification played when the exit is jammed. The filename of the audio is defined per faction in notifications.yaml. </td></tr>
<tr><td>ChargeInterval</td><td>0</td><td>Integer</td><td>Measured in ticks. </td></tr>
<tr><td>IconImage</td><td>icon</td><td>String</td><td></td></tr>
<tr><td>Icon</td><td></td><td>String</td><td>Icon sprite displayed in the support power palette. </td></tr>
<tr><td>IconPalette</td><td>chrome</td><td>String</td><td>Palette used for the icon. </td></tr>
<tr><td>Description</td><td></td><td>String</td><td></td></tr>
<tr><td>LongDesc</td><td></td><td>String</td><td></td></tr>
<tr><td>AllowMultiple</td><td>False</td><td>Boolean</td><td>Allow multiple instances of the same support power. </td></tr>
<tr><td>OneShot</td><td>False</td><td>Boolean</td><td>Allow this to be used only once. </td></tr>
<tr><td>Cursor</td><td>ability</td><td>String</td><td>Cursor to display for using this support power. </td></tr>
<tr><td>StartFullyCharged</td><td>False</td><td>Boolean</td><td>If set to true, the support power will be fully charged when it becomes available. Normal rules apply for subsequent charges. </td></tr>
<tr><td>Prerequisites</td><td></td><td>Collection of String</td><td></td></tr>
<tr><td>BeginChargeSound</td><td></td><td>String</td><td></td></tr>
<tr><td>BeginChargeSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>EndChargeSound</td><td></td><td>String</td><td></td></tr>
<tr><td>EndChargeSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>SelectTargetSound</td><td></td><td>String</td><td></td></tr>
<tr><td>SelectTargetSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>InsufficientPowerSound</td><td></td><td>String</td><td></td></tr>
<tr><td>InsufficientPowerSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>LaunchSound</td><td></td><td>String</td><td></td></tr>
<tr><td>LaunchSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>IncomingSound</td><td></td><td>String</td><td></td></tr>
<tr><td>IncomingSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>DisplayTimerRelationships</td><td>None</td><td>PlayerRelationship</td><td>Defines to which players the timer is shown. </td></tr>
<tr><td>DisplayBeacon</td><td>False</td><td>Boolean</td><td>Beacons are only supported on the Airstrike, Paratroopers, and Nuke powers </td></tr>
<tr><td>BeaconPaletteIsPlayerPalette</td><td>True</td><td>Boolean</td><td></td></tr>
<tr><td>BeaconPalette</td><td>player</td><td>String</td><td></td></tr>
<tr><td>BeaconImage</td><td>beacon</td><td>String</td><td></td></tr>
<tr><td>BeaconPoster</td><td></td><td>String</td><td></td></tr>
<tr><td>BeaconPosterPalette</td><td>chrome</td><td>String</td><td></td></tr>
<tr><td>ClockSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>BeaconSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>ArrowSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>CircleSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>BeaconDelay</td><td>0</td><td>Integer</td><td>Delay after launch, measured in ticks. </td></tr>
<tr><td>DisplayRadarPing</td><td>False</td><td>Boolean</td><td></td></tr>
<tr><td>RadarPingDuration</td><td>125</td><td>Integer</td><td>Measured in ticks. </td></tr>
<tr><td>OrderName</td><td>ProduceActorPowerInfoOrder</td><td>String</td><td></td></tr>
<tr><td>SupportPowerPaletteOrder</td><td>9999</td><td>Integer</td><td>Sort order for the support power palette. Smaller numbers are presented earlier. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### SpawnActorPower
Spawns an actor that stays for a limited amount of time.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Actor</td><td><em>(required)</em></td><td>String</td><td>Actor to spawn. </td></tr>
<tr><td>LifeTime</td><td>250</td><td>Integer</td><td>Amount of time to keep the actor alive in ticks. Value < 0 means this actor will not remove itself. </td></tr>
<tr><td>DeploySound</td><td></td><td>String</td><td></td></tr>
<tr><td>EffectImage</td><td></td><td>String</td><td></td></tr>
<tr><td>EffectSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>EffectPalette</td><td></td><td>String</td><td></td></tr>
<tr><td>ChargeInterval</td><td>0</td><td>Integer</td><td>Measured in ticks. </td></tr>
<tr><td>IconImage</td><td>icon</td><td>String</td><td></td></tr>
<tr><td>Icon</td><td></td><td>String</td><td>Icon sprite displayed in the support power palette. </td></tr>
<tr><td>IconPalette</td><td>chrome</td><td>String</td><td>Palette used for the icon. </td></tr>
<tr><td>Description</td><td></td><td>String</td><td></td></tr>
<tr><td>LongDesc</td><td></td><td>String</td><td></td></tr>
<tr><td>AllowMultiple</td><td>False</td><td>Boolean</td><td>Allow multiple instances of the same support power. </td></tr>
<tr><td>OneShot</td><td>False</td><td>Boolean</td><td>Allow this to be used only once. </td></tr>
<tr><td>Cursor</td><td>ability</td><td>String</td><td>Cursor to display for using this support power. </td></tr>
<tr><td>StartFullyCharged</td><td>False</td><td>Boolean</td><td>If set to true, the support power will be fully charged when it becomes available. Normal rules apply for subsequent charges. </td></tr>
<tr><td>Prerequisites</td><td></td><td>Collection of String</td><td></td></tr>
<tr><td>BeginChargeSound</td><td></td><td>String</td><td></td></tr>
<tr><td>BeginChargeSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>EndChargeSound</td><td></td><td>String</td><td></td></tr>
<tr><td>EndChargeSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>SelectTargetSound</td><td></td><td>String</td><td></td></tr>
<tr><td>SelectTargetSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>InsufficientPowerSound</td><td></td><td>String</td><td></td></tr>
<tr><td>InsufficientPowerSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>LaunchSound</td><td></td><td>String</td><td></td></tr>
<tr><td>LaunchSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>IncomingSound</td><td></td><td>String</td><td></td></tr>
<tr><td>IncomingSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>DisplayTimerRelationships</td><td>None</td><td>PlayerRelationship</td><td>Defines to which players the timer is shown. </td></tr>
<tr><td>DisplayBeacon</td><td>False</td><td>Boolean</td><td>Beacons are only supported on the Airstrike, Paratroopers, and Nuke powers </td></tr>
<tr><td>BeaconPaletteIsPlayerPalette</td><td>True</td><td>Boolean</td><td></td></tr>
<tr><td>BeaconPalette</td><td>player</td><td>String</td><td></td></tr>
<tr><td>BeaconImage</td><td>beacon</td><td>String</td><td></td></tr>
<tr><td>BeaconPoster</td><td></td><td>String</td><td></td></tr>
<tr><td>BeaconPosterPalette</td><td>chrome</td><td>String</td><td></td></tr>
<tr><td>ClockSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>BeaconSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>ArrowSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>CircleSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>BeaconDelay</td><td>0</td><td>Integer</td><td>Delay after launch, measured in ticks. </td></tr>
<tr><td>DisplayRadarPing</td><td>False</td><td>Boolean</td><td></td></tr>
<tr><td>RadarPingDuration</td><td>125</td><td>Integer</td><td>Measured in ticks. </td></tr>
<tr><td>OrderName</td><td>SpawnActorPowerInfoOrder</td><td>String</td><td></td></tr>
<tr><td>SupportPowerPaletteOrder</td><td>9999</td><td>Integer</td><td>Sort order for the support power palette. Smaller numbers are presented earlier. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### SupportPowerManager
Attach this to the player actor.

Requires traits: [`DeveloperMode`](#developermode), [`TechTree`](#techtree).

### Targetable
Actor can be targeted.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>TargetTypes</td><td></td><td>Collection of TargetableType</td><td>Target type. Used for filtering (in)valid targets. </td></tr>
<tr><td>RequiresForceFire</td><td>False</td><td>Boolean</td><td></td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### TemporaryOwnerManager
Interacts with the ChangeOwner warhead.
Displays a bar how long this actor is affected and reverts back to the old owner on temporary changes.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>BarColor</td><td>FFA500</td><td>Color (RRGGBB[AA] notation)</td><td></td></tr>
</table>

### TerrainLighting
Add to the world actor to apply a global lighting tint and allow actors using the TerrainLightSource to add localised lighting.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Intensity</td><td>1</td><td>Real Number</td><td></td></tr>
<tr><td>HeightStep</td><td>0</td><td>Real Number</td><td></td></tr>
<tr><td>RedTint</td><td>1</td><td>Real Number</td><td></td></tr>
<tr><td>GreenTint</td><td>1</td><td>Real Number</td><td></td></tr>
<tr><td>BlueTint</td><td>1</td><td>Real Number</td><td></td></tr>
<tr><td>BinSize</td><td>10</td><td>Integer</td><td>Size of light source partition bins (cells) </td></tr>
</table>

### TerrainLightSource
Adds a localized circular light centered on the actor to the world's TerrainLightSource trait.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Range</td><td>10c0</td><td>1D World Distance</td><td></td></tr>
<tr><td>Intensity</td><td>0</td><td>Real Number</td><td></td></tr>
<tr><td>RedTint</td><td>0</td><td>Real Number</td><td></td></tr>
<tr><td>GreenTint</td><td>0</td><td>Real Number</td><td></td></tr>
<tr><td>BlueTint</td><td>0</td><td>Real Number</td><td></td></tr>
</table>

### ThrowsParticle
Requires traits: [`BodyOrientation`](#bodyorientation), [`WithSpriteBody`](#withspritebody).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Anim</td><td><em>(required)</em></td><td>String</td><td></td></tr>
<tr><td>Offset</td><td>0,0,0</td><td>3D World Vector</td><td>Initial position relative to body </td></tr>
<tr><td>MinThrowRange</td><td>0c256</td><td>1D World Distance</td><td>Minimum distance to throw the particle </td></tr>
<tr><td>MaxThrowRange</td><td>0c768</td><td>1D World Distance</td><td>Maximum distance to throw the particle </td></tr>
<tr><td>MinThrowAngle</td><td>85</td><td>1D World Angle</td><td>Minimum angle to throw the particle </td></tr>
<tr><td>MaxThrowAngle</td><td>170</td><td>1D World Angle</td><td>Maximum angle to throw the particle </td></tr>
<tr><td>Velocity</td><td>75</td><td>Integer</td><td>Speed to throw the particle (horizontal WPos/tick) </td></tr>
<tr><td>TurnSpeed</td><td>60</td><td>1D World Angle</td><td>Speed at which the particle turns. </td></tr>
</table>

### ThrowsShrapnel
Throws particles when the actor is destroyed that do damage on impact.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Weapons</td><td><em>(required)</em></td><td>Collection of String</td><td>The weapons used for shrapnel. </td></tr>
<tr><td>Pieces</td><td>3, 10</td><td>Collection of Integer</td><td>The amount of pieces of shrapnel to expel. Two values indicate a range. </td></tr>
<tr><td>Range</td><td>2c0, 5c0</td><td>Collection of 1D World Distance</td><td>The minimum and maximum distances the shrapnel may travel. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### EditorOnlyTooltip
Shown in map editor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Name</td><td></td><td>String</td><td></td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### Tooltip
Shown in the build palette widget.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>GenericName</td><td></td><td>String</td><td>An optional generic name (i.e. "Soldier" or "Structure")to be shown to chosen players. </td></tr>
<tr><td>GenericStancePrefix</td><td>True</td><td>Boolean</td><td>Prefix generic tooltip name with 'Ally/Neutral/EnemyPrefix'. </td></tr>
<tr><td>AllyPrefix</td><td>Allied</td><td>String</td><td>Prefix to display in the tooltip for allied units. </td></tr>
<tr><td>NeutralPrefix</td><td></td><td>String</td><td>Prefix to display in the tooltip for neutral units. </td></tr>
<tr><td>EnemyPrefix</td><td>Enemy</td><td>String</td><td>Prefix to display in the tooltip for enemy units. </td></tr>
<tr><td>GenericVisibility</td><td>None</td><td>PlayerRelationship</td><td>Player stances that the generic name should be shown to. </td></tr>
<tr><td>ShowOwnerRow</td><td>True</td><td>Boolean</td><td>Show the actor's owner and their faction flag </td></tr>
<tr><td>Name</td><td></td><td>String</td><td></td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### TooltipDescription
Additional info shown in the battlefield tooltip.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Description</td><td></td><td>String</td><td>Text shown in tooltip. </td></tr>
<tr><td>ValidRelationships</td><td>Enemy, Neutral, Ally</td><td>PlayerRelationship</td><td>Player relationships who can view the description. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### TransformCrusherOnCrush
Put this on the actor that gets crushed to replace the crusher with a new actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>IntoActor</td><td><em>(required)</em></td><td>String</td><td></td></tr>
<tr><td>SkipMakeAnims</td><td>True</td><td>Boolean</td><td></td></tr>
<tr><td>CrushClasses</td><td></td><td>Collection of CrushClass</td><td></td></tr>
</table>

### TransformOnCapture
Replaces the captured actor with a new one.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>IntoActor</td><td><em>(required)</em></td><td>String</td><td></td></tr>
<tr><td>ForceHealthPercentage</td><td>0</td><td>Integer</td><td></td></tr>
<tr><td>SkipMakeAnims</td><td>True</td><td>Boolean</td><td></td></tr>
<tr><td>CaptureTypes</td><td></td><td>Collection of CaptureType</td><td>Transform only if the capturer's CaptureTypes overlap with these types. Leave empty to allow all types. </td></tr>
</table>

### Transforms
Actor becomes a specified actor type when this trait is triggered.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>IntoActor</td><td><em>(required)</em></td><td>String</td><td>Actor to transform into. </td></tr>
<tr><td>Offset</td><td>0,0</td><td>2D Cell Vector</td><td>Offset to spawn the transformed actor relative to the current cell. </td></tr>
<tr><td>Facing</td><td>384</td><td>1D World Angle</td><td>Facing that the actor must face before transforming. </td></tr>
<tr><td>TransformSounds</td><td></td><td>Collection of String</td><td>Sounds to play when transforming. </td></tr>
<tr><td>NoTransformSounds</td><td></td><td>Collection of String</td><td>Sounds to play when the transformation is blocked. </td></tr>
<tr><td>TransformNotification</td><td></td><td>String</td><td>Notification to play when transforming. </td></tr>
<tr><td>NoTransformNotification</td><td></td><td>String</td><td>Notification to play when the transformation is blocked. </td></tr>
<tr><td>DeployCursor</td><td>deploy</td><td>String</td><td>Cursor to display when able to (un)deploy the actor. </td></tr>
<tr><td>DeployBlockedCursor</td><td>deploy-blocked</td><td>String</td><td>Cursor to display when unable to (un)deploy the actor. </td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### TunnelEntrance
Provides a target for players to issue orders for units to move through a TerrainTunnel.
The host actor should be placed so that the Sensor position overlaps one of the TerrainTunnel portal cells.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>RallyPoint</td><td><em>(required)</em></td><td>2D Cell Vector</td><td>Offset to use as a staging point for actors entering or exiting the tunnel. Should be at least Margin cells away from the actual entrance. </td></tr>
<tr><td>Margin</td><td>2</td><td>Integer</td><td>Cell radius to use as a staging area around the RallyPoint. </td></tr>
<tr><td>Sensor</td><td>0,0</td><td>2D Cell Vector</td><td>Offset to check for the corresponding TerrainTunnel portal cell(s). </td></tr>
</table>

### TurnOnIdle
Turns actor randomly when idle.

Requires trait: [`Mobile`](#mobile).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>MinDelay</td><td>400</td><td>Integer</td><td>Minimum amount of ticks the actor will wait before the turn. </td></tr>
<tr><td>MaxDelay</td><td>800</td><td>Integer</td><td>Maximum amount of ticks the actor will wait before the turn. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### Turreted
Requires trait: [`BodyOrientation`](#bodyorientation).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Turret</td><td>primary</td><td>String</td><td></td></tr>
<tr><td>TurnSpeed</td><td>512</td><td>1D World Angle</td><td>Speed at which the turret turns. </td></tr>
<tr><td>InitialFacing</td><td>0</td><td>1D World Angle</td><td></td></tr>
<tr><td>RealignDelay</td><td>40</td><td>Integer</td><td>Number of ticks before turret is realigned. (-1 turns off realignment) </td></tr>
<tr><td>Offset</td><td>0,0,0</td><td>3D World Vector</td><td>Muzzle position relative to turret or body. (forward, right, up) triples </td></tr>
<tr><td>EditorTurretFacingDisplayOrder</td><td>4</td><td>Integer</td><td>Display order for the turret facing slider in the map editor </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### UpdatesDerrickCount
Tag trait for updating the 'Oil Derrick' count economy statistic.

### Valued
How much the unit is worth.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Cost</td><td><em>(required)</em></td><td>Integer</td><td>Used in production, but also for bounties so remember to set it > 0 even for NPCs. </td></tr>
</table>

### Voiced
This actor has a voice.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>VoiceSet</td><td><em>(required)</em></td><td>String</td><td>Which voice set to use. </td></tr>
<tr><td>Volume</td><td>1</td><td>Real Number</td><td>Multiply volume with this factor. </td></tr>
</table>

### Wanders
Wanders around aimlessly while idle.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>WanderMoveRadius</td><td>1</td><td>Integer</td><td></td></tr>
<tr><td>ReduceMoveRadiusDelay</td><td>5</td><td>Integer</td><td>Number of ticks to wait before decreasing the effective move radius. </td></tr>
<tr><td>MinMoveDelay</td><td>0</td><td>Integer</td><td>Minimum amount of ticks the actor will sit idly before starting to wander. </td></tr>
<tr><td>MaxMoveDelay</td><td>0</td><td>Integer</td><td>Maximum amount of ticks the actor will sit idly before starting to wander. </td></tr>
<tr><td>AvoidTerrainTypes</td><td></td><td>Set of System.String[]</td><td>The terrain types that this actor should avoid wandering on to. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ActorMap
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>BinSize</td><td>10</td><td>Integer</td><td>Size of partition bins (cells) </td></tr>
</table>

### ActorSpawnManager
Controls the spawning of specified actor types. Attach this to the world actor.

Requires trait: [`MapCreeps`](#mapcreeps).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Minimum</td><td>0</td><td>Integer</td><td>Minimum number of actors. </td></tr>
<tr><td>Maximum</td><td>4</td><td>Integer</td><td>Maximum number of actors. </td></tr>
<tr><td>SpawnInterval</td><td>6000</td><td>Collection of Integer</td><td>Time (in ticks) between actor spawn. Supports 1 or 2 values.
If 2 values are provided they are used as a range from which a value is randomly selected. </td></tr>
<tr><td>Actors</td><td><em>(required)</em></td><td>Collection of String</td><td>Name of the actor that will be randomly picked to spawn. </td></tr>
<tr><td>Owner</td><td>Creeps</td><td>String</td><td></td></tr>
<tr><td>Types</td><td></td><td>Set of System.String[]</td><td>Type of ActorSpawner with which it connects. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### BridgeLayer

### CliffBackImpassabilityLayer
Sets a custom terrain type for cells that are obscured by back-facing cliffs.
This trait replicates the default CliffBackImpassability=2 behaviour from the TS/RA2 rules.ini.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>TerrainType</td><td>Impassable</td><td>String</td><td></td></tr>
</table>

### ColorPickerManager
Configuration options for the lobby player color picker. Attach this to the world actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>HsvSaturationRange</td><td>0.3, 0.95</td><td>Collection of Real Number</td><td>Minimum and maximum saturation levels that are valid for use. </td></tr>
<tr><td>V</td><td>0.95</td><td>Real Number</td><td>HSV value component for player colors. </td></tr>
<tr><td>SimilarityThreshold</td><td>0.314</td><td>Real Number</td><td>Perceptual color threshold for determining whether two colors are too similar. </td></tr>
<tr><td>PresetHues</td><td></td><td>Collection of Real Number</td><td>List of hue components for the preset colors in the palette tab. Each entry must have a corresponding PresetSaturations definition. </td></tr>
<tr><td>PresetSaturations</td><td></td><td>Collection of Real Number</td><td>List of saturation components for the preset colors in the palette tab. Each entry must have a corresponding PresetHues definition. </td></tr>
<tr><td>PreviewActor</td><td></td><td>String</td><td>Actor type to show in the color picker. This can be overriden for specific factions with FactionPreviewActors. </td></tr>
<tr><td>FactionPreviewActors</td><td></td><td>Dictionary with Key: String, Value String</td><td>Actor type to show in the color picker for specific factions. Overrides PreviewActor. A dictionary of [faction name]: [actor name]. </td></tr>
<tr><td>Color</td><td>00000000</td><td>Color (RRGGBB[AA] notation)</td><td></td></tr>
</table>

### CrateSpawner
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>CheckboxLabel</td><td>Crates</td><td>String</td><td>Descriptive label for the crates checkbox in the lobby. </td></tr>
<tr><td>CheckboxDescription</td><td>Collect crates with units to receive random bonuses or penalties</td><td>String</td><td>Tooltip description for the crates checkbox in the lobby. </td></tr>
<tr><td>CheckboxEnabled</td><td>True</td><td>Boolean</td><td>Default value of the crates checkbox in the lobby. </td></tr>
<tr><td>CheckboxLocked</td><td>False</td><td>Boolean</td><td>Prevent the crates state from being changed in the lobby. </td></tr>
<tr><td>CheckboxVisible</td><td>True</td><td>Boolean</td><td>Whether to display the crates checkbox in the lobby. </td></tr>
<tr><td>CheckboxDisplayOrder</td><td>0</td><td>Integer</td><td>Display order for the crates checkbox in the lobby. </td></tr>
<tr><td>Minimum</td><td>1</td><td>Integer</td><td>Minimum number of crates. </td></tr>
<tr><td>Maximum</td><td>255</td><td>Integer</td><td>Maximum number of crates. </td></tr>
<tr><td>SpawnInterval</td><td>4500</td><td>Integer</td><td>Average time (ticks) between crate spawn. </td></tr>
<tr><td>InitialSpawnDelay</td><td>0</td><td>Integer</td><td>Delay (in ticks) before the first crate spawns. </td></tr>
<tr><td>ValidGround</td><td>Clear, Rough, Road, Ore, Beach</td><td>Set of System.String[]</td><td>Which terrain types can we drop on? </td></tr>
<tr><td>ValidWater</td><td>Water</td><td>Set of System.String[]</td><td>Which terrain types count as water? </td></tr>
<tr><td>WaterChance</td><td>20</td><td>Integer</td><td>Chance of generating a water crate instead of a land crate. </td></tr>
<tr><td>CrateActors</td><td>crate</td><td>Collection of String</td><td>Crate actors to drop. </td></tr>
<tr><td>CrateActorShares</td><td>10</td><td>Collection of Integer</td><td>Chance of each crate actor spawning. </td></tr>
<tr><td>DeliveryAircraft</td><td></td><td>String</td><td>If a DeliveryAircraft: is specified, then this actor will deliver crates. </td></tr>
<tr><td>QuantizedFacings</td><td>32</td><td>Integer</td><td>Number of facings that the delivery aircraft may approach from. </td></tr>
<tr><td>Cordon</td><td>5c0</td><td>1D World Distance</td><td>Spawn and remove the plane this far outside the map. </td></tr>
</table>

### CreateMapPlayers
Attach this to the world actor.

### DomainIndex
Identify untraversable regions of the map for faster pathfinding, especially with AI.
This trait is required. Every mod needs it attached to the world actor.

### EditorActionManager

### EditorActorLayer
Required for the map editor to work. Attach this to the world actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>BinSize</td><td>250</td><td>Integer</td><td>Size of partition bins (world pixels) </td></tr>
</table>

### EditorCursorLayer
Required for the map editor to work. Attach this to the world actor.

Requires trait: [`EditorActorLayer`](#editoractorlayer).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>PreviewFacing</td><td>384</td><td>1D World Angle</td><td></td></tr>
</table>

### EditorResourceLayer
Required for the map editor to work. Attach this to the world actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ResourceTypes</td><td></td><td>Dictionary with Key: String, Value ResourceTypeInfo</td><td></td></tr>
<tr><td>RecalculateResourceDensity</td><td>False</td><td>Boolean</td><td>Override the density saved in maps with values calculated based on the number of neighbouring resource cells. </td></tr>
</table>

### EditorSelectionLayer
Required for the map editor to work. Attach this to the world actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Palette</td><td>terrain</td><td>String</td><td>Palette to use for rendering the placement sprite. </td></tr>
<tr><td>FootprintAlpha</td><td>1</td><td>Real Number</td><td>Custom opacity to apply to the placement sprite. </td></tr>
<tr><td>Image</td><td>editor-overlay</td><td>String</td><td>Sequence image where the selection overlay types are defined. </td></tr>
<tr><td>CopySequence</td><td>copy</td><td>String</td><td>Sequence to use for the copy overlay. </td></tr>
<tr><td>PasteSequence</td><td>paste</td><td>String</td><td>Sequence to use for the paste overlay. </td></tr>
</table>

### ElevatedBridgeLayer
Requires trait: [`DomainIndex`](#domainindex).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ImpassableTerrainType</td><td>Impassable</td><td>String</td><td>Terrain type used by cells outside any elevated bridge footprint. </td></tr>
</table>

### ElevatedBridgePlaceholder
Placeholder to make static elevated bridges work.
Define individual trait instances for each elevated bridge footprint in the map.

Requires trait: [`ElevatedBridgeLayer`](#elevatedbridgelayer).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Location</td><td><em>(required)</em></td><td>2D Cell Position</td><td>Location of the bridge </td></tr>
<tr><td>Orientation</td><td><em>(required)</em></td><td>ElevatedBridgePlaceholderOrientation</td><td>Orientation of the bridge. </td></tr>
<tr><td>Length</td><td><em>(required)</em></td><td>Integer</td><td>Length of the bridge </td></tr>
<tr><td>Height</td><td><em>(required)</em></td><td>Byte</td><td>Height of the bridge in map height steps. </td></tr>
<tr><td>TerrainType</td><td>Road</td><td>String</td><td>Terrain type of the bridge. </td></tr>
</table>

### ExitsDebugOverlayManager
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Font</td><td>TinyBold</td><td>String</td><td>The font used to draw cell vectors. Should match the value as-is in the Fonts section of the mod manifest (do not convert to lowercase). </td></tr>
</table>

### GameSaveViewportManager

### JumpjetActorLayer
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>TerrainType</td><td>Jumpjet</td><td>String</td><td>Terrain type of the airborne layer. </td></tr>
<tr><td>HeightOffset</td><td>3c920</td><td>1D World Distance</td><td>Height offset relative to the smoothed terrain for movement. </td></tr>
<tr><td>SmoothingRadius</td><td>2</td><td>Integer</td><td>Cell radius for smoothing adjacent cell heights. </td></tr>
</table>

### JumpjetLocomotor
Used by Mobile. Required for jumpjet actors. Attach these to the world actor. You can have multiple variants by adding @suffixes.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>JumpjetTransitionCost</td><td>0</td><td>Integer</td><td>Pathfinding cost for taking off or landing. </td></tr>
<tr><td>JumpjetTransitionTerrainTypes</td><td></td><td>Set of System.String[]</td><td>The terrain types that this actor can transition on. Leave empty to allow any. </td></tr>
<tr><td>JumpjetTransitionOnRamps</td><td>True</td><td>Boolean</td><td>Can this actor transition on slopes? </td></tr>
<tr><td>Name</td><td>default</td><td>String</td><td>Locomotor ID. </td></tr>
<tr><td>WaitAverage</td><td>40</td><td>Integer</td><td></td></tr>
<tr><td>WaitSpread</td><td>10</td><td>Integer</td><td></td></tr>
<tr><td>SharesCell</td><td>False</td><td>Boolean</td><td>Allow multiple (infantry) units in one cell. </td></tr>
<tr><td>MoveIntoShroud</td><td>True</td><td>Boolean</td><td>Can the actor be ordered to move in to shroud? </td></tr>
<tr><td>Crushes</td><td></td><td>Collection of CrushClass</td><td>e.g. crate, wall, infantry </td></tr>
<tr><td>CrushDamageTypes</td><td></td><td>Collection of DamageType</td><td>Types of damage that are caused while crushing. Leave empty for no damage types. </td></tr>
<tr><td>TerrainSpeeds</td><td><em>(required)</em></td><td>Dictionary with Key: String, Value TerrainInfo</td><td>Lower the value on rough terrain. Leave out entries for impassable terrain. </td></tr>
</table>

### LegacyBridgeLayer
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Bridges</td><td>bridge1, bridge2</td><td>Collection of String</td><td></td></tr>
</table>

### LoadWidgetAtGameStart
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ShellmapRoot</td><td>MAINMENU</td><td>String</td><td>The widget tree to open when a shellmap is loaded (i.e. the main menu). </td></tr>
<tr><td>IngameRoot</td><td>INGAME_ROOT</td><td>String</td><td>The widget tree to open when a regular map is loaded (i.e. the ingame UI). </td></tr>
<tr><td>EditorRoot</td><td>EDITOR_ROOT</td><td>String</td><td>The widget tree to open when the map editor is loaded. </td></tr>
<tr><td>GameSaveLoadingRoot</td><td>GAMESAVE_LOADING_SCREEN</td><td>String</td><td>The widget tree to open (in addition to INGAME_ROOT) while loading a saved game. </td></tr>
<tr><td>ClearRoot</td><td>True</td><td>Boolean</td><td>Remove any existing UI when a map is loaded. </td></tr>
</table>

### LobbyPrerequisiteCheckbox
Enables defined prerequisites at game start for all players if the checkbox is enabled.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ID</td><td><em>(required)</em></td><td>String</td><td>Internal id for this checkbox. </td></tr>
<tr><td>Label</td><td><em>(required)</em></td><td>String</td><td>Display name for this checkbox. </td></tr>
<tr><td>Description</td><td></td><td>String</td><td>Description name for this checkbox. </td></tr>
<tr><td>Enabled</td><td>False</td><td>Boolean</td><td>Default value of the checkbox in the lobby. </td></tr>
<tr><td>Locked</td><td>False</td><td>Boolean</td><td>Prevent the checkbox from being changed from its default value. </td></tr>
<tr><td>Visible</td><td>True</td><td>Boolean</td><td>Display the checkbox in the lobby. </td></tr>
<tr><td>DisplayOrder</td><td>0</td><td>Integer</td><td>Display order for the checkbox in the lobby. </td></tr>
<tr><td>Prerequisites</td><td><em>(required)</em></td><td>Set of System.String[]</td><td>Prerequisites to grant when this checkbox is enabled. </td></tr>
</table>

### Locomotor
Used by Mobile. Attach these to the world actor. You can have multiple variants by adding @suffixes.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Name</td><td>default</td><td>String</td><td>Locomotor ID. </td></tr>
<tr><td>WaitAverage</td><td>40</td><td>Integer</td><td></td></tr>
<tr><td>WaitSpread</td><td>10</td><td>Integer</td><td></td></tr>
<tr><td>SharesCell</td><td>False</td><td>Boolean</td><td>Allow multiple (infantry) units in one cell. </td></tr>
<tr><td>MoveIntoShroud</td><td>True</td><td>Boolean</td><td>Can the actor be ordered to move in to shroud? </td></tr>
<tr><td>Crushes</td><td></td><td>Collection of CrushClass</td><td>e.g. crate, wall, infantry </td></tr>
<tr><td>CrushDamageTypes</td><td></td><td>Collection of DamageType</td><td>Types of damage that are caused while crushing. Leave empty for no damage types. </td></tr>
<tr><td>TerrainSpeeds</td><td><em>(required)</em></td><td>Dictionary with Key: String, Value TerrainInfo</td><td>Lower the value on rough terrain. Leave out entries for impassable terrain. </td></tr>
</table>

### MapBuildRadius
Controls the build radius checkboxes in the lobby options.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>AllyBuildRadiusCheckboxLabel</td><td>Build off Allies</td><td>String</td><td>Descriptive label for the ally build radius checkbox in the lobby. </td></tr>
<tr><td>AllyBuildRadiusCheckboxDescription</td><td>Allow allies to place structures inside your build area</td><td>String</td><td>Tooltip description for the ally build radius checkbox in the lobby. </td></tr>
<tr><td>AllyBuildRadiusCheckboxEnabled</td><td>True</td><td>Boolean</td><td>Default value of the ally build radius checkbox in the lobby. </td></tr>
<tr><td>AllyBuildRadiusCheckboxLocked</td><td>False</td><td>Boolean</td><td>Prevent the ally build radius state from being changed in the lobby. </td></tr>
<tr><td>AllyBuildRadiusCheckboxVisible</td><td>True</td><td>Boolean</td><td>Whether to display the ally build radius checkbox in the lobby. </td></tr>
<tr><td>AllyBuildRadiusCheckboxDisplayOrder</td><td>0</td><td>Integer</td><td>Display order for the ally build radius checkbox in the lobby. </td></tr>
<tr><td>BuildRadiusCheckboxLabel</td><td>Limit Build Area</td><td>String</td><td>Tooltip description for the build radius checkbox in the lobby. </td></tr>
<tr><td>BuildRadiusCheckboxDescription</td><td>Limits structure placement to areas around Construction Yards</td><td>String</td><td>Tooltip description for the build radius checkbox in the lobby. </td></tr>
<tr><td>BuildRadiusCheckboxEnabled</td><td>True</td><td>Boolean</td><td>Default value of the build radius checkbox in the lobby. </td></tr>
<tr><td>BuildRadiusCheckboxLocked</td><td>False</td><td>Boolean</td><td>Prevent the build radius state from being changed in the lobby. </td></tr>
<tr><td>BuildRadiusCheckboxVisible</td><td>True</td><td>Boolean</td><td>Display the build radius checkbox in the lobby. </td></tr>
<tr><td>BuildRadiusCheckboxDisplayOrder</td><td>0</td><td>Integer</td><td>Display order for the build radius checkbox in the lobby. </td></tr>
</table>

### MapCreeps
Controls the 'Creeps' checkbox in the lobby options.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>CheckboxLabel</td><td>Creep Actors</td><td>String</td><td>Descriptive label for the creeps checkbox in the lobby. </td></tr>
<tr><td>CheckboxDescription</td><td>Hostile forces spawn on the battlefield</td><td>String</td><td>Tooltip description for the creeps checkbox in the lobby. </td></tr>
<tr><td>CheckboxEnabled</td><td>True</td><td>Boolean</td><td>Default value of the creeps checkbox in the lobby. </td></tr>
<tr><td>CheckboxLocked</td><td>False</td><td>Boolean</td><td>Prevent the creeps state from being changed in the lobby. </td></tr>
<tr><td>CheckboxVisible</td><td>True</td><td>Boolean</td><td>Whether to display the creeps checkbox in the lobby. </td></tr>
<tr><td>CheckboxDisplayOrder</td><td>0</td><td>Integer</td><td>Display order for the creeps checkbox in the lobby. </td></tr>
</table>

### MapOptions
Controls the game speed, tech level, and short game lobby options.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ShortGameCheckboxLabel</td><td>Short Game</td><td>String</td><td>Descriptive label for the short game checkbox in the lobby. </td></tr>
<tr><td>ShortGameCheckboxDescription</td><td>Players are defeated when their bases are destroyed</td><td>String</td><td>Tooltip description for the short game checkbox in the lobby. </td></tr>
<tr><td>ShortGameCheckboxEnabled</td><td>True</td><td>Boolean</td><td>Default value of the short game checkbox in the lobby. </td></tr>
<tr><td>ShortGameCheckboxLocked</td><td>False</td><td>Boolean</td><td>Prevent the short game enabled state from being changed in the lobby. </td></tr>
<tr><td>ShortGameCheckboxVisible</td><td>True</td><td>Boolean</td><td>Whether to display the short game checkbox in the lobby. </td></tr>
<tr><td>ShortGameCheckboxDisplayOrder</td><td>0</td><td>Integer</td><td>Display order for the short game checkbox in the lobby. </td></tr>
<tr><td>TechLevelDropdownLabel</td><td>Tech Level</td><td>String</td><td>Descriptive label for the tech level option in the lobby. </td></tr>
<tr><td>TechLevelDropdownDescription</td><td>Change the units and abilities at your disposal</td><td>String</td><td>Tooltip description for the tech level option in the lobby. </td></tr>
<tr><td>TechLevel</td><td>unrestricted</td><td>String</td><td>Default tech level. </td></tr>
<tr><td>TechLevelDropdownLocked</td><td>False</td><td>Boolean</td><td>Prevent the tech level from being changed in the lobby. </td></tr>
<tr><td>TechLevelDropdownVisible</td><td>True</td><td>Boolean</td><td>Display the tech level option in the lobby. </td></tr>
<tr><td>TechLevelDropdownDisplayOrder</td><td>0</td><td>Integer</td><td>Display order for the tech level option in the lobby. </td></tr>
<tr><td>GameSpeedDropdownLabel</td><td>Game Speed</td><td>String</td><td>Tooltip description for the game speed option in the lobby. </td></tr>
<tr><td>GameSpeedDropdownDescription</td><td>Change the rate at which time passes</td><td>String</td><td>Description of the game speed option in the lobby. </td></tr>
<tr><td>GameSpeed</td><td></td><td>String</td><td>Default game speed (leave empty to use the default defined in mod.yaml). </td></tr>
<tr><td>GameSpeedDropdownLocked</td><td>False</td><td>Boolean</td><td>Prevent the game speed from being changed in the lobby. </td></tr>
<tr><td>GameSpeedDropdownVisible</td><td>True</td><td>Boolean</td><td>Display the game speed option in the lobby. </td></tr>
<tr><td>GameSpeedDropdownDisplayOrder</td><td>0</td><td>Integer</td><td>Display order for the game speed option in the lobby. </td></tr>
</table>

### MapStartingLocations
Allows the map to have working spawnpoints. Also controls the 'Separate Team Spawns' checkbox in the lobby options.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>InitialExploreRange</td><td>5c0</td><td>1D World Distance</td><td></td></tr>
<tr><td>SeparateTeamSpawnsCheckboxLabel</td><td>Separate Team Spawns</td><td>String</td><td>Descriptive label for the spawn positions checkbox in the lobby. </td></tr>
<tr><td>SeparateTeamSpawnsCheckboxDescription</td><td>Players without assigned spawn points will start as far as possible from enemy players</td><td>String</td><td>Tooltip description for the spawn positions checkbox in the lobby. </td></tr>
<tr><td>SeparateTeamSpawnsCheckboxEnabled</td><td>True</td><td>Boolean</td><td>Default value of the spawn positions checkbox in the lobby. </td></tr>
<tr><td>SeparateTeamSpawnsCheckboxLocked</td><td>False</td><td>Boolean</td><td>Prevent the spawn positions state from being changed in the lobby. </td></tr>
<tr><td>SeparateTeamSpawnsCheckboxVisible</td><td>True</td><td>Boolean</td><td>Whether to display the spawn positions checkbox in the lobby. </td></tr>
<tr><td>SeparateTeamSpawnsCheckboxDisplayOrder</td><td>0</td><td>Integer</td><td>Display order for the spawn positions checkbox in the lobby. </td></tr>
</table>

### StartingUnits
Used by SpawnStartingUnits. Attach these to the world actor. You can have multiple variants by adding @suffixes.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Class</td><td>none</td><td>String</td><td>Internal class ID. </td></tr>
<tr><td>ClassName</td><td>Unlabeled</td><td>String</td><td>Exposed via the UI to the player. </td></tr>
<tr><td>Factions</td><td></td><td>Set of System.String[]</td><td>Only available when selecting one of these factions. Leave empty for no restrictions. </td></tr>
<tr><td>BaseActor</td><td></td><td>String</td><td>The actor at the center, usually the mobile construction vehicle. </td></tr>
<tr><td>BaseActorOffset</td><td>0,0</td><td>2D Cell Vector</td><td>Offset from the spawn point, BaseActor will spawn at. </td></tr>
<tr><td>SupportActors</td><td></td><td>Collection of String</td><td>A group of units ready to defend or scout. </td></tr>
<tr><td>InnerSupportRadius</td><td>2</td><td>Integer</td><td>Inner radius for spawning support actors </td></tr>
<tr><td>OuterSupportRadius</td><td>4</td><td>Integer</td><td>Outer radius for spawning support actors </td></tr>
<tr><td>BaseActorFacing</td><td>512</td><td>1D World Angle (optional)</td><td>Initial facing of BaseActor. Leave undefined for random facings. </td></tr>
<tr><td>SupportActorsFacing</td><td></td><td>1D World Angle (optional)</td><td>Initial facing of SupportActors. Leave undefined for random facings. </td></tr>
</table>

### MissionData
Defines the FMVs that can be played by missions.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Briefing</td><td></td><td>String</td><td>Briefing text displayed in the mission browser. </td></tr>
<tr><td>BackgroundVideo</td><td></td><td>String</td><td>Played by the "Background Info" button in the mission browser. </td></tr>
<tr><td>BriefingVideo</td><td></td><td>String</td><td>Played by the "Briefing" button in the mission browser. </td></tr>
<tr><td>StartVideo</td><td></td><td>String</td><td>Automatically played before starting the mission. </td></tr>
<tr><td>WinVideo</td><td></td><td>String</td><td>Automatically played when the player wins the mission. </td></tr>
<tr><td>LossVideo</td><td></td><td>String</td><td>Automatically played when the player loses the mission. </td></tr>
</table>

### MusicPlaylist
Trait for music handling. Attach this to the world actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>StartingMusic</td><td></td><td>String</td><td>Music to play when the map starts. Plays the first song on the playlist when undefined. </td></tr>
<tr><td>VictoryMusic</td><td></td><td>String</td><td>Music to play when the game has been won. </td></tr>
<tr><td>DefeatMusic</td><td></td><td>String</td><td>Music to play when the game has been lost. </td></tr>
<tr><td>BackgroundMusic</td><td></td><td>String</td><td>This track is played when no other music is playing. It cannot be paused, but can be overridden by selecting a new track. </td></tr>
<tr><td>AllowMuteBackgroundMusic</td><td>False</td><td>Boolean</td><td>Allow the background music to be muted by the player. </td></tr>
<tr><td>DisableWorldSounds</td><td>False</td><td>Boolean</td><td>Disable all world sounds (combat etc). </td></tr>
</table>

### PathFinder
Calculates routes for mobile units based on the A* search algorithm.
 Attach this to the world actor.

Requires trait: [`Locomotor`](#locomotor).

### RadarPings
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>FromRadius</td><td>200</td><td>Integer</td><td></td></tr>
<tr><td>ToRadius</td><td>15</td><td>Integer</td><td></td></tr>
<tr><td>ShrinkSpeed</td><td>4</td><td>Integer</td><td></td></tr>
<tr><td>RotationSpeed</td><td>0.12</td><td>Real Number</td><td></td></tr>
</table>

### ResourceClaimLayer
Allows harvesters to coordinate their operations. Attach this to the world actor.

### ResourceLayer
Attach this to the world actor.

Requires trait: [`BuildingInfluence`](#buildinginfluence).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ResourceTypes</td><td></td><td>Dictionary with Key: String, Value ResourceTypeInfo</td><td></td></tr>
<tr><td>RecalculateResourceDensity</td><td>False</td><td>Boolean</td><td>Override the density saved in maps with values calculated based on the number of neighbouring resource cells. </td></tr>
</table>

### ResourceRenderer
Visualizes the state of the `ResourceLayer`.
 Attach this to the world actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ResourceTypes</td><td></td><td>Dictionary with Key: String, Value ResourceTypeInfo</td><td></td></tr>
</table>

### ScriptLobbyDropdown
Controls the map difficulty, tech level, and short game lobby options.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ID</td><td><em>(required)</em></td><td>String</td><td>Internal id for this option. </td></tr>
<tr><td>Label</td><td><em>(required)</em></td><td>String</td><td>Descriptive label for this option. </td></tr>
<tr><td>Description</td><td></td><td>String</td><td>Tooltip description for this option. </td></tr>
<tr><td>Default</td><td><em>(required)</em></td><td>String</td><td>Default option key in the `Values` list. </td></tr>
<tr><td>Values</td><td><em>(required)</em></td><td>Dictionary with Key: String, Value String</td><td>Difficulty levels supported by the map. </td></tr>
<tr><td>Locked</td><td>False</td><td>Boolean</td><td>Prevent the option from being changed from its default value. </td></tr>
<tr><td>Visible</td><td>True</td><td>Boolean</td><td>Whether to display the option in the lobby. </td></tr>
<tr><td>DisplayOrder</td><td>0</td><td>Integer</td><td>Display order for the option in the lobby. </td></tr>
</table>

### Selection

### ShroudRenderer
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Sequence</td><td>shroud</td><td>String</td><td></td></tr>
<tr><td>ShroudVariants</td><td>shroud</td><td>Collection of String</td><td></td></tr>
<tr><td>FogVariants</td><td>fog</td><td>Collection of String</td><td></td></tr>
<tr><td>ShroudPalette</td><td>shroud</td><td>String</td><td></td></tr>
<tr><td>FogPalette</td><td>fog</td><td>String</td><td></td></tr>
<tr><td>Index</td><td>12, 9, 8, 3, 1, 6, 4, 2, 13, 11, 7, 14</td><td>Collection of Integer</td><td>Bitfield of shroud directions for each frame. Lower four bits are corners clockwise from TL; upper four are edges clockwise from top </td></tr>
<tr><td>UseExtendedIndex</td><td>False</td><td>Boolean</td><td>Use the upper four bits when calculating frame </td></tr>
<tr><td>OverrideFullShroud</td><td></td><td>String</td><td>Override for source art that doesn't define a fully shrouded tile </td></tr>
<tr><td>OverrideShroudIndex</td><td>15</td><td>Integer</td><td></td></tr>
<tr><td>OverrideFullFog</td><td></td><td>String</td><td>Override for source art that doesn't define a fully fogged tile </td></tr>
<tr><td>OverrideFogIndex</td><td>15</td><td>Integer</td><td></td></tr>
<tr><td>ShroudBlend</td><td>Alpha</td><td>BlendMode</td><td></td></tr>
</table>

### SmudgeLayer
Attach this to the world actor.
Order of the layers defines the Z sorting.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Type</td><td>Scorch</td><td>String</td><td></td></tr>
<tr><td>Sequence</td><td>scorch</td><td>String</td><td>Sprite sequence name </td></tr>
<tr><td>SmokeChance</td><td>0</td><td>Integer</td><td>Chance of smoke rising from the ground </td></tr>
<tr><td>SmokeImage</td><td></td><td>String</td><td>Smoke sprite image name </td></tr>
<tr><td>SmokeSequences</td><td></td><td>Collection of String</td><td>Smoke sprite sequences randomly chosen from </td></tr>
<tr><td>SmokePalette</td><td>effect</td><td>String</td><td></td></tr>
<tr><td>Palette</td><td>terrain</td><td>String</td><td></td></tr>
<tr><td>InitialSmudges</td><td></td><td>Dictionary with Key: 2D Cell Position, Value MapSmudge</td><td></td></tr>
</table>

### SpawnMapActors
Spawns the initial units for each player upon game start.

### SpawnStartingUnits
Spawn base actor at the spawnpoint and support units in an annulus around the base actor. Both are defined at MPStartUnits. Attach this to the world actor.

Requires trait: [`StartingUnits`](#startingunits).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>StartingUnitsClass</td><td>none</td><td>String</td><td></td></tr>
<tr><td>DropdownLabel</td><td>Starting Units</td><td>String</td><td>Descriptive label for the starting units option in the lobby. </td></tr>
<tr><td>DropdownDescription</td><td>Change the units that you start the game with</td><td>String</td><td>Tooltip description for the starting units option in the lobby. </td></tr>
<tr><td>DropdownLocked</td><td>False</td><td>Boolean</td><td>Prevent the starting units option from being changed in the lobby. </td></tr>
<tr><td>DropdownVisible</td><td>True</td><td>Boolean</td><td>Whether to display the starting units option in the lobby. </td></tr>
<tr><td>DropdownDisplayOrder</td><td>0</td><td>Integer</td><td>Display order for the starting units option in the lobby. </td></tr>
</table>

### StartGameNotification
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Notification</td><td>StartGame</td><td>String</td><td></td></tr>
<tr><td>LoadedNotification</td><td>GameLoaded</td><td>String</td><td></td></tr>
<tr><td>SavedNotification</td><td>GameSaved</td><td>String</td><td></td></tr>
</table>

### SubterraneanActorLayer
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>TerrainType</td><td>Subterranean</td><td>String</td><td>Terrain type of the underground layer. </td></tr>
<tr><td>HeightOffset</td><td>-2c0</td><td>1D World Distance</td><td>Height offset relative to the smoothed terrain for movement. </td></tr>
<tr><td>SmoothingRadius</td><td>2</td><td>Integer</td><td>Cell radius for smoothing adjacent cell heights. </td></tr>
</table>

### SubterraneanLocomotor
Used by Mobile. Required for subterranean actors. Attach these to the world actor. You can have multiple variants by adding @suffixes.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>SubterraneanTransitionCost</td><td>0</td><td>Integer</td><td>Pathfinding cost for submerging or reemerging. </td></tr>
<tr><td>SubterraneanTransitionTerrainTypes</td><td></td><td>Set of System.String[]</td><td>The terrain types that this actor can transition on. Leave empty to allow any. </td></tr>
<tr><td>SubterraneanTransitionOnRamps</td><td>False</td><td>Boolean</td><td>Can this actor transition on slopes? </td></tr>
<tr><td>SubterraneanTransitionDepth</td><td>-1c0</td><td>1D World Distance</td><td>Depth at which the subterranian condition is applied. </td></tr>
<tr><td>Name</td><td>default</td><td>String</td><td>Locomotor ID. </td></tr>
<tr><td>WaitAverage</td><td>40</td><td>Integer</td><td></td></tr>
<tr><td>WaitSpread</td><td>10</td><td>Integer</td><td></td></tr>
<tr><td>SharesCell</td><td>False</td><td>Boolean</td><td>Allow multiple (infantry) units in one cell. </td></tr>
<tr><td>MoveIntoShroud</td><td>True</td><td>Boolean</td><td>Can the actor be ordered to move in to shroud? </td></tr>
<tr><td>Crushes</td><td></td><td>Collection of CrushClass</td><td>e.g. crate, wall, infantry </td></tr>
<tr><td>CrushDamageTypes</td><td></td><td>Collection of DamageType</td><td>Types of damage that are caused while crushing. Leave empty for no damage types. </td></tr>
<tr><td>TerrainSpeeds</td><td><em>(required)</em></td><td>Dictionary with Key: String, Value TerrainInfo</td><td>Lower the value on rough terrain. Leave out entries for impassable terrain. </td></tr>
</table>

### TerrainGeometryOverlay
Renders a debug overlay showing the terrain cells. Attach this to the world actor.

### TerrainRenderer

### TerrainTunnel
Requires trait: [`TerrainTunnelLayer`](#terraintunnellayer).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Location</td><td><em>(required)</em></td><td>2D Cell Position</td><td>Location of the tunnel </td></tr>
<tr><td>Height</td><td><em>(required)</em></td><td>Byte</td><td>Height of the tunnel floor in map height steps. </td></tr>
<tr><td>Dimensions</td><td><em>(required)</em></td><td>2D Cell Vector</td><td>Size of the tunnel footprint </td></tr>
<tr><td>Footprint</td><td><em>(required)</em></td><td>String</td><td>Tunnel footprint. _ is passable, x is blocked, and o are tunnel portals. </td></tr>
<tr><td>TerrainType</td><td><em>(required)</em></td><td>String</td><td>Terrain type of the tunnel floor. </td></tr>
</table>

### TerrainTunnelLayer
Requires trait: [`DomainIndex`](#domainindex).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ImpassableTerrainType</td><td>Impassable</td><td>String</td><td>Terrain type used by cells outside any tunnel footprint. </td></tr>
</table>

### ValidateOrder
Used to detect exploits. Attach this to the world actor.

### WarheadDebugOverlay
Part of the combat overlay from DeveloperMode. Attach this to the world actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>DisplayDuration</td><td>25</td><td>Integer</td><td></td></tr>
</table>

### WeatherOverlay
Adds a particle-based overlay.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ParticleDensityFactor</td><td>8</td><td>Integer</td><td>Average number of particles per 100x100 px square. </td></tr>
<tr><td>ChangingWindLevel</td><td>True</td><td>Boolean</td><td>Should the level of the wind change over time, or just stick to the first value of WindLevels? </td></tr>
<tr><td>WindLevels</td><td>-5, -3, -2, 0, 2, 3, 5</td><td>Collection of Integer</td><td>The levels of wind intensity (particles x-axis movement in px/tick). </td></tr>
<tr><td>WindTick</td><td>150, 750</td><td>Collection of Integer</td><td>Works only if ChangingWindLevel is enabled. Min. and max. ticks needed to change the WindLevel. </td></tr>
<tr><td>InstantWindChanges</td><td>False</td><td>Boolean</td><td>Hard or soft fading between the WindLevels. </td></tr>
<tr><td>UseSquares</td><td>True</td><td>Boolean</td><td>Particles are drawn in squares when enabled, otherwise with lines. </td></tr>
<tr><td>ParticleSize</td><td>1, 3</td><td>Collection of Integer</td><td>Size / width of the particle in px. </td></tr>
<tr><td>ScatterDirection</td><td>-1, 1</td><td>Collection of Integer</td><td>Scatters falling direction on the x-axis. Scatter min. and max. value in px/tick. </td></tr>
<tr><td>Gravity</td><td>1, 2</td><td>Collection of Real Number</td><td>Min. and max. speed at which particles fall in px/tick. </td></tr>
<tr><td>SwingOffset</td><td>1, 1.5</td><td>Collection of Real Number</td><td>The current offset value for the swing movement. SwingOffset min. and max. value in px/tick. </td></tr>
<tr><td>SwingSpeed</td><td>0.001, 0.025</td><td>Collection of Real Number</td><td>The value that particles swing to the side each update. SwingSpeed min. and max. value in px/tick. </td></tr>
<tr><td>SwingAmplitude</td><td>1, 1.5</td><td>Collection of Real Number</td><td>The value range that can be swung to the left or right. SwingAmplitude min. and max. value in px/tick. </td></tr>
<tr><td>ParticleColors</td><td>ECECEC, E4E4E4, D0D0D0, BCBCBC</td><td>Collection of Color (RRGGBB[AA] notation)</td><td>The randomly selected rgb(a) hex colors for the particles. Use this order: rrggbb[aa], rrggbb[aa], ... </td></tr>
<tr><td>LineTailAlphaValue</td><td>200</td><td>Byte</td><td>Works only with line enabled and can be used to fade out the tail of the line like a contrail. </td></tr>
</table>


### GrantRandomCondition
Grants a random condition from a predefined list to the actor when created.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Conditions</td><td><em>(required)</em></td><td>Collection of String</td><td>List of conditions to grant from. </td></tr>
</table>


### AppearsOnRadar
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>UseLocation</td><td>False</td><td>Boolean</td><td></td></tr>
<tr><td>ValidRelationships</td><td>Enemy, Neutral, Ally</td><td>PlayerRelationship</td><td>Player relationships who can view this actor on radar. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ProvidesRadar
This actor enables the radar minimap.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### RadarColorFromTerrain
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Terrain</td><td><em>(required)</em></td><td>String</td><td></td></tr>
</table>


### CashTricklerBar
Display the time remaining until the next cash is given by actor's CashTrickler trait.

Requires trait: [`CashTrickler`](#cashtrickler).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>DisplayRelationships</td><td>Ally</td><td>PlayerRelationship</td><td>Defines to which players the bar is to be shown. </td></tr>
<tr><td>Color</td><td>FF00FF</td><td>Color (RRGGBB[AA] notation)</td><td></td></tr>
</table>

### Hovers
Changes the visual Z position periodically.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>BobDistance</td><td>-0c43</td><td>1D World Distance</td><td>Maximum visual Z axis distance relative to actual position + InitialHeight. </td></tr>
<tr><td>MinHoveringAltitude</td><td>0c0</td><td>1D World Distance</td><td>Actual altitude of actor needs to be this or higher to enable hover effect. </td></tr>
<tr><td>Ticks</td><td>6</td><td>Integer</td><td>Amount of ticks it takes to reach BobDistance. </td></tr>
<tr><td>FallTicks</td><td>10</td><td>Integer</td><td>Amount of ticks it takes to fall to the ground from the highest point when disabled. </td></tr>
<tr><td>RiseTicks</td><td>20</td><td>Integer</td><td>Amount of ticks it takes to rise from the ground to InitialHeight. </td></tr>
<tr><td>InitialHeight</td><td>0c43</td><td>1D World Distance</td><td>Initial Z axis modifier relative to actual position. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### IsometricSelectionDecorations
Requires trait: [`IsometricSelectable`](#isometricselectable).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>SelectionBoxColor</td><td>FFFFFF</td><td>Color (RRGGBB[AA] notation)</td><td></td></tr>
</table>

### LeavesTrails
Renders a sprite effect when leaving a cell.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Image</td><td><em>(required)</em></td><td>String</td><td></td></tr>
<tr><td>Sequences</td><td>idle</td><td>Collection of String</td><td></td></tr>
<tr><td>Palette</td><td>effect</td><td>String</td><td></td></tr>
<tr><td>TerrainTypes</td><td></td><td>Set of System.String[]</td><td>Only leave trail on listed terrain types. Leave empty to leave trail on all terrain types. </td></tr>
<tr><td>Type</td><td>Cell</td><td>TrailType</td><td>Accepts values: Cell to draw the trail sprite in the center of the current cell, CenterPosition to draw the trail sprite at the current position. </td></tr>
<tr><td>VisibleThroughFog</td><td>False</td><td>Boolean</td><td>Should the trail be visible through fog. </td></tr>
<tr><td>TrailWhileStationary</td><td>False</td><td>Boolean</td><td>Display a trail while stationary. </td></tr>
<tr><td>StationaryInterval</td><td>0</td><td>Integer</td><td>Delay between trail updates when stationary. </td></tr>
<tr><td>TrailWhileMoving</td><td>True</td><td>Boolean</td><td>Display a trail while moving. </td></tr>
<tr><td>MovingInterval</td><td>0</td><td>Integer</td><td>Delay between trail updates when moving. </td></tr>
<tr><td>StartDelay</td><td>0</td><td>Integer</td><td>Delay before first trail. Use negative values for falling back to the *Interval values. </td></tr>
<tr><td>Offsets</td><td>0,0,0</td><td>Collection of 3D World Vector</td><td>Trail spawn positions relative to actor position. (forward, right, up) triples </td></tr>
<tr><td>SpawnAtLastPosition</td><td>True</td><td>Boolean</td><td>Should the trail spawn relative to last position or current position? </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ProductionBar
Visualizes the remaining build time of actor produced here.

Requires trait: [`Production`](#production).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ProductionType</td><td><em>(required)</em></td><td>String</td><td>Production queue type, for actors with multiple queues. </td></tr>
<tr><td>Color</td><td>87CEEB</td><td>Color (RRGGBB[AA] notation)</td><td></td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ReloadArmamentsBar
Visualizes the minimum remaining time for reloading the armaments.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Armaments</td><td>primary, secondary</td><td>Collection of String</td><td>Armament names </td></tr>
<tr><td>Color</td><td>FF0000</td><td>Color (RRGGBB[AA] notation)</td><td></td></tr>
</table>

### RenderDebugState
Displays the actor's type and ID above the actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Font</td><td>TinyBold</td><td>String</td><td></td></tr>
</table>

### RenderDetectionCircle
Requires trait: [`DetectCloaked`](#detectcloaked).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>UpdateLineTick</td><td>1023</td><td>1D World Angle</td><td>WAngle the Radar update line advances per tick. </td></tr>
<tr><td>TrailCount</td><td>0</td><td>Integer</td><td>Number of trailing Radar update lines. </td></tr>
<tr><td>Color</td><td>32CD3280</td><td>Color (RRGGBB[AA] notation)</td><td>Color of the circle and scanner update line. </td></tr>
<tr><td>Width</td><td>1</td><td>Real Number</td><td>Range circle line width. </td></tr>
<tr><td>BorderColor</td><td>00000060</td><td>Color (RRGGBB[AA] notation)</td><td>Border color of the circle and scanner update line. </td></tr>
<tr><td>BorderWidth</td><td>3</td><td>Real Number</td><td>Range circle border width. </td></tr>
</table>

### RenderRangeCircle
Draw a circle indicating my weapon's range.

Requires trait: [`AttackBase`](#attackbase).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>RangeCircleType</td><td></td><td>String</td><td></td></tr>
<tr><td>FallbackRange</td><td>0c0</td><td>1D World Distance</td><td>Range to draw if no armaments are available. </td></tr>
<tr><td>RangeCircleMode</td><td>Maximum</td><td>RangeCircleMode</td><td>Which circle to show. Valid values are `Maximum`, and `Minimum`. </td></tr>
<tr><td>Color</td><td>FFFF0080</td><td>Color (RRGGBB[AA] notation)</td><td>Color of the circle. </td></tr>
<tr><td>Width</td><td>1</td><td>Real Number</td><td>Range circle line width. </td></tr>
<tr><td>BorderColor</td><td>00000060</td><td>Color (RRGGBB[AA] notation)</td><td>Color of the border. </td></tr>
<tr><td>BorderWidth</td><td>3</td><td>Real Number</td><td>Range circle border width. </td></tr>
</table>

### RenderSprites
Render trait fundament that won't work without additional With* render traits.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Image</td><td></td><td>String</td><td>The sequence name that defines the actor sprites. Defaults to the actor name. </td></tr>
<tr><td>FactionImages</td><td></td><td>Dictionary with Key: String, Value String</td><td>A dictionary of faction-specific image overrides. </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name </td></tr>
<tr><td>PlayerPalette</td><td>player</td><td>String</td><td>Custom PlayerColorPalette: BaseName </td></tr>
</table>

### RenderSpritesEditorOnly
Invisible during games.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Image</td><td></td><td>String</td><td>The sequence name that defines the actor sprites. Defaults to the actor name. </td></tr>
<tr><td>FactionImages</td><td></td><td>Dictionary with Key: String, Value String</td><td>A dictionary of faction-specific image overrides. </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name </td></tr>
<tr><td>PlayerPalette</td><td>player</td><td>String</td><td>Custom PlayerColorPalette: BaseName </td></tr>
</table>

### RenderVoxels
Requires trait: [`BodyOrientation`](#bodyorientation).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Image</td><td></td><td>String</td><td>Defaults to the actor name. </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name </td></tr>
<tr><td>PlayerPalette</td><td>player</td><td>String</td><td>Custom PlayerColorPalette: BaseName </td></tr>
<tr><td>NormalsPalette</td><td>normals</td><td>String</td><td></td></tr>
<tr><td>ShadowPalette</td><td>shadow</td><td>String</td><td></td></tr>
<tr><td>Scale</td><td>12</td><td>Real Number</td><td>Change the image size. </td></tr>
<tr><td>LightPitch</td><td>142</td><td>1D World Angle</td><td></td></tr>
<tr><td>LightYaw</td><td>682</td><td>1D World Angle</td><td></td></tr>
<tr><td>LightAmbientColor</td><td>0.6, 0.6, 0.6</td><td>Collection of Real Number</td><td></td></tr>
<tr><td>LightDiffuseColor</td><td>0.4, 0.4, 0.4</td><td>Collection of Real Number</td><td></td></tr>
</table>

### SelectionDecorations
Requires trait: [`Interactable`](#interactable).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>SelectionBoxColor</td><td>FFFFFF</td><td>Color (RRGGBB[AA] notation)</td><td></td></tr>
</table>

### SupportPowerChargeBar
Display the time remaining until the super weapon attached to the actor is ready.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>DisplayRelationships</td><td>Ally</td><td>PlayerRelationship</td><td>Defines to which players the bar is to be shown. </td></tr>
<tr><td>Color</td><td>FF00FF</td><td>Color (RRGGBB[AA] notation)</td><td></td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### TimedConditionBar
Visualizes the remaining time for a condition.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td>Condition that this bar corresponds to </td></tr>
<tr><td>Color</td><td>FF0000</td><td>Color (RRGGBB[AA] notation)</td><td></td></tr>
</table>

### VeteranProductionIconOverlay
Attach this to the player actor. When attached, enables all actors possessing the ProducibleWithLevel 
trait to have their production queue icons render with an overlay defined in this trait. 
The icon change occurs when ProducibleWithLevel.Prerequisites are met.

Requires trait: [`TechTree`](#techtree).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Image</td><td><em>(required)</em></td><td>String</td><td>Image used for the overlay. </td></tr>
<tr><td>Sequence</td><td></td><td>String</td><td>Sequence used for the overlay (cannot be animated). </td></tr>
<tr><td>Palette</td><td>chrome</td><td>String</td><td>Palette to render the sprite in. Reference the world actor's PaletteFrom* traits. </td></tr>
</table>

### WithAcceptDeliveredCashAnimation
Replaces the building animation when it accepts a cash delivery unit.

Requires trait: [`WithSpriteBody`](#withspritebody).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Sequence</td><td>active</td><td>String</td><td>Sequence name to use </td></tr>
<tr><td>Body</td><td>body</td><td>String</td><td>Which sprite body to play the animation on. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithAimAnimation
Requires traits: [`AttackBase`](#attackbase), [`WithSpriteBody`](#withspritebody).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Armament</td><td>primary</td><td>String</td><td>Armament name </td></tr>
<tr><td>Sequence</td><td><em>(required)</em></td><td>String</td><td>Displayed while targeting. </td></tr>
<tr><td>Body</td><td>body</td><td>String</td><td>Which sprite body to modify. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithAmmoPipsDecoration
Requires trait: [`AmmoPool`](#ammopool).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>PipCount</td><td>-1</td><td>Integer</td><td>Number of pips to display. Defaults to the sum of the enabled AmmoPool.Ammo. </td></tr>
<tr><td>PipStride</td><td>0,0</td><td>2D Integer</td><td>If non-zero, override the spacing between adjacent pips. </td></tr>
<tr><td>Image</td><td>pips</td><td>String</td><td>Image that defines the pip sequences. </td></tr>
<tr><td>EmptySequence</td><td>pip-empty</td><td>String</td><td>Sequence used for empty pips. </td></tr>
<tr><td>FullSequence</td><td>pip-green</td><td>String</td><td>Sequence used for full pips. </td></tr>
<tr><td>Palette</td><td>chrome</td><td>String</td><td></td></tr>
<tr><td>AmmoPools</td><td></td><td>Collection of String</td><td>Name(s) of AmmoPool(s) that use this decoration. Leave empty to include all pools. </td></tr>
<tr><td>Position</td><td>TopLeft</td><td>String</td><td>Position in the actor's selection box to draw the decoration. </td></tr>
<tr><td>ValidRelationships</td><td>Ally</td><td>PlayerRelationship</td><td>Player relationships who can view the decoration. </td></tr>
<tr><td>RequiresSelection</td><td>False</td><td>Boolean</td><td>Should this be visible only when selected? </td></tr>
<tr><td>Margin</td><td>0,0</td><td>2D Integer</td><td>Offset sprite center position from the selection box edge. </td></tr>
<tr><td>Offsets</td><td></td><td>Dictionary with Key: BooleanExpression, Value 2D Integer</td><td>Screen-space offsets to apply when defined conditions are enabled. A dictionary of [condition string]: [x, y offset]. </td></tr>
<tr><td>BlinkInterval</td><td>5</td><td>Integer</td><td>The number of ticks that each step in the blink pattern in active. </td></tr>
<tr><td>BlinkPattern</td><td></td><td>Collection of BlinkState</td><td>A pattern of ticks (BlinkInterval long) where the decoration is visible or hidden. </td></tr>
<tr><td>BlinkPatterns</td><td></td><td>Dictionary with Key: BooleanExpression, Value Collection of BlinkState</td><td>Override blink conditions to use when defined conditions are enabled. A dictionary of [condition string]: [pattern]. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithAttackAnimation
Requires traits: [`Armament`](#armament), [`AttackBase`](#attackbase), [`WithSpriteBody`](#withspritebody).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Armament</td><td>primary</td><td>String</td><td>Armament name </td></tr>
<tr><td>Sequence</td><td></td><td>String</td><td>Displayed while attacking. </td></tr>
<tr><td>Delay</td><td>0</td><td>Integer</td><td>Delay in ticks before animation starts, either relative to attack preparation or attack. </td></tr>
<tr><td>DelayRelativeTo</td><td>Preparation</td><td>AttackDelayType</td><td>Should the animation be delayed relative to preparation or actual attack? </td></tr>
<tr><td>Body</td><td>body</td><td>String</td><td>Which sprite body to modify. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithAttackOverlay
Rendered together with an attack.

Requires trait: [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Sequence</td><td><em>(required)</em></td><td>String</td><td>Sequence name to use </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Custom palette is a player palette BaseName </td></tr>
<tr><td>Delay</td><td>0</td><td>Integer</td><td>Delay in ticks before overlay starts, either relative to attack preparation or attack. </td></tr>
<tr><td>DelayRelativeTo</td><td>Preparation</td><td>AttackDelayType</td><td>Should the overlay be delayed relative to preparation or actual attack? </td></tr>
</table>

### WithBridgeSpriteBody

Requires trait: [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Type</td><td>GroundLevelBridge</td><td>String</td><td></td></tr>
<tr><td>AOffset</td><td>0,0</td><td>2D Cell Vector</td><td>Offset to search for the 'A' neighbour </td></tr>
<tr><td>BOffset</td><td>0,0</td><td>2D Cell Vector</td><td>Position to search for the 'B' neighbour </td></tr>
<tr><td>Sequences</td><td>idle</td><td>Collection of String</td><td>Sequences to use when both neighbours are alive. </td></tr>
<tr><td>ADestroyedSequences</td><td>adestroyed</td><td>Collection of String</td><td></td></tr>
<tr><td>BDestroyedSequences</td><td>bdestroyed</td><td>Collection of String</td><td></td></tr>
<tr><td>ABDestroyedSequences</td><td>abdestroyed</td><td>Collection of String</td><td></td></tr>
<tr><td>StartSequence</td><td></td><td>String</td><td>Animation to play when the actor is created. </td></tr>
<tr><td>Sequence</td><td>idle</td><td>String</td><td>Animation to play when the actor is idle. </td></tr>
<tr><td>Name</td><td>body</td><td>String</td><td>Identifier used to assign modifying traits to this sprite body. </td></tr>
<tr><td>ForceToGround</td><td>False</td><td>Boolean</td><td>Forces sprite body to be rendered on ground regardless of actor altitude (for example for custom shadow sprites). </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name. </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Palette is a player palette BaseName. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithBuildingPlacedAnimation
Changes the animation when the actor constructed a building.

Requires trait: [`WithSpriteBody`](#withspritebody).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Sequence</td><td>build</td><td>String</td><td>Sequence name to use </td></tr>
<tr><td>Body</td><td>body</td><td>String</td><td>Which sprite body to play the animation on. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithBuildingPlacedOverlay
Rendered when the actor constructed a building.

Requires traits: [`BodyOrientation`](#bodyorientation), [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Sequence</td><td>crane-overlay</td><td>String</td><td>Sequence name to use </td></tr>
<tr><td>Offset</td><td>0,0,0</td><td>3D World Vector</td><td>Position relative to body </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Custom palette is a player palette BaseName </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithBuildingRepairDecoration
Displays a custom UI overlay relative to the actor's mouseover bounds.

Requires trait: [`RepairableBuilding`](#repairablebuilding).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Image</td><td></td><td>String</td><td>Image used for this decoration. Defaults to the actor's type. </td></tr>
<tr><td>Sequence</td><td><em>(required)</em></td><td>String</td><td>Sequence used for this decoration (can be animated). </td></tr>
<tr><td>Palette</td><td>chrome</td><td>String</td><td>Palette to render the sprite in. Reference the world actor's PaletteFrom* traits. </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Custom palette is a player palette BaseName </td></tr>
<tr><td>Position</td><td>TopLeft</td><td>String</td><td>Position in the actor's selection box to draw the decoration. </td></tr>
<tr><td>ValidRelationships</td><td>Ally</td><td>PlayerRelationship</td><td>Player relationships who can view the decoration. </td></tr>
<tr><td>RequiresSelection</td><td>False</td><td>Boolean</td><td>Should this be visible only when selected? </td></tr>
<tr><td>Margin</td><td>0,0</td><td>2D Integer</td><td>Offset sprite center position from the selection box edge. </td></tr>
<tr><td>Offsets</td><td></td><td>Dictionary with Key: BooleanExpression, Value 2D Integer</td><td>Screen-space offsets to apply when defined conditions are enabled. A dictionary of [condition string]: [x, y offset]. </td></tr>
<tr><td>BlinkInterval</td><td>5</td><td>Integer</td><td>The number of ticks that each step in the blink pattern in active. </td></tr>
<tr><td>BlinkPattern</td><td></td><td>Collection of BlinkState</td><td>A pattern of ticks (BlinkInterval long) where the decoration is visible or hidden. </td></tr>
<tr><td>BlinkPatterns</td><td></td><td>Dictionary with Key: BooleanExpression, Value Collection of BlinkState</td><td>Override blink conditions to use when defined conditions are enabled. A dictionary of [condition string]: [pattern]. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithCargoPipsDecoration
Requires trait: [`Cargo`](#cargo).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>PipCount</td><td>-1</td><td>Integer</td><td>Number of pips to display. Defaults to Cargo.MaxWeight. </td></tr>
<tr><td>PipStride</td><td>0,0</td><td>2D Integer</td><td>If non-zero, override the spacing between adjacent pips. </td></tr>
<tr><td>Image</td><td>pips</td><td>String</td><td>Image that defines the pip sequences. </td></tr>
<tr><td>EmptySequence</td><td>pip-empty</td><td>String</td><td>Sequence used for empty pips. </td></tr>
<tr><td>FullSequence</td><td>pip-green</td><td>String</td><td>Sequence used for full pips that aren't defined in CustomPipSequences. </td></tr>
<tr><td>CustomPipSequences</td><td></td><td>Dictionary with Key: String, Value String</td><td>Pip sequence to use for specific passenger actors. </td></tr>
<tr><td>Palette</td><td>chrome</td><td>String</td><td></td></tr>
<tr><td>Position</td><td>TopLeft</td><td>String</td><td>Position in the actor's selection box to draw the decoration. </td></tr>
<tr><td>ValidRelationships</td><td>Ally</td><td>PlayerRelationship</td><td>Player relationships who can view the decoration. </td></tr>
<tr><td>RequiresSelection</td><td>False</td><td>Boolean</td><td>Should this be visible only when selected? </td></tr>
<tr><td>Margin</td><td>0,0</td><td>2D Integer</td><td>Offset sprite center position from the selection box edge. </td></tr>
<tr><td>Offsets</td><td></td><td>Dictionary with Key: BooleanExpression, Value 2D Integer</td><td>Screen-space offsets to apply when defined conditions are enabled. A dictionary of [condition string]: [x, y offset]. </td></tr>
<tr><td>BlinkInterval</td><td>5</td><td>Integer</td><td>The number of ticks that each step in the blink pattern in active. </td></tr>
<tr><td>BlinkPattern</td><td></td><td>Collection of BlinkState</td><td>A pattern of ticks (BlinkInterval long) where the decoration is visible or hidden. </td></tr>
<tr><td>BlinkPatterns</td><td></td><td>Dictionary with Key: BooleanExpression, Value Collection of BlinkState</td><td>Override blink conditions to use when defined conditions are enabled. A dictionary of [condition string]: [pattern]. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithChargeOverlay
Render overlay that varies the animation frame based on the AttackCharges trait's charge level.

Requires traits: [`RenderSprites`](#rendersprites), [`WithSpriteBody`](#withspritebody).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Sequence</td><td>active</td><td>String</td><td>Sequence to use for the charge levels. </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Custom palette is a player palette BaseName </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithChargeSpriteBody
Render trait that varies the sprite body frame based on the AttackCharges trait's charge level.

Requires traits: [`AttackCharges`](#attackcharges), [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>StartSequence</td><td></td><td>String</td><td>Animation to play when the actor is created. </td></tr>
<tr><td>Sequence</td><td>idle</td><td>String</td><td>Animation to play when the actor is idle. </td></tr>
<tr><td>Name</td><td>body</td><td>String</td><td>Identifier used to assign modifying traits to this sprite body. </td></tr>
<tr><td>ForceToGround</td><td>False</td><td>Boolean</td><td>Forces sprite body to be rendered on ground regardless of actor altitude (for example for custom shadow sprites). </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name. </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Palette is a player palette BaseName. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithCrateBody
Renders crates with both water and land variants.

Requires trait: [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>XmasImages</td><td></td><td>Collection of String</td><td>Easteregg sequences to use in December. </td></tr>
<tr><td>WaterTerrainTypes</td><td>Water</td><td>Set of System.String[]</td><td>Terrain types on which to display WaterSequence. </td></tr>
<tr><td>IdleSequence</td><td>idle</td><td>String</td><td></td></tr>
<tr><td>WaterSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>LandSequence</td><td></td><td>String</td><td></td></tr>
</table>

### WithDamageOverlay
Renders an overlay when the actor is taking heavy damage.

Requires trait: [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Image</td><td>smoke_m</td><td>String</td><td></td></tr>
<tr><td>IdleSequence</td><td>idle</td><td>String</td><td></td></tr>
<tr><td>LoopSequence</td><td>loop</td><td>String</td><td></td></tr>
<tr><td>EndSequence</td><td>end</td><td>String</td><td></td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name. </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Custom palette is a player palette BaseName. </td></tr>
<tr><td>DamageTypes</td><td></td><td>Collection of DamageType</td><td>Damage types that this should be used for (defined on the warheads). Leave empty to disable all filtering. </td></tr>
<tr><td>MinimumDamageState</td><td>Heavy</td><td>DamageState</td><td>Trigger when Undamaged, Light, Medium, Heavy, Critical or Dead. </td></tr>
<tr><td>MaximumDamageState</td><td>Dead</td><td>DamageState</td><td></td></tr>
</table>

### WithDeadBridgeSpriteBody

Requires trait: [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>RampActors</td><td></td><td>Collection of String</td><td></td></tr>
<tr><td>AOffset</td><td>0,0</td><td>2D Cell Vector</td><td>Offset to search for the 'A' neighbour </td></tr>
<tr><td>BOffset</td><td>0,0</td><td>2D Cell Vector</td><td>Position to search for the 'B' neighbour </td></tr>
<tr><td>ARampSequences</td><td>aramp</td><td>Collection of String</td><td></td></tr>
<tr><td>BRampSequences</td><td>bramp</td><td>Collection of String</td><td></td></tr>
<tr><td>ABRampSequences</td><td>abramp</td><td>Collection of String</td><td></td></tr>
<tr><td>EditorSequence</td><td>editor</td><td>String</td><td>Placeholder sequence to use in the map editor. </td></tr>
<tr><td>EditorPalette</td><td>terrainalpha</td><td>String</td><td>Palette to use for the editor placeholder. </td></tr>
<tr><td>StartSequence</td><td></td><td>String</td><td>Animation to play when the actor is created. </td></tr>
<tr><td>Sequence</td><td>idle</td><td>String</td><td>Animation to play when the actor is idle. </td></tr>
<tr><td>Name</td><td>body</td><td>String</td><td>Identifier used to assign modifying traits to this sprite body. </td></tr>
<tr><td>ForceToGround</td><td>False</td><td>Boolean</td><td>Forces sprite body to be rendered on ground regardless of actor altitude (for example for custom shadow sprites). </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name. </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Palette is a player palette BaseName. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithDeathAnimation
This actor has a death animation.

Requires trait: [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>DeathSequence</td><td>die</td><td>String</td><td>Sequence prefix to play when this actor is killed by a warhead. </td></tr>
<tr><td>DeathSequencePalette</td><td>player</td><td>String</td><td>The palette used for `DeathSequence`. </td></tr>
<tr><td>DeathPaletteIsPlayerPalette</td><td>True</td><td>Boolean</td><td>Custom death animation palette is a player palette BaseName </td></tr>
<tr><td>UseDeathTypeSuffix</td><td>True</td><td>Boolean</td><td>Should DeathType-specific sequences be used (sequence name = DeathSequence + DeathType). </td></tr>
<tr><td>CrushedSequence</td><td></td><td>String</td><td>Sequence to play when this actor is crushed. </td></tr>
<tr><td>CrushedSequencePalette</td><td>effect</td><td>String</td><td>The palette used for `CrushedSequence`. </td></tr>
<tr><td>CrushedPaletteIsPlayerPalette</td><td>False</td><td>Boolean</td><td>Custom crushed animation palette is a player palette BaseName </td></tr>
<tr><td>DeathTypes</td><td></td><td>Dictionary with Key: String, Value Collection of String</td><td>Death animations to use for each damage type (defined on the warheads). Is only used if UseDeathTypeSuffix is `True`. </td></tr>
<tr><td>FallbackSequence</td><td></td><td>String</td><td>Sequence to use when the actor is killed by some non-standard means (e.g. suicide). </td></tr>
<tr><td>Delay</td><td>0</td><td>Integer</td><td>Delay the spawn of the death animation by this many ticks. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithDecoration
Displays a custom UI overlay relative to the actor's mouseover bounds.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Image</td><td></td><td>String</td><td>Image used for this decoration. Defaults to the actor's type. </td></tr>
<tr><td>Sequence</td><td><em>(required)</em></td><td>String</td><td>Sequence used for this decoration (can be animated). </td></tr>
<tr><td>Palette</td><td>chrome</td><td>String</td><td>Palette to render the sprite in. Reference the world actor's PaletteFrom* traits. </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Custom palette is a player palette BaseName </td></tr>
<tr><td>Position</td><td>TopLeft</td><td>String</td><td>Position in the actor's selection box to draw the decoration. </td></tr>
<tr><td>ValidRelationships</td><td>Ally</td><td>PlayerRelationship</td><td>Player relationships who can view the decoration. </td></tr>
<tr><td>RequiresSelection</td><td>False</td><td>Boolean</td><td>Should this be visible only when selected? </td></tr>
<tr><td>Margin</td><td>0,0</td><td>2D Integer</td><td>Offset sprite center position from the selection box edge. </td></tr>
<tr><td>Offsets</td><td></td><td>Dictionary with Key: BooleanExpression, Value 2D Integer</td><td>Screen-space offsets to apply when defined conditions are enabled. A dictionary of [condition string]: [x, y offset]. </td></tr>
<tr><td>BlinkInterval</td><td>5</td><td>Integer</td><td>The number of ticks that each step in the blink pattern in active. </td></tr>
<tr><td>BlinkPattern</td><td></td><td>Collection of BlinkState</td><td>A pattern of ticks (BlinkInterval long) where the decoration is visible or hidden. </td></tr>
<tr><td>BlinkPatterns</td><td></td><td>Dictionary with Key: BooleanExpression, Value Collection of BlinkState</td><td>Override blink conditions to use when defined conditions are enabled. A dictionary of [condition string]: [pattern]. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithDeliveryAnimation
Building animation to play when ProductionAirdrop is used to deliver units.

Requires trait: [`WithSpriteBody`](#withspritebody).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ActiveSequence</td><td>active</td><td>String</td><td></td></tr>
<tr><td>Body</td><td>body</td><td>String</td><td>Which sprite body to play the animation on. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithDockedOverlay
Rendered when a harvester is docked.

Requires traits: [`BodyOrientation`](#bodyorientation), [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Sequence</td><td>docking-overlay</td><td>String</td><td>Sequence name to use </td></tr>
<tr><td>Offset</td><td>0,0,0</td><td>3D World Vector</td><td>Position relative to body </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Custom palette is a player palette BaseName </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithDockingAnimation
Requires traits: [`Harvester`](#harvester), [`WithSpriteBody`](#withspritebody).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>DockSequence</td><td>dock</td><td>String</td><td>Displayed when docking to refinery. </td></tr>
<tr><td>DockLoopSequence</td><td>dock-loop</td><td>String</td><td>Looped while unloading at refinery. </td></tr>
</table>

### WithFacingSpriteBody

Requires traits: [`BodyOrientation`](#bodyorientation), [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>StartSequence</td><td></td><td>String</td><td>Animation to play when the actor is created. </td></tr>
<tr><td>Sequence</td><td>idle</td><td>String</td><td>Animation to play when the actor is idle. </td></tr>
<tr><td>Name</td><td>body</td><td>String</td><td>Identifier used to assign modifying traits to this sprite body. </td></tr>
<tr><td>ForceToGround</td><td>False</td><td>Boolean</td><td>Forces sprite body to be rendered on ground regardless of actor altitude (for example for custom shadow sprites). </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name. </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Palette is a player palette BaseName. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithGateSpriteBody

Requires traits: [`Gate`](#gate), [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>WallConnections</td><td></td><td>Collection of 2D Cell Vector</td><td>Cells (outside the gate footprint) that contain wall cells that can connect to the gate </td></tr>
<tr><td>Type</td><td>wall</td><td>String</td><td>Wall type for connections </td></tr>
<tr><td>OpenSequence</td><td></td><td>String</td><td>Override sequence to use when fully open. </td></tr>
<tr><td>StartSequence</td><td></td><td>String</td><td>Animation to play when the actor is created. </td></tr>
<tr><td>Sequence</td><td>idle</td><td>String</td><td>Animation to play when the actor is idle. </td></tr>
<tr><td>Name</td><td>body</td><td>String</td><td>Identifier used to assign modifying traits to this sprite body. </td></tr>
<tr><td>ForceToGround</td><td>False</td><td>Boolean</td><td>Forces sprite body to be rendered on ground regardless of actor altitude (for example for custom shadow sprites). </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name. </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Palette is a player palette BaseName. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithHarvestAnimation
Requires traits: [`Harvester`](#harvester), [`WithSpriteBody`](#withspritebody).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>HarvestSequence</td><td>harvest</td><td>String</td><td>Displayed while harvesting. </td></tr>
<tr><td>Body</td><td>body</td><td>String</td><td>Which sprite body to play the animation on. </td></tr>
</table>

### WithHarvesterPipsDecoration
Requires trait: [`Harvester`](#harvester).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>PipCount</td><td><em>(required)</em></td><td>Integer</td><td>Number of pips to display how filled unit is. </td></tr>
<tr><td>PipStride</td><td>0,0</td><td>2D Integer</td><td>If non-zero, override the spacing between adjacent pips. </td></tr>
<tr><td>Image</td><td>pips</td><td>String</td><td>Image that defines the pip sequences. </td></tr>
<tr><td>EmptySequence</td><td>pip-empty</td><td>String</td><td>Sequence used for empty pips. </td></tr>
<tr><td>FullSequence</td><td>pip-green</td><td>String</td><td>Sequence used for full pips that aren't defined in ResourceSequences. </td></tr>
<tr><td>ResourceSequences</td><td></td><td>Dictionary with Key: String, Value String</td><td>Pip sequence to use for specific resource types. </td></tr>
<tr><td>Palette</td><td>chrome</td><td>String</td><td></td></tr>
<tr><td>Position</td><td>TopLeft</td><td>String</td><td>Position in the actor's selection box to draw the decoration. </td></tr>
<tr><td>ValidRelationships</td><td>Ally</td><td>PlayerRelationship</td><td>Player relationships who can view the decoration. </td></tr>
<tr><td>RequiresSelection</td><td>False</td><td>Boolean</td><td>Should this be visible only when selected? </td></tr>
<tr><td>Margin</td><td>0,0</td><td>2D Integer</td><td>Offset sprite center position from the selection box edge. </td></tr>
<tr><td>Offsets</td><td></td><td>Dictionary with Key: BooleanExpression, Value 2D Integer</td><td>Screen-space offsets to apply when defined conditions are enabled. A dictionary of [condition string]: [x, y offset]. </td></tr>
<tr><td>BlinkInterval</td><td>5</td><td>Integer</td><td>The number of ticks that each step in the blink pattern in active. </td></tr>
<tr><td>BlinkPattern</td><td></td><td>Collection of BlinkState</td><td>A pattern of ticks (BlinkInterval long) where the decoration is visible or hidden. </td></tr>
<tr><td>BlinkPatterns</td><td></td><td>Dictionary with Key: BooleanExpression, Value Collection of BlinkState</td><td>Override blink conditions to use when defined conditions are enabled. A dictionary of [condition string]: [pattern]. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithHarvestOverlay
Displays an overlay whenever resources are harvested by the actor.

Requires traits: [`BodyOrientation`](#bodyorientation), [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Sequence</td><td>harvest</td><td>String</td><td>Sequence name to use </td></tr>
<tr><td>LocalOffset</td><td>0,0,0</td><td>3D World Vector</td><td>Position relative to body </td></tr>
<tr><td>Palette</td><td>effect</td><td>String</td><td></td></tr>
</table>

### WithIdleAnimation
Periodically plays an idle animation, replacing the default body animation.

Requires trait: [`WithSpriteBody`](#withspritebody).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Sequences</td><td>active</td><td>Collection of String</td><td>Sequence names to use. </td></tr>
<tr><td>Interval</td><td>750</td><td>Collection of Integer</td><td>The amount of time (in ticks) between animations. Two values indicate a range between which a random value is chosen. </td></tr>
<tr><td>Body</td><td>body</td><td>String</td><td>Which sprite body to play the animation on. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithIdleOverlay
Renders a decorative animation on units and buildings.

Requires traits: [`BodyOrientation`](#bodyorientation), [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Image</td><td></td><td>String</td><td>Image used for this decoration. Defaults to the actor's type. </td></tr>
<tr><td>StartSequence</td><td></td><td>String</td><td>Animation to play when the actor is created. </td></tr>
<tr><td>Sequence</td><td>idle-overlay</td><td>String</td><td>Sequence name to use </td></tr>
<tr><td>Offset</td><td>0,0,0</td><td>3D World Vector</td><td>Position relative to body </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Custom palette is a player palette BaseName </td></tr>
<tr><td>IsDecoration</td><td>False</td><td>Boolean</td><td></td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithInfantryBody
Requires trait: [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>MinIdleDelay</td><td>30</td><td>Integer</td><td></td></tr>
<tr><td>MaxIdleDelay</td><td>110</td><td>Integer</td><td></td></tr>
<tr><td>MoveSequence</td><td>run</td><td>String</td><td></td></tr>
<tr><td>DefaultAttackSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>AttackSequences</td><td></td><td>Dictionary with Key: String, Value Collection of String</td><td>Attack sequence to use for each armament. A dictionary of [armament name]: [sequence name(s)]. Multiple sequence names can be defined to specify per-burst animations. </td></tr>
<tr><td>IdleSequences</td><td></td><td>Collection of String</td><td></td></tr>
<tr><td>StandSequences</td><td>stand</td><td>Collection of String</td><td></td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Palette is a player palette BaseName </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithMakeAnimation
Replaces the sprite during construction/deploy/undeploy.

Requires trait: [`WithSpriteBody`](#withspritebody).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Sequence</td><td>make</td><td>String</td><td>Sequence name to use. </td></tr>
<tr><td>Condition</td><td></td><td>String</td><td>The condition to grant to self while the make animation is playing. </td></tr>
<tr><td>BodyNames</td><td>body</td><td>Collection of String</td><td>Apply to sprite bodies with these names. </td></tr>
</table>

### WithMakeOverlay
Draws an overlay on top of a make animation.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Sequence</td><td><em>(required)</em></td><td>String</td><td>Sequence name to use. </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name. </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Custom palette is a player palette BaseName. </td></tr>
</table>

### WithMoveAnimation
Requires trait: [`WithSpriteBody`](#withspritebody).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>MoveSequence</td><td>move</td><td>String</td><td>Displayed while moving. </td></tr>
<tr><td>Body</td><td>body</td><td>String</td><td>Which sprite body to modify. </td></tr>
<tr><td>ValidMovementTypes</td><td>Horizontal</td><td>MovementType</td><td>Apply condition on listed movement types. Available options are: None, Horizontal, Vertical, Turn. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithMuzzleOverlay
Renders the MuzzleSequence from the Armament trait.

Requires traits: [`Armament`](#armament), [`AttackBase`](#attackbase), [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>IgnoreOffset</td><td>False</td><td>Boolean</td><td>Ignore the weapon position, and always draw relative to the center of the actor </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithNameTagDecoration
Displays the player name above the unit
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>MaxLength</td><td>10</td><td>Integer</td><td></td></tr>
<tr><td>Font</td><td>TinyBold</td><td>String</td><td></td></tr>
<tr><td>Color</td><td>FFFFFF</td><td>Color (RRGGBB[AA] notation)</td><td>Display in this color when not using the player color. </td></tr>
<tr><td>UsePlayerColor</td><td>False</td><td>Boolean</td><td>Use the player color of the current owner. </td></tr>
<tr><td>Position</td><td>TopLeft</td><td>String</td><td>Position in the actor's selection box to draw the decoration. </td></tr>
<tr><td>ValidRelationships</td><td>Ally</td><td>PlayerRelationship</td><td>Player relationships who can view the decoration. </td></tr>
<tr><td>RequiresSelection</td><td>False</td><td>Boolean</td><td>Should this be visible only when selected? </td></tr>
<tr><td>Margin</td><td>0,0</td><td>2D Integer</td><td>Offset sprite center position from the selection box edge. </td></tr>
<tr><td>Offsets</td><td></td><td>Dictionary with Key: BooleanExpression, Value 2D Integer</td><td>Screen-space offsets to apply when defined conditions are enabled. A dictionary of [condition string]: [x, y offset]. </td></tr>
<tr><td>BlinkInterval</td><td>5</td><td>Integer</td><td>The number of ticks that each step in the blink pattern in active. </td></tr>
<tr><td>BlinkPattern</td><td></td><td>Collection of BlinkState</td><td>A pattern of ticks (BlinkInterval long) where the decoration is visible or hidden. </td></tr>
<tr><td>BlinkPatterns</td><td></td><td>Dictionary with Key: BooleanExpression, Value Collection of BlinkState</td><td>Override blink conditions to use when defined conditions are enabled. A dictionary of [condition string]: [pattern]. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithParachute
Renders a parachute on units.

Requires traits: [`BodyOrientation`](#bodyorientation), [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Image</td><td></td><td>String</td><td>The image that contains the parachute sequences. </td></tr>
<tr><td>OpeningSequence</td><td></td><td>String</td><td>Parachute opening sequence. </td></tr>
<tr><td>Sequence</td><td></td><td>String</td><td>Parachute idle sequence. </td></tr>
<tr><td>ClosingSequence</td><td></td><td>String</td><td>Parachute closing sequence. Defaults to opening sequence played backwards. </td></tr>
<tr><td>Palette</td><td>player</td><td>String</td><td>Palette used to render the parachute. </td></tr>
<tr><td>IsPlayerPalette</td><td>True</td><td>Boolean</td><td></td></tr>
<tr><td>Offset</td><td>0,0,384</td><td>3D World Vector</td><td>Parachute position relative to the paradropped unit. </td></tr>
<tr><td>ShadowImage</td><td></td><td>String</td><td>The image that contains the shadow sequence for the paradropped unit. </td></tr>
<tr><td>ShadowSequence</td><td></td><td>String</td><td>Paradropped unit's shadow sequence. </td></tr>
<tr><td>ShadowColor</td><td>0000008C</td><td>Color (RRGGBB[AA] notation)</td><td>Color to render the paradropped unit's shadow. </td></tr>
<tr><td>ShadowOffset</td><td>0,128,0</td><td>3D World Vector</td><td>Shadow position relative to the paradropped unit's intended landing position. </td></tr>
<tr><td>ShadowZOffset</td><td>0</td><td>Integer</td><td>Z-offset to apply on the shadow sequence. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithProductionDoorOverlay
Play an animation when a unit exits or blocks the exit after production finished.

Requires traits: [`BodyOrientation`](#bodyorientation), [`Building`](#building), [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Sequence</td><td>build-door</td><td>String</td><td></td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithProductionOverlay
Renders an animation when the Production trait of the actor is activated.
Works both with per player ClassicProductionQueue and per building ProductionQueue, but needs any of these.

Requires traits: [`BodyOrientation`](#bodyorientation), [`Production`](#production), [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Queues</td><td></td><td>Set of System.String[]</td><td>Queues that should be producing for this overlay to render. </td></tr>
<tr><td>Sequence</td><td>production-overlay</td><td>String</td><td>Sequence name to use </td></tr>
<tr><td>Offset</td><td>0,0,0</td><td>3D World Vector</td><td>Position relative to body </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Custom palette is a player palette BaseName </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithRangeCircle
Renders an arbitrary circle when selected or placing a structure
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Type</td><td></td><td>String</td><td>Type of range circle. used to decide which circles to draw on other structures during building placement. </td></tr>
<tr><td>Color</td><td>FFFFFF80</td><td>Color (RRGGBB[AA] notation)</td><td>Color of the circle </td></tr>
<tr><td>Width</td><td>1</td><td>Real Number</td><td>Border width. </td></tr>
<tr><td>BorderColor</td><td>00000060</td><td>Color (RRGGBB[AA] notation)</td><td>Color of the border. </td></tr>
<tr><td>BorderWidth</td><td>3</td><td>Real Number</td><td>Range circle border width. </td></tr>
<tr><td>UsePlayerColor</td><td>False</td><td>Boolean</td><td>If set, the color of the owning player will be used instead of `Color`. </td></tr>
<tr><td>ValidRelationships</td><td>Ally</td><td>PlayerRelationship</td><td>Player relationships which will be able to see the circle. Valid values are combinations of `None`, `Ally`, `Enemy` and `Neutral`. </td></tr>
<tr><td>Visible</td><td>WhenSelected</td><td>RangeCircleVisibility</td><td>When to show the range circle. Valid values are `Always`, and `WhenSelected` </td></tr>
<tr><td>Range</td><td>0c0</td><td>1D World Distance</td><td>Range of the circle </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithRepairOverlay
Displays an overlay when the building is being repaired by the player.

Requires traits: [`BodyOrientation`](#bodyorientation), [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>StartSequence</td><td></td><td>String</td><td>Sequence to use upon repair beginning. </td></tr>
<tr><td>Sequence</td><td>active</td><td>String</td><td>Sequence name to play once during repair intervals or repeatedly if a start sequence is set. </td></tr>
<tr><td>EndSequence</td><td></td><td>String</td><td>Sequence to use after repairing has finished. </td></tr>
<tr><td>Offset</td><td>0,0,0</td><td>3D World Vector</td><td>Position relative to body </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Custom palette is a player palette BaseName </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithResourceLevelOverlay
Displays the fill status of PlayerResources with an extra sprite overlay on the actor.

Requires traits: [`RenderSprites`](#rendersprites), [`WithSpriteBody`](#withspritebody).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Sequence</td><td>resources</td><td>String</td><td>Sequence name to use </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name. </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Custom palette is a player palette BaseName. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithResourceLevelSpriteBody
Render trait for buildings that change the sprite according to the remaining resource storage capacity across all depots.

Requires trait: [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Stages</td><td>10</td><td>Integer</td><td>Internal resource stages. Does not have to match number of sequence frames. </td></tr>
<tr><td>StartSequence</td><td></td><td>String</td><td>Animation to play when the actor is created. </td></tr>
<tr><td>Sequence</td><td>idle</td><td>String</td><td>Animation to play when the actor is idle. </td></tr>
<tr><td>Name</td><td>body</td><td>String</td><td>Identifier used to assign modifying traits to this sprite body. </td></tr>
<tr><td>ForceToGround</td><td>False</td><td>Boolean</td><td>Forces sprite body to be rendered on ground regardless of actor altitude (for example for custom shadow sprites). </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name. </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Palette is a player palette BaseName. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithResourceStoragePipsDecoration
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>PipCount</td><td><em>(required)</em></td><td>Integer</td><td>Number of pips to display how filled unit is. </td></tr>
<tr><td>PipStride</td><td>0,0</td><td>2D Integer</td><td>If non-zero, override the spacing between adjacing pips. </td></tr>
<tr><td>Image</td><td>pips</td><td>String</td><td>Image that defines the pip sequences. </td></tr>
<tr><td>EmptySequence</td><td>pip-empty</td><td>String</td><td>Sequence used for empty pips. </td></tr>
<tr><td>FullSequence</td><td>pip-green</td><td>String</td><td>Sequence used for full pips. </td></tr>
<tr><td>Palette</td><td>chrome</td><td>String</td><td></td></tr>
<tr><td>Position</td><td>TopLeft</td><td>String</td><td>Position in the actor's selection box to draw the decoration. </td></tr>
<tr><td>ValidRelationships</td><td>Ally</td><td>PlayerRelationship</td><td>Player relationships who can view the decoration. </td></tr>
<tr><td>RequiresSelection</td><td>False</td><td>Boolean</td><td>Should this be visible only when selected? </td></tr>
<tr><td>Margin</td><td>0,0</td><td>2D Integer</td><td>Offset sprite center position from the selection box edge. </td></tr>
<tr><td>Offsets</td><td></td><td>Dictionary with Key: BooleanExpression, Value 2D Integer</td><td>Screen-space offsets to apply when defined conditions are enabled. A dictionary of [condition string]: [x, y offset]. </td></tr>
<tr><td>BlinkInterval</td><td>5</td><td>Integer</td><td>The number of ticks that each step in the blink pattern in active. </td></tr>
<tr><td>BlinkPattern</td><td></td><td>Collection of BlinkState</td><td>A pattern of ticks (BlinkInterval long) where the decoration is visible or hidden. </td></tr>
<tr><td>BlinkPatterns</td><td></td><td>Dictionary with Key: BooleanExpression, Value Collection of BlinkState</td><td>Override blink conditions to use when defined conditions are enabled. A dictionary of [condition string]: [pattern]. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithResupplyAnimation
Replaces the default animation when actor resupplies a unit.

Requires trait: [`WithSpriteBody`](#withspritebody).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Sequence</td><td>active</td><td>String</td><td>Sequence name to use </td></tr>
<tr><td>Body</td><td>body</td><td>String</td><td>Which sprite body to play the animation on. </td></tr>
<tr><td>PlayAnimationOn</td><td>Rearm, Repair</td><td>ResupplyType</td><td>Events leading to the animation getting played. Possible values currently are: Rearm, Repair. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithShadow
Clones the actor sprite with another palette below it.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ShadowColor</td><td>0000008C</td><td>Color (RRGGBB[AA] notation)</td><td>Color to draw shadow. </td></tr>
<tr><td>Offset</td><td>0,0,0</td><td>3D World Vector</td><td>Shadow position offset relative to actor position (ground level). </td></tr>
<tr><td>ZOffset</td><td>-5</td><td>Integer</td><td>Shadow Z offset relative to actor sprite. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithSpriteBarrel
Renders barrels for units with the Turreted trait.

Requires traits: [`Armament`](#armament), [`BodyOrientation`](#bodyorientation), [`RenderSprites`](#rendersprites), [`Turreted`](#turreted).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Sequence</td><td>barrel</td><td>String</td><td>Sequence name to use. </td></tr>
<tr><td>Armament</td><td>primary</td><td>String</td><td>Armament to use for recoil. </td></tr>
<tr><td>LocalOffset</td><td>0,0,0</td><td>3D World Vector</td><td>Visual offset. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithSpriteBody
Default trait for rendering sprite-based actors.

Requires trait: [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>StartSequence</td><td></td><td>String</td><td>Animation to play when the actor is created. </td></tr>
<tr><td>Sequence</td><td>idle</td><td>String</td><td>Animation to play when the actor is idle. </td></tr>
<tr><td>Name</td><td>body</td><td>String</td><td>Identifier used to assign modifying traits to this sprite body. </td></tr>
<tr><td>ForceToGround</td><td>False</td><td>Boolean</td><td>Forces sprite body to be rendered on ground regardless of actor altitude (for example for custom shadow sprites). </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name. </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Palette is a player palette BaseName. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithSpriteControlGroupDecoration
Renders Ctrl groups using pixel art.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Palette</td><td>chrome</td><td>String</td><td></td></tr>
<tr><td>Image</td><td>pips</td><td>String</td><td></td></tr>
<tr><td>GroupSequence</td><td>groups</td><td>String</td><td>Sprite sequence used to render the control group 0-9 numbers. </td></tr>
<tr><td>Position</td><td>TopLeft</td><td>String</td><td>Position in the actor's selection box to draw the decoration. </td></tr>
<tr><td>Margin</td><td>0,0</td><td>2D Integer</td><td>Offset sprite center position from the selection box edge. </td></tr>
</table>

### WithSpriteTurret
Renders turrets for units with the Turreted trait.

Requires traits: [`Armament`](#armament), [`BodyOrientation`](#bodyorientation), [`RenderSprites`](#rendersprites), [`Turreted`](#turreted).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Sequence</td><td>turret</td><td>String</td><td>Sequence name to use </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Palette is a player palette BaseName </td></tr>
<tr><td>Turret</td><td>primary</td><td>String</td><td>Turreted 'Turret' key to display </td></tr>
<tr><td>Recoils</td><td>True</td><td>Boolean</td><td>Render recoil </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithSupportPowerActivationAnimation
Replaces the building animation when a support power is triggered.

Requires trait: [`WithSpriteBody`](#withspritebody).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Sequence</td><td>active</td><td>String</td><td>Sequence name to use </td></tr>
<tr><td>Body</td><td>body</td><td>String</td><td>Which sprite body to play the animation on. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithSupportPowerActivationOverlay
Displays an overlay when a support power is triggered.

Requires traits: [`BodyOrientation`](#bodyorientation), [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Sequence</td><td>active</td><td>String</td><td>Sequence name to use </td></tr>
<tr><td>Offset</td><td>0,0,0</td><td>3D World Vector</td><td>Position relative to body </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Custom palette is a player palette BaseName </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithTextControlGroupDecoration
Renders Ctrl groups using typeface.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Font</td><td>TinyBold</td><td>String</td><td></td></tr>
<tr><td>Color</td><td>FFFFFF</td><td>Color (RRGGBB[AA] notation)</td><td>Display in this color when not using the player color. </td></tr>
<tr><td>UsePlayerColor</td><td>False</td><td>Boolean</td><td>Use the player color of the current owner. </td></tr>
<tr><td>Position</td><td>TopLeft</td><td>String</td><td>Position in the actor's selection box to draw the decoration. </td></tr>
<tr><td>Margin</td><td>0,0</td><td>2D Integer</td><td>Offset text center position from the selection box edge. </td></tr>
</table>

### WithTextDecoration
Displays a text overlay relative to the selection box.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Text</td><td><em>(required)</em></td><td>String</td><td></td></tr>
<tr><td>Font</td><td>TinyBold</td><td>String</td><td></td></tr>
<tr><td>Color</td><td>FFFFFF</td><td>Color (RRGGBB[AA] notation)</td><td>Display in this color when not using the player color. </td></tr>
<tr><td>UsePlayerColor</td><td>False</td><td>Boolean</td><td>Use the player color of the current owner. </td></tr>
<tr><td>Position</td><td>TopLeft</td><td>String</td><td>Position in the actor's selection box to draw the decoration. </td></tr>
<tr><td>ValidRelationships</td><td>Ally</td><td>PlayerRelationship</td><td>Player relationships who can view the decoration. </td></tr>
<tr><td>RequiresSelection</td><td>False</td><td>Boolean</td><td>Should this be visible only when selected? </td></tr>
<tr><td>Margin</td><td>0,0</td><td>2D Integer</td><td>Offset sprite center position from the selection box edge. </td></tr>
<tr><td>Offsets</td><td></td><td>Dictionary with Key: BooleanExpression, Value 2D Integer</td><td>Screen-space offsets to apply when defined conditions are enabled. A dictionary of [condition string]: [x, y offset]. </td></tr>
<tr><td>BlinkInterval</td><td>5</td><td>Integer</td><td>The number of ticks that each step in the blink pattern in active. </td></tr>
<tr><td>BlinkPattern</td><td></td><td>Collection of BlinkState</td><td>A pattern of ticks (BlinkInterval long) where the decoration is visible or hidden. </td></tr>
<tr><td>BlinkPatterns</td><td></td><td>Dictionary with Key: BooleanExpression, Value Collection of BlinkState</td><td>Override blink conditions to use when defined conditions are enabled. A dictionary of [condition string]: [pattern]. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithTurretAimAnimation
Requires traits: [`AttackBase`](#attackbase), [`WithSpriteTurret`](#withspriteturret).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Armament</td><td>primary</td><td>String</td><td>Armament name </td></tr>
<tr><td>Turret</td><td>primary</td><td>String</td><td>Turret name </td></tr>
<tr><td>Sequence</td><td><em>(required)</em></td><td>String</td><td>Displayed while targeting. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithTurretAttackAnimation
Requires traits: [`Armament`](#armament), [`WithSpriteTurret`](#withspriteturret).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Armament</td><td>primary</td><td>String</td><td>Armament name </td></tr>
<tr><td>Turret</td><td>primary</td><td>String</td><td>Turret name </td></tr>
<tr><td>Sequence</td><td></td><td>String</td><td>Displayed while attacking. </td></tr>
<tr><td>Delay</td><td>0</td><td>Integer</td><td>Delay in ticks before animation starts, either relative to attack preparation or attack. </td></tr>
<tr><td>DelayRelativeTo</td><td>Preparation</td><td>AttackDelayType</td><td>Should the animation be delayed relative to preparation or actual attack? </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithVoxelBarrel
Requires traits: [`Armament`](#armament), [`RenderVoxels`](#rendervoxels), [`Turreted`](#turreted).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Sequence</td><td>barrel</td><td>String</td><td>Voxel sequence name to use </td></tr>
<tr><td>Armament</td><td>primary</td><td>String</td><td>Armament to use for recoil </td></tr>
<tr><td>LocalOffset</td><td>0,0,0</td><td>3D World Vector</td><td>Visual offset </td></tr>
<tr><td>LocalOrientation</td><td>0,0,0</td><td>3D World Rotation</td><td>Rotate the barrel relative to the body </td></tr>
<tr><td>ShowShadow</td><td>True</td><td>Boolean</td><td>Defines if the Voxel should have a shadow. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithVoxelBody
Also returns a default selection size that is calculated automatically from the voxel dimensions.

Requires trait: [`RenderVoxels`](#rendervoxels).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Sequence</td><td>idle</td><td>String</td><td></td></tr>
<tr><td>ShowShadow</td><td>True</td><td>Boolean</td><td>Defines if the Voxel should have a shadow. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithVoxelTurret
Requires traits: [`RenderVoxels`](#rendervoxels), [`Turreted`](#turreted).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Sequence</td><td>turret</td><td>String</td><td>Voxel sequence name to use </td></tr>
<tr><td>Turret</td><td>primary</td><td>String</td><td>Turreted 'Turret' key to display </td></tr>
<tr><td>ShowShadow</td><td>True</td><td>Boolean</td><td>Defines if the Voxel should have a shadow. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithWallSpriteBody
Render trait for actors that change sprites if neighbors with the same trait are present.

Requires traits: [`Building`](#building), [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Type</td><td>wall</td><td>String</td><td></td></tr>
<tr><td>StartSequence</td><td></td><td>String</td><td>Animation to play when the actor is created. </td></tr>
<tr><td>Sequence</td><td>idle</td><td>String</td><td>Animation to play when the actor is idle. </td></tr>
<tr><td>Name</td><td>body</td><td>String</td><td>Identifier used to assign modifying traits to this sprite body. </td></tr>
<tr><td>ForceToGround</td><td>False</td><td>Boolean</td><td>Forces sprite body to be rendered on ground regardless of actor altitude (for example for custom shadow sprites). </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name. </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Palette is a player palette BaseName. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### EmptySelectionDecorations
Requires trait: [`Interactable`](#interactable).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>SelectionBoxColor</td><td>FFFFFF</td><td>Color (RRGGBB[AA] notation)</td><td></td></tr>
</table>

### OutlinedSelectionDecorations
Displays thick and outlined healthbars as well as sprite based selection boxes.

Requires trait: [`Interactable`](#interactable).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Image</td><td>outline</td><td>String</td><td>Image used for the undamaged decoration. </td></tr>
<tr><td>DamagedImage</td><td>outline-yellow</td><td>String</td><td></td></tr>
<tr><td>CriticallyDamagedImage</td><td>outline-red</td><td>String</td><td></td></tr>
<tr><td>TopLeftSequence</td><td>top-left</td><td>String</td><td></td></tr>
<tr><td>TopRightSequence</td><td>top-right</td><td>String</td><td></td></tr>
<tr><td>BottomLeftSequence</td><td>bottom-left</td><td>String</td><td></td></tr>
<tr><td>BottomRightSequence</td><td>bottom-right</td><td>String</td><td></td></tr>
<tr><td>Spacers</td><td>False</td><td>Boolean</td><td>Render left, bottom, right and top as well. </td></tr>
<tr><td>LeftSequence</td><td>left</td><td>String</td><td></td></tr>
<tr><td>BottomSequence</td><td>bottom</td><td>String</td><td></td></tr>
<tr><td>RightSequence</td><td>right</td><td>String</td><td></td></tr>
<tr><td>TopSequence</td><td>top</td><td>String</td><td></td></tr>
<tr><td>Palette</td><td>cursor</td><td>String</td><td>Palette to render the sprite in. Reference the world actor's PaletteFrom* traits. </td></tr>
<tr><td>SelectionBoxColor</td><td>FFFFFF</td><td>Color (RRGGBB[AA] notation)</td><td></td></tr>
</table>


### ActorLostNotification
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Notification</td><td>UnitLost</td><td>String</td><td></td></tr>
<tr><td>NotifyAll</td><td>False</td><td>Boolean</td><td></td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### AmbientSound
Plays a looping audio file at the actor position. Attach this to the `World` actor to cover the whole map.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>SoundFiles</td><td><em>(required)</em></td><td>Collection of String</td><td></td></tr>
<tr><td>Delay</td><td>0</td><td>Collection of Integer</td><td>Initial delay (in ticks) before playing the sound for the first time. Two values indicate a random delay range. </td></tr>
<tr><td>Interval</td><td>0</td><td>Collection of Integer</td><td>Interval between playing the sound (in ticks). Two values indicate a random delay range. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### AnnounceOnKill
Play the Kill voice of this actor when eliminating enemies.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Interval</td><td>5000</td><td>Integer</td><td>Minimum duration (in milliseconds) between sound events. </td></tr>
<tr><td>Voice</td><td>Kill</td><td>String</td><td>Voice to use when killing something. </td></tr>
</table>

### AnnounceOnSeen
Players will be notified when this actor becomes visible to them.
Requires the 'EnemyWatcher' trait on the player actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>PingRadar</td><td>False</td><td>Boolean</td><td>Should there be a radar ping on enemies' radar at the actor's location when they see him </td></tr>
<tr><td>Notification</td><td></td><td>String</td><td></td></tr>
<tr><td>AnnounceNeutrals</td><td>False</td><td>Boolean</td><td></td></tr>
</table>

### AttackSounds
Played when preparing for an attack or attacking.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Sounds</td><td></td><td>Collection of String</td><td>Play a randomly selected sound from this list when preparing for an attack or attacking. </td></tr>
<tr><td>Delay</td><td>0</td><td>Integer</td><td>Delay in ticks before sound starts, either relative to attack preparation or attack. </td></tr>
<tr><td>DelayRelativeTo</td><td>Preparation</td><td>AttackDelayType</td><td>Should the sound be delayed relative to preparation or actual attack? </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### CaptureNotification
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Notification</td><td>BuildingCaptured</td><td>String</td><td>The speech notification to play to the new owner. </td></tr>
<tr><td>NewOwnerVoice</td><td>True</td><td>Boolean</td><td>Specifies if Notification is played with the voice of the new owners faction. </td></tr>
<tr><td>LoseNotification</td><td></td><td>String</td><td>The speech notification to play to the old owner. </td></tr>
<tr><td>LoseNewOwnerVoice</td><td>False</td><td>Boolean</td><td>Specifies if LoseNotification is played with the voice of the new owners faction. </td></tr>
</table>

### DeathSounds
Sounds to play when killed.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Voice</td><td>Die</td><td>String</td><td>Death notification voice. </td></tr>
<tr><td>VolumeMultiplier</td><td>1</td><td>Real Number</td><td>Multiply volume with this factor. </td></tr>
<tr><td>DeathTypes</td><td></td><td>Collection of DamageType</td><td>Damage types that this should be used for (defined on the warheads). If empty, this will be used as the default sound for all death types. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### SoundOnDamageTransition
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>DamagedSounds</td><td></td><td>Collection of String</td><td>Play a random sound from this list when damaged. </td></tr>
<tr><td>DestroyedSounds</td><td></td><td>Collection of String</td><td>Play a random sound from this list when destroyed. </td></tr>
<tr><td>DamageTypes</td><td></td><td>Collection of DamageType</td><td>DamageType(s) that trigger the sounds. Leave empty to always trigger a sound. </td></tr>
</table>

### VoiceAnnouncement
Plays a voice clip when the trait is enabled.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Voice</td><td><em>(required)</em></td><td>String</td><td>Voice to play. </td></tr>
<tr><td>ValidRelationships</td><td>Enemy, Neutral, Ally</td><td>PlayerRelationship</td><td>Player relationships who can hear this voice. </td></tr>
<tr><td>PlayToOwner</td><td>True</td><td>Boolean</td><td>Play the voice to the owning player even if Stance.Ally is not included in ValidStances. </td></tr>
<tr><td>OneShot</td><td>False</td><td>Boolean</td><td>Disable the announcement after it has been triggered. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>


### CustomTerrainRenderer


### AcceptsDeliveredResources
Tag trait for actors with `ResourceCollector`.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>DeliveryVehicleType</td><td></td><td>Collection of String</td><td></td></tr>
</table>

### BaseBotModule
Manages the initial base.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### CubePickupBotModule
Put this on the Player actor. Manages cube collection.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ExcludedUnitTypes</td><td></td><td>Set of System.String[]</td><td>Actor types that should not start hunting for cubes. </td></tr>
<tr><td>IncludedUnitTypes</td><td></td><td>Set of System.String[]</td><td>Only these actor types should start hunting for cubes. </td></tr>
<tr><td>ScanForCubesInterval</td><td>50</td><td>Integer</td><td>Interval (in ticks) between giving out orders to idle units. </td></tr>
<tr><td>MaxProximityRadius</td><td>0</td><td>Integer</td><td>Only move this far away from base. Disabled if set to zero. </td></tr>
<tr><td>EnemyAvoidanceRadius</td><td>8c0</td><td>1D World Distance</td><td>Avoid enemy actors nearby when searching for cubes. Should be somewhere near the max weapon range. </td></tr>
<tr><td>CheckTargetsForVisibility</td><td>True</td><td>Boolean</td><td>Should visibility (Shroud, Fog, Cloak, etc) be considered when searching for cubes? </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### CustomBaseBuilderBotModule
Manages AI base construction.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ConstructionYardTypes</td><td></td><td>Set of System.String[]</td><td>Tells the AI what building types are considered construction yards. </td></tr>
<tr><td>VehiclesFactoryTypes</td><td></td><td>Set of System.String[]</td><td>Tells the AI what building types are considered vehicle production facilities. </td></tr>
<tr><td>RefineryTypes</td><td></td><td>Set of System.String[]</td><td>Tells the AI what building types are considered refineries. </td></tr>
<tr><td>MinerTypes</td><td></td><td>Set of System.String[]</td><td>Tells the AI what building types are considered miners. </td></tr>
<tr><td>PowerTypes</td><td></td><td>Set of System.String[]</td><td>Tells the AI what building types are considered power plants. </td></tr>
<tr><td>BarracksTypes</td><td></td><td>Set of System.String[]</td><td>Tells the AI what building types are considered infantry production facilities. </td></tr>
<tr><td>ProductionTypes</td><td></td><td>Set of System.String[]</td><td>Tells the AI what building types are considered production facilities. </td></tr>
<tr><td>NavalProductionTypes</td><td></td><td>Set of System.String[]</td><td>Tells the AI what building types are considered naval production facilities. </td></tr>
<tr><td>SiloTypes</td><td></td><td>Set of System.String[]</td><td>Tells the AI what building types are considered silos (resource storage). </td></tr>
<tr><td>BuildingQueues</td><td>Building</td><td>Set of System.String[]</td><td>Production queues AI uses for buildings. </td></tr>
<tr><td>DefenseQueues</td><td>Defense</td><td>Set of System.String[]</td><td>Production queues AI uses for defenses. </td></tr>
<tr><td>MinBaseRadius</td><td>2</td><td>Integer</td><td>Minimum distance in cells from center of the base when checking for building placement. </td></tr>
<tr><td>MaxBaseRadius</td><td>20</td><td>Integer</td><td>Radius in cells around the center of the base to expand. </td></tr>
<tr><td>MinimumExcessPower</td><td>0</td><td>Integer</td><td>Minimum excess power the AI should try to maintain. </td></tr>
<tr><td>MaximumExcessPower</td><td>0</td><td>Integer</td><td>The targeted excess power the AI tries to maintain cannot rise above this. </td></tr>
<tr><td>ExcessPowerIncrement</td><td>0</td><td>Integer</td><td>Increase maintained excess power by this amount for every ExcessPowerIncreaseThreshold of base buildings. </td></tr>
<tr><td>ExcessPowerIncreaseThreshold</td><td>1</td><td>Integer</td><td>Increase maintained excess power by ExcessPowerIncrement for every N base buildings. </td></tr>
<tr><td>MinimumRefineryCount</td><td>1</td><td>Integer</td><td>Number of refineries to build before building a barracks. </td></tr>
<tr><td>ResourceDistance</td><td>5</td><td>Integer</td><td>Minimum distance in cells for resource patches when checking for building placement. </td></tr>
<tr><td>StructureProductionInactiveDelay</td><td>125</td><td>Integer</td><td>Additional delay (in ticks) between structure production checks when there is no active production. StructureProductionRandomBonusDelay is added to this. </td></tr>
<tr><td>StructureProductionActiveDelay</td><td>0</td><td>Integer</td><td>Additional delay (in ticks) added between structure production checks when actively building things. Note: The total delay is gamespeed OrderLatency x 4 + this + StructureProductionRandomBonusDelay. </td></tr>
<tr><td>StructureProductionRandomBonusDelay</td><td>10</td><td>Integer</td><td>A random delay (in ticks) of up to this is added to active/inactive production delays. </td></tr>
<tr><td>StructureProductionResumeDelay</td><td>1500</td><td>Integer</td><td>Delay (in ticks) until retrying to build structure after the last 3 consecutive attempts failed. </td></tr>
<tr><td>MaximumFailedPlacementAttempts</td><td>3</td><td>Integer</td><td>After how many failed attempts to place a structure should AI give up and wait for StructureProductionResumeDelay before retrying. </td></tr>
<tr><td>CheckForNewBasesDelay</td><td>1500</td><td>Integer</td><td>Delay (in ticks) until rechecking for new BaseProviders. </td></tr>
<tr><td>PlaceDefenseTowardsEnemyChance</td><td>100</td><td>Integer</td><td>Chance that the AI will place the defenses in the direction of the closest enemy building. </td></tr>
<tr><td>MinimumDefenseRadius</td><td>5</td><td>Integer</td><td>Minimum range at which to build defensive structures near a combat hotspot. </td></tr>
<tr><td>MaximumDefenseRadius</td><td>20</td><td>Integer</td><td>Maximum range at which to build defensive structures near a combat hotspot. </td></tr>
<tr><td>NewProductionCashThreshold</td><td>5000</td><td>Integer</td><td>Try to build another production building if there is too much cash. </td></tr>
<tr><td>RallyPointScanRadius</td><td>8</td><td>Integer</td><td>Radius in cells around a factory scanned for rally points by the AI. </td></tr>
<tr><td>CheckForWaterRadius</td><td>8</td><td>Integer</td><td>Radius in cells around each building with ProvideBuildableArea to check for a 3x3 area of water where naval structures can be built. Should match maximum adjacency of naval structures. </td></tr>
<tr><td>WaterTerrainTypes</td><td>Water</td><td>Set of System.String[]</td><td>Terrain types which are considered water for base building purposes. </td></tr>
<tr><td>BuildingFractions</td><td></td><td>Dictionary with Key: String, Value Integer</td><td>What buildings to the AI should build. What integer percentage of the total base must be this type of building. </td></tr>
<tr><td>BuildingLimits</td><td></td><td>Dictionary with Key: String, Value Integer</td><td>What buildings should the AI have a maximum limit to build. </td></tr>
<tr><td>BuildingDelays</td><td></td><td>Dictionary with Key: String, Value Integer</td><td>When should the AI start building specific buildings. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### DeployDetectorBotModule
Manages AI cloak detector deployment logic. For use with the regular `SquadManagerBotModule`.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>DeployableActorTypes</td><td><em>(required)</em></td><td>Set of System.String[]</td><td>Actor types that can deploy. </td></tr>
<tr><td>MinimumScanDelay</td><td>20</td><td>Integer</td><td>Minimum delay (in ticks) between trying to deploy with DeployableActorTypes. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### MinerBotModule
Manages AI miner deployment logic.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>DeployableActorTypes</td><td><em>(required)</em></td><td>Set of System.String[]</td><td>Actor types that can deploy onto resources. </td></tr>
<tr><td>VehiclesQueue</td><td>Vehicle</td><td>String</td><td>Where to request production of additional deployable actors. </td></tr>
<tr><td>DeployableTerrainTypes</td><td><em>(required)</em></td><td>Set of System.String[]</td><td>Terrain types that can be targeted for deployment. </td></tr>
<tr><td>DeployedActorTypes</td><td><em>(required)</em></td><td>Set of System.String[]</td><td>Actor types that have been deployed onto resources. </td></tr>
<tr><td>MinimumDeployedActors</td><td>1</td><td>Integer</td><td>Prioritize this many resource towers before building other units. </td></tr>
<tr><td>MinimumScanDelay</td><td>20</td><td>Integer</td><td>Minimum delay (in ticks) between trying to deploy with DeployableActorTypes. </td></tr>
<tr><td>LastSearchFailedDelay</td><td>500</td><td>Integer</td><td>Minimum delay (in ticks) after the last search for resources failed. </td></tr>
<tr><td>EnemyAvoidanceRadius</td><td>8c0</td><td>1D World Distance</td><td>Avoid enemy actors nearby when searching for a new resource patch. Should be somewhere near the max weapon range. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### PowerDownBotModule
Manages AI powerdown.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Interval</td><td>150</td><td>Integer</td><td>Delay (in ticks) between toggling powerdown. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### PriorityCaptureManagerBotModule
Manages AI capturing logic.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>CapturingActorTypes</td><td><em>(required)</em></td><td>Set of System.String[]</td><td>Actor types that can capture other actors (via `Captures`). </td></tr>
<tr><td>PriorityCaptureChance</td><td>75</td><td>Integer</td><td>Percentage chance of trying a priority capture. </td></tr>
<tr><td>PriorityCapturableActorTypes</td><td></td><td>Set of System.String[]</td><td>Actor types that should be priorizited to be captured. Leave this empty to include all actors. </td></tr>
<tr><td>CapturableActorTypes</td><td></td><td>Set of System.String[]</td><td>Actor types that can be targeted for capturing. Leave this empty to include all actors. </td></tr>
<tr><td>EnemyAvoidanceRadius</td><td>8c0</td><td>1D World Distance</td><td>Avoid enemy actors nearby when searching for capture opportunities. Should be somewhere near the max weapon range. </td></tr>
<tr><td>MinimumCaptureDelay</td><td>375</td><td>Integer</td><td>Minimum delay (in ticks) between trying to capture with CapturingActorTypes. </td></tr>
<tr><td>MaximumCaptureTargetOptions</td><td>10</td><td>Integer</td><td>Maximum number of options to consider for capturing. If a value less than 1 is given 1 will be used instead. </td></tr>
<tr><td>CheckCaptureTargetsForVisibility</td><td>True</td><td>Boolean</td><td>Should visibility (Shroud, Fog, Cloak, etc) be considered when searching for capturable targets? </td></tr>
<tr><td>CapturableStances</td><td>Enemy, Neutral</td><td>PlayerRelationship</td><td>Player stances that capturers should attempt to target. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ScoutBotModule
Manages AI random scouting. Exclude from `SquadManagerBotModule`.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ScoutActorTypes</td><td><em>(required)</em></td><td>Set of System.String[]</td><td>Actor types that are sent around the map. </td></tr>
<tr><td>MinimumScanDelay</td><td>200</td><td>Integer</td><td>Minimum delay (in ticks) between searching for ScoutActorTypes. </td></tr>
<tr><td>MoveRadius</td><td>1</td><td>Integer</td><td>How far away to move from current location. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### BotRepairOrSellCaptures
Helper trait to set up AI to sell heavily damaged newly controlled actors and repairing them otherwise.

### CollectScrapCrateAction
Gives cash to the collector.

Requires trait: [`ScrapValue`](#scrapvalue).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>UseCashTick</td><td>True</td><td>Boolean</td><td>Should the collected amount be displayed as a cash tick? </td></tr>
<tr><td>SelectionShares</td><td>10</td><td>Integer</td><td>Chance of getting this crate, assuming the collector is compatible. </td></tr>
<tr><td>Image</td><td>crate-effects</td><td>String</td><td>Image containing the crate effect animation sequence. </td></tr>
<tr><td>Sequence</td><td></td><td>String</td><td>Animation sequence played when collected. Leave empty for no effect. </td></tr>
<tr><td>Palette</td><td>effect</td><td>String</td><td>Palette to draw the animation in. </td></tr>
<tr><td>Sound</td><td></td><td>String</td><td>Audio clip to play when the crate is collected. </td></tr>
<tr><td>Notification</td><td></td><td>String</td><td>Notification to play when the crate is collected. </td></tr>
<tr><td>TimeDelay</td><td>0</td><td>Integer</td><td>The earliest time (in ticks) that this crate action can occur on. </td></tr>
<tr><td>Prerequisites</td><td></td><td>Collection of String</td><td>Only allow this crate action when the collector has these prerequisites </td></tr>
<tr><td>ExcludedActorTypes</td><td></td><td>Collection of String</td><td>Actor types that this crate action will not occur for. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### GrantConditionOnBurstComplete
Grants a condition when this actor finishes a burst.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td>The condition to grant. </td></tr>
<tr><td>ArmamentNames</td><td>primary</td><td>Set of System.String[]</td><td>Name of the armaments that grant this condition. </td></tr>
<tr><td>RevokeDelay</td><td><em>(required)</em></td><td>Integer</td><td></td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### GrantConditionOnNeutralOwner
Grants a condition if the owner is the Neutral player.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td></td><td>String</td><td>The condition to grant. </td></tr>
</table>

### GrantExternalConditionToOwner
Grants an external condition to the owner player's actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td><em>(required)</em></td><td>String</td><td></td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### DebugOffsetOverlay
Displays a developer offset point, controllable via chat commands.
Select the unit first.
Rendering is enabled automatically with the first valid command.
Available commands:
`/offset body`: Sets the reference point to the actor's center position.
`/offset turret X`: where X is the turret index whose center the reference point should be set. Falls back to actor center position on wrong index.
`/offset set X,Y,Z`: Sets the offset. No spaces are supported between the values.
`/offset add X,Y,Z`: Adds the value to the current offset. Negative values function to subtract. No spaces are supported between the values.
`/offset query`: Returns the current offset value in the chat.
`/offset disable`: Disables rendering of the offset.

### Floods
Lets the actor spread resources around it in straight lines.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Interval</td><td>75</td><td>Integer</td><td></td></tr>
<tr><td>ResourceType</td><td>water</td><td>String</td><td></td></tr>
<tr><td>MaxRange</td><td>100</td><td>Integer</td><td></td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### FreeActorWithEffect
Player receives a unit for free once the building is placed with a sprite effect.
If you want more than one unit to be spawned, copy this section and assign IDs like FreeActorWithDelay@2, ...
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Image</td><td></td><td>String</td><td></td></tr>
<tr><td>Sequence</td><td></td><td>String</td><td>Sequence to use for overlay animation. </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name </td></tr>
<tr><td>Actor</td><td><em>(required)</em></td><td>String</td><td>Name of the actor. </td></tr>
<tr><td>SpawnOffset</td><td>0,0</td><td>2D Cell Vector</td><td>Offset relative to the top-left cell of the building. </td></tr>
<tr><td>Facing</td><td>0</td><td>1D World Angle</td><td>Which direction the unit should face. </td></tr>
<tr><td>AllowRespawn</td><td>False</td><td>Boolean</td><td>Whether another actor should spawn upon re-enabling the trait. </td></tr>
<tr><td>EditorFreeActorDisplayOrder</td><td>4</td><td>Integer</td><td>Display order for the free actor checkbox in the map editor </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### LaysTerrain
Requires trait: [`Building`](#building).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Template</td><td>0</td><td>UInt16</td><td>The terrain template to place. If the template is PickAny, then the actor footprint will be filled with this tile. </td></tr>
<tr><td>TerrainTypes</td><td></td><td>Set of System.String[]</td><td>The terrain types that this template will be placed on. </td></tr>
<tr><td>Offset</td><td>0,0</td><td>2D Cell Vector</td><td>Offset relative to the actor TopLeft. Not used if the template is PickAny. Tiles being offset out of the actor's footprint will not be placed. </td></tr>
</table>

### Mine
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>CrushClasses</td><td></td><td>Collection of CrushClass</td><td></td></tr>
<tr><td>AvoidFriendly</td><td>True</td><td>Boolean</td><td></td></tr>
<tr><td>BlockFriendly</td><td>True</td><td>Boolean</td><td></td></tr>
<tr><td>DetonateClasses</td><td></td><td>Collection of CrushClass</td><td></td></tr>
</table>

### MineImmune
Tag trait for stuff that should not trigger mines.

### Minelayer
Requires trait: [`Rearmable`](#rearmable).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Mines</td><td><em>(required)</em></td><td>Collection of String</td><td></td></tr>
<tr><td>AmmoPoolName</td><td>primary</td><td>String</td><td></td></tr>
<tr><td>MinefieldDepth</td><td>1c512</td><td>1D World Distance</td><td></td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td>Voice to use when ordered to lay a minefield. </td></tr>
<tr><td>TileImage</td><td>overlay</td><td>String</td><td>Sprite image used for overlays. </td></tr>
<tr><td>TileValidName</td><td>target-valid</td><td>String</td><td>Sprite overlay to use for valid minefield cells. </td></tr>
<tr><td>TileInvalidName</td><td>target-invalid</td><td>String</td><td>Sprite overlay to use for invalid minefield cells. </td></tr>
<tr><td>TileUnknownName</td><td>target-unknown</td><td>String</td><td>Sprite overlay to use for minefield cells hidden behind fog or shroud. </td></tr>
<tr><td>Cursor</td><td>ability</td><td>String</td><td>Cursor to display when able to (un)deploy the actor. </td></tr>
<tr><td>TargetLineColor</td><td>DC143C</td><td>Color (RRGGBB[AA] notation)</td><td>Color to use for the target line when laying mines. </td></tr>
<tr><td>TerrainTypes</td><td></td><td>Set of System.String[]</td><td>Only allow laying mines on listed terrain types. Leave empty to allow all terrain types. </td></tr>
<tr><td>DeployCursor</td><td>deploy</td><td>String</td><td>Cursor to display when able to lay a mine. </td></tr>
<tr><td>DeployBlockedCursor</td><td>deploy-blocked</td><td>String</td><td>Cursor to display when unable to lay a mine. </td></tr>
</table>

### Miner
Allows the miner to deploy at a target location with a single order.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>DeployCursor</td><td>deploy</td><td>String</td><td>Cursor to display when able to lay a mine. </td></tr>
<tr><td>TerrainTypes</td><td><em>(required)</em></td><td>Set of System.String[]</td><td>Terrain types that can be targeted for deployment. </td></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td>Voice to use when ordered to lay a minefield. </td></tr>
</table>

### PeriodicDischarge
Dispenses a weapon at the actor's position when enabled.Reload/BurstDelays are used as release intervals.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Weapon</td><td><em>(required)</em></td><td>String</td><td>Has to be defined in weapons.yaml as well. </td></tr>
<tr><td>ResetReloadWhenEnabled</td><td>True</td><td>Boolean</td><td></td></tr>
<tr><td>AmmoPoolName</td><td></td><td>String</td><td>Which limited ammo pool (if present) should this weapon be assigned to. </td></tr>
<tr><td>LocalOffset</td><td>0,0,0</td><td>3D World Vector</td><td>Explosion offset relative to actor's position. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### TeleportNetworkManager
This must be attached to player in order for TeleportNetwork to work.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Type</td><td><em>(required)</em></td><td>String</td><td>Type of TeleportNetwork that pairs up, in order for it to work. </td></tr>
</table>

### ProductionSound
Requires trait: [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Files</td><td><em>(required)</em></td><td>Collection of String</td><td></td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### RailgunPower
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>CameraRange</td><td>0c0</td><td>1D World Distance</td><td>Range of cells the camera should reveal around target cell. </td></tr>
<tr><td>RevealGeneratedShroud</td><td>True</td><td>Boolean</td><td>Can the camera reveal shroud generated by the GeneratesShroud trait? </td></tr>
<tr><td>CameraRelationships</td><td>Ally</td><td>PlayerRelationship</td><td>Reveal cells to players with these relationships only. </td></tr>
<tr><td>CameraSpawnAdvance</td><td>25</td><td>Integer</td><td>Amount of time before detonation to spawn the camera. </td></tr>
<tr><td>CameraRemoveDelay</td><td>25</td><td>Integer</td><td>Amount of time after detonation to remove the camera. </td></tr>
<tr><td>Effect</td><td>railgun</td><td>String</td><td>Effect sequence sprite image </td></tr>
<tr><td>EffectSequence</td><td>idle</td><td>String</td><td>Effect sequence to display </td></tr>
<tr><td>EffectPalette</td><td>effect</td><td>String</td><td></td></tr>
<tr><td>Weapon</td><td>RailgunStrike</td><td>String</td><td>Which weapon to fire </td></tr>
<tr><td>WeaponDelay</td><td>7</td><td>Integer</td><td>Apply the weapon impact this many ticks into the effect </td></tr>
<tr><td>ChargeInterval</td><td>0</td><td>Integer</td><td>Measured in ticks. </td></tr>
<tr><td>IconImage</td><td>icon</td><td>String</td><td></td></tr>
<tr><td>Icon</td><td></td><td>String</td><td>Icon sprite displayed in the support power palette. </td></tr>
<tr><td>IconPalette</td><td>chrome</td><td>String</td><td>Palette used for the icon. </td></tr>
<tr><td>Description</td><td></td><td>String</td><td></td></tr>
<tr><td>LongDesc</td><td></td><td>String</td><td></td></tr>
<tr><td>AllowMultiple</td><td>False</td><td>Boolean</td><td>Allow multiple instances of the same support power. </td></tr>
<tr><td>OneShot</td><td>False</td><td>Boolean</td><td>Allow this to be used only once. </td></tr>
<tr><td>Cursor</td><td>ability</td><td>String</td><td>Cursor to display for using this support power. </td></tr>
<tr><td>StartFullyCharged</td><td>False</td><td>Boolean</td><td>If set to true, the support power will be fully charged when it becomes available. Normal rules apply for subsequent charges. </td></tr>
<tr><td>Prerequisites</td><td></td><td>Collection of String</td><td></td></tr>
<tr><td>BeginChargeSound</td><td></td><td>String</td><td></td></tr>
<tr><td>BeginChargeSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>EndChargeSound</td><td></td><td>String</td><td></td></tr>
<tr><td>EndChargeSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>SelectTargetSound</td><td></td><td>String</td><td></td></tr>
<tr><td>SelectTargetSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>InsufficientPowerSound</td><td></td><td>String</td><td></td></tr>
<tr><td>InsufficientPowerSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>LaunchSound</td><td></td><td>String</td><td></td></tr>
<tr><td>LaunchSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>IncomingSound</td><td></td><td>String</td><td></td></tr>
<tr><td>IncomingSpeechNotification</td><td></td><td>String</td><td></td></tr>
<tr><td>DisplayTimerRelationships</td><td>None</td><td>PlayerRelationship</td><td>Defines to which players the timer is shown. </td></tr>
<tr><td>DisplayBeacon</td><td>False</td><td>Boolean</td><td>Beacons are only supported on the Airstrike, Paratroopers, and Nuke powers </td></tr>
<tr><td>BeaconPaletteIsPlayerPalette</td><td>True</td><td>Boolean</td><td></td></tr>
<tr><td>BeaconPalette</td><td>player</td><td>String</td><td></td></tr>
<tr><td>BeaconImage</td><td>beacon</td><td>String</td><td></td></tr>
<tr><td>BeaconPoster</td><td></td><td>String</td><td></td></tr>
<tr><td>BeaconPosterPalette</td><td>chrome</td><td>String</td><td></td></tr>
<tr><td>ClockSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>BeaconSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>ArrowSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>CircleSequence</td><td></td><td>String</td><td></td></tr>
<tr><td>BeaconDelay</td><td>0</td><td>Integer</td><td>Delay after launch, measured in ticks. </td></tr>
<tr><td>DisplayRadarPing</td><td>False</td><td>Boolean</td><td></td></tr>
<tr><td>RadarPingDuration</td><td>125</td><td>Integer</td><td>Measured in ticks. </td></tr>
<tr><td>OrderName</td><td>RailgunPowerInfoOrder</td><td>String</td><td></td></tr>
<tr><td>SupportPowerPaletteOrder</td><td>9999</td><td>Integer</td><td>Sort order for the support power palette. Smaller numbers are presented earlier. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ResourceDensityOverlay
Displays resource density colored by type.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Font</td><td>TinyBold</td><td>String</td><td></td></tr>
</table>

### TerrainDebugOverlay
Displays terrain tile IDs colored by terrain type.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Font</td><td>TinyBold</td><td>String</td><td></td></tr>
</table>

### ResourceCollector
Lets the actor generate resources in a set periodic time.

Requires trait: [`Building`](#building).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Interval</td><td>50</td><td>Integer</td><td>Number of ticks to wait between gathering resources. </td></tr>
<tr><td>InitialDelay</td><td>200</td><td>Integer</td><td>Number of ticks to wait before gathering first resources. </td></tr>
<tr><td>Amount</td><td>100</td><td>Integer</td><td>Amount of resource to collect each time. </td></tr>
<tr><td>Capacity</td><td>1000</td><td>Integer</td><td>How much can be temporarily stored. </td></tr>
<tr><td>DeliveryVehicleType</td><td></td><td>Collection of String</td><td></td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### ResourceTransporter
Requires trait: [`Mobile`](#mobile).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>DeliveryBuildings</td><td></td><td>Set of System.String[]</td><td></td></tr>
<tr><td>Capacity</td><td>10</td><td>Integer</td><td>How much resources it can carry. </td></tr>
<tr><td>DeliverVoice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>EnterCursor</td><td>enter</td><td>String</td><td>Cursor to display when able to unload at target actor. </td></tr>
<tr><td>EnterBlockedCursor</td><td>enter-blocked</td><td>String</td><td>Cursor to display when unable to unload at target actor. </td></tr>
<tr><td>EnemyAvoidanceRadius</td><td>8c0</td><td>1D World Distance</td><td>Avoid enemy actors nearby when searching for a new delivery route. Should be somewhere near the max weapon range. </td></tr>
<tr><td>IdleScanDelay</td><td>20</td><td>Integer</td><td>Minimum delay (in ticks) between searching for destinations. </td></tr>
</table>

### ScrapOptions
Controls the 'Scrap' checkbox in the lobby options.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>CheckboxLabel</td><td>Scrap</td><td>String</td><td>Descriptive label for the scrap checkbox in the lobby. </td></tr>
<tr><td>CheckboxDescription</td><td>Collectible junk after unit destruction</td><td>String</td><td>Tooltip description for the scrap checkbox in the lobby. </td></tr>
<tr><td>CheckboxEnabled</td><td>True</td><td>Boolean</td><td>Default value of the scrap checkbox in the lobby. </td></tr>
<tr><td>CheckboxLocked</td><td>False</td><td>Boolean</td><td>Prevent the scrap state from being changed in the lobby. </td></tr>
<tr><td>CheckboxVisible</td><td>True</td><td>Boolean</td><td>Whether to display the scrap checkbox in the lobby. </td></tr>
<tr><td>CheckboxDisplayOrder</td><td>0</td><td>Integer</td><td>Display order for the scrap checkbox in the lobby. </td></tr>
</table>

### ScrapValue
How much the unit leftovers are worth.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Percentage</td><td>10</td><td>Integer</td><td>Percentage of the killed actor's value. </td></tr>
</table>

### SpawnScrapOnDeath
Spawn an actor of the same value immediately upon death when the 'Scrap' trait is enabled.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Actors</td><td><em>(required)</em></td><td>Collection of String</td><td>Random actor to spawn on death. </td></tr>
<tr><td>Probability</td><td>100</td><td>Integer</td><td>Probability the actor spawns. </td></tr>
<tr><td>InternalOwner</td><td>Neutral</td><td>String</td><td>Map player to use when 'InternalName' is defined on 'OwnerType'. </td></tr>
<tr><td>DeathType</td><td></td><td>String</td><td>DeathType that triggers the actor spawn. Leave empty to spawn an actor ignoring the DeathTypes. </td></tr>
<tr><td>Offset</td><td>0,0</td><td>2D Cell Vector</td><td>Offset of the spawned actor relative to the dying actor's position. Warning: Spawning an actor outside the parent actor's footprint/influence might lead to unexpected behaviour. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### SpawnsShrapnel
Spawns shrapnel weapons after a periodic interval.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Weapon</td><td><em>(required)</em></td><td>String</td><td>Has to be defined in weapons.yaml as well. </td></tr>
<tr><td>Amount</td><td>1</td><td>Collection of Integer</td><td>Amount of shrapnels thrown. Two values indicate a range. </td></tr>
<tr><td>Delay</td><td>50</td><td>Collection of Integer</td><td>Delay between two spawns. Two values indicate a range. </td></tr>
<tr><td>AimChance</td><td>0</td><td>Integer</td><td>The percentage of aiming this shrapnel to a suitable target actor. </td></tr>
<tr><td>AimTargetStances</td><td>Enemy, Neutral, Ally</td><td>PlayerRelationship</td><td>What diplomatic stances can be targeted by the shrapnel. </td></tr>
<tr><td>ThrowWithoutTarget</td><td>True</td><td>Boolean</td><td>Allow this shrapnel to be thrown randomly when no targets found. </td></tr>
<tr><td>AllowSelfHit</td><td>False</td><td>Boolean</td><td>Should the shrapnel hit the spawner actor? </td></tr>
<tr><td>LocalOffset</td><td>0,0,0</td><td>3D World Vector</td><td>Shrapnel spawn offset relative to actor's position. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### TeleportNetwork
This actor can teleport actors to another actor with the same trait.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Type</td><td><em>(required)</em></td><td>String</td><td>Type of TeleportNetwork that pairs up, in order for it to work. </td></tr>
<tr><td>ValidStances</td><td>Ally</td><td>PlayerRelationship</td><td>Stances requirement that targeted TeleportNetwork has to meet in order to teleport units. </td></tr>
<tr><td>Delay</td><td>20</td><td>Integer</td><td>Time in ticks to wait for the teleporter to charge up. </td></tr>
</table>

### TeleportNetworkPrimaryExit
Used with TeleportNetwork trait for primary exit designation.

Requires trait: [`TeleportNetwork`](#teleportnetwork).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>PrimaryCondition</td><td>primary</td><td>String</td><td>The condition to grant to self while this is the primary building. </td></tr>
<tr><td>SelectionNotification</td><td></td><td>String</td><td>The speech notification to play when selecting a primary exit. </td></tr>
<tr><td>Cursor</td><td>deploy</td><td>String</td><td>Cursor to display when setting the primary building. </td></tr>
</table>

### TeleportNetworkTransportable
Can move actors instantly to primary designated teleport network canal actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Voice</td><td>Action</td><td>String</td><td></td></tr>
<tr><td>EnterCursor</td><td>enter</td><td>String</td><td></td></tr>
<tr><td>EnterBlockedCursor</td><td>enter-blocked</td><td>String</td><td></td></tr>
</table>

### Tree
For use with the ForestLayer.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Template</td><td><em>(required)</em></td><td>UInt16</td><td>Terrain tile to match. </td></tr>
</table>

### CloudSpawner
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>SpawnInterval</td><td>250</td><td>Integer</td><td>Average time (ticks) between cloud spawn. </td></tr>
<tr><td>InitialSpawnDelay</td><td>0</td><td>Integer</td><td>Delay (in ticks) before the first cloud spawns. </td></tr>
<tr><td>Image</td><td><em>(required)</em></td><td>String</td><td>Which image to use. </td></tr>
<tr><td>Sequences</td><td><em>(required)</em></td><td>Collection of String</td><td>Which sequence to use. </td></tr>
<tr><td>Palette</td><td><em>(required)</em></td><td>String</td><td>Which palette to use. </td></tr>
<tr><td>WindDirection</td><td>8</td><td>Integer</td><td>Facing that the cloud may approach from. </td></tr>
<tr><td>Cordon</td><td>7c512</td><td>1D World Distance</td><td>Spawn and remove the cloud this far outside the map. </td></tr>
<tr><td>Speed</td><td><em>(required)</em></td><td>Collection of 1D World Distance</td><td>Cloud forward movement. Two values mean the cloud speed randomizes between them. </td></tr>
<tr><td>CruiseAltitude</td><td>2c512</td><td>1D World Distance</td><td>The altitude of the cloud. </td></tr>
<tr><td>CloseEnough</td><td>0c128</td><td>1D World Distance</td><td>Distance margin where the cloud can be removed. </td></tr>
<tr><td>ShouldPrespawn</td><td>True</td><td>Boolean</td><td>Should we pre-spawn clouds covers the map? </td></tr>
</table>

### CubeSpawner
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>CheckboxLabel</td><td>Cubes</td><td>String</td><td>Descriptive label for the cubes checkbox in the lobby. </td></tr>
<tr><td>CheckboxDescription</td><td>Collect cubes with units to receive random bonuses</td><td>String</td><td>Tooltip description for the cubes checkbox in the lobby. </td></tr>
<tr><td>CheckboxEnabled</td><td>False</td><td>Boolean</td><td>Default value of the cubes checkbox in the lobby. </td></tr>
<tr><td>CheckboxLocked</td><td>False</td><td>Boolean</td><td>Prevent the cubes state from being changed in the lobby. </td></tr>
<tr><td>CheckboxVisible</td><td>True</td><td>Boolean</td><td>Whether to display the cubes checkbox in the lobby. </td></tr>
<tr><td>CheckboxDisplayOrder</td><td>0</td><td>Integer</td><td>Display order for the cubes checkbox in the lobby. </td></tr>
<tr><td>Minimum</td><td>1</td><td>Integer</td><td>Minimum number of cubes. </td></tr>
<tr><td>Maximum</td><td>255</td><td>Integer</td><td>Maximum number of cubes. </td></tr>
<tr><td>SpawnInterval</td><td>4500</td><td>Integer</td><td>Average time (ticks) between cube spawn. </td></tr>
<tr><td>InitialSpawnDelay</td><td>0</td><td>Integer</td><td>Delay (in ticks) before the first cube spawns. </td></tr>
<tr><td>ValidGround</td><td>Clear</td><td>Set of System.String[]</td><td>Which terrain types can we drop on? </td></tr>
<tr><td>CubeActors</td><td>cube</td><td>Collection of String</td><td>Cube actors to drop. </td></tr>
<tr><td>CubeActorShares</td><td>10</td><td>Collection of Integer</td><td>Chance of each cube actor spawning. </td></tr>
</table>

### CustomTerrainLayer
Attach this to the world actor. Required for LaysTerrain to work.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Palette</td><td>terrain</td><td>String</td><td>Palette to render the layer sprites in. </td></tr>
</table>

### DebugOffsetOverlayManager

### EditorAutoTiler

### ForestLayer
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Trees</td><td><em>(required)</em></td><td>Collection of String</td><td></td></tr>
</table>

### LiquidTerrainRenderer
Used to render liquids.
Attach this to the world actor
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ResourceTypes</td><td></td><td>Dictionary with Key: String, Value ResourceTypeInfo</td><td></td></tr>
</table>

### TerrainTileAnimation
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Tiles</td><td><em>(required)</em></td><td>Collection of UInt16</td><td></td></tr>
<tr><td>Interval</td><td>175, 325</td><td>Collection of Integer</td><td>Average time (ticks) between animations. </td></tr>
<tr><td>InitialDelay</td><td>0</td><td>Integer</td><td>Delay (in ticks) before the first animation happens. </td></tr>
<tr><td>Image</td><td><em>(required)</em></td><td>String</td><td>Which image to use. </td></tr>
<tr><td>Sequence</td><td><em>(required)</em></td><td>String</td><td>Which sequence to use. </td></tr>
<tr><td>Palette</td><td><em>(required)</em></td><td>String</td><td>Which palette to use. </td></tr>
</table>

### UndergroundResourceLayer
Allows resources below actors. Attach this to the world actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ResourceTypes</td><td></td><td>Dictionary with Key: String, Value ResourceTypeInfo</td><td></td></tr>
</table>


### WithConstructionBeamOverlay
Rendered after the "make" animation.

Requires trait: [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Condition</td><td></td><td>String</td><td>The condition to grant to self while the overlay is playing. </td></tr>
<tr><td>Sequence</td><td>make-overlay</td><td>String</td><td>Sequence name to use </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Custom palette is a player palette BaseName </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithConstructionOverlay
Rendered together with the "make" animation.

Requires traits: [`BodyOrientation`](#bodyorientation), [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Sequence</td><td>make-overlay</td><td>String</td><td>Sequence name to use </td></tr>
<tr><td>Offset</td><td>0,0,0</td><td>3D World Vector</td><td>Position relative to body </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithDamagedOverlay
Renders an overlay when the actor is taking heavy damage.

Requires trait: [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Image</td><td></td><td>String</td><td>Defaults to the actor name. </td></tr>
<tr><td>Sequence</td><td></td><td>String</td><td></td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name. </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Custom palette is a player palette BaseName. </td></tr>
<tr><td>DamageTypes</td><td></td><td>Collection of DamageType</td><td>Damage types that this should be used for (defined on the warheads). Leave empty to disable all filtering. </td></tr>
<tr><td>MinimumDamageState</td><td>Heavy</td><td>DamageState</td><td>Trigger when Undamaged, Light, Medium, Heavy, Critical or Dead. </td></tr>
<tr><td>MaximumDamageState</td><td>Dead</td><td>DamageState</td><td></td></tr>
</table>

### WithIdleOverlayOnGround
Plays an idle overlay on the ground position under the actor (regardless of it's actual height).

Requires traits: [`BodyOrientation`](#bodyorientation), [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Image</td><td></td><td>String</td><td>Image used for this decoration. Defaults to the actor's type. </td></tr>
<tr><td>StartSequence</td><td></td><td>String</td><td>Animation to play when the actor is created. </td></tr>
<tr><td>Sequence</td><td>idle-overlay</td><td>String</td><td>Sequence name to use </td></tr>
<tr><td>Offset</td><td>0,0,0</td><td>3D World Vector</td><td>Position relative to body </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Custom palette is a player palette BaseName </td></tr>
<tr><td>IsDecoration</td><td>False</td><td>Boolean</td><td></td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithLandingAnimation
Requires trait: [`WithSpriteBody`](#withspritebody).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>RequiredFacing</td><td>0</td><td>1D World Angle</td><td></td></tr>
<tr><td>LandingSequence</td><td>landing</td><td>String</td><td></td></tr>
<tr><td>TouchdownSequence</td><td>touchdown</td><td>String</td><td></td></tr>
<tr><td>LiftoffSequence</td><td>liftoff</td><td>String</td><td></td></tr>
<tr><td>Body</td><td>body</td><td>String</td><td>Which sprite body to play the animation on. </td></tr>
</table>

### WithProductionDoorAnimation
Play an animation when a unit exits after production finished.

Requires trait: [`WithSpriteBody`](#withspritebody).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ExitCells</td><td><em>(required)</em></td><td>Collection of 2D Cell Vector</td><td>Exit offset associated with the animation. </td></tr>
<tr><td>Sequence</td><td>door</td><td>String</td><td></td></tr>
<tr><td>Body</td><td>body</td><td>String</td><td>Which sprite body to play the animation on. </td></tr>
<tr><td>ReplayBackwards</td><td>False</td><td>Boolean</td><td>Replay the animation backwards after it was played once? </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithProductionExitOverlay
Rendered when an actor finishes production on the used exit cell.

Requires trait: [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ExitCell</td><td><em>(required)</em></td><td>2D Cell Vector</td><td>Exit offset associated with the animation. </td></tr>
<tr><td>Sequence</td><td><em>(required)</em></td><td>String</td><td>Sequence name to use. </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name. </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Custom palette is a player palette BaseName. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithRandomFacingSpriteBody
Picks sprites from a random actor.

Requires traits: [`BodyOrientation`](#bodyorientation), [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Images</td><td><em>(required)</em></td><td>Collection of String</td><td>The sequence names that define the actor sprites. </td></tr>
<tr><td>StartSequence</td><td></td><td>String</td><td>Animation to play when the actor is created. </td></tr>
<tr><td>Sequence</td><td>idle</td><td>String</td><td>Animation to play when the actor is idle. </td></tr>
<tr><td>Name</td><td>body</td><td>String</td><td>Identifier used to assign modifying traits to this sprite body. </td></tr>
<tr><td>ForceToGround</td><td>False</td><td>Boolean</td><td>Forces sprite body to be rendered on ground regardless of actor altitude (for example for custom shadow sprites). </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name. </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Palette is a player palette BaseName. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithResourceCollectorOverlay
Renders the fillness state.

Requires traits: [`RenderSprites`](#rendersprites), [`ResourceCollector`](#resourcecollector).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Sequence</td><td>silo</td><td>String</td><td>Sequence name to use </td></tr>
<tr><td>Offset</td><td>0,0,0</td><td>3D World Vector</td><td>Position relative to body </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Custom palette is a player palette BaseName </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithSeaMonsterBody
Emerge from water animation.

Requires traits: [`BodyOrientation`](#bodyorientation), [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>LeftSequence</td><td>left</td><td>String</td><td></td></tr>
<tr><td>RightSequence</td><td>right</td><td>String</td><td></td></tr>
<tr><td>EditorSequence</td><td>left</td><td>String</td><td>Placeholder sequence to use in the map editor. </td></tr>
<tr><td>EmergeDuration</td><td>0</td><td>Integer</td><td></td></tr>
<tr><td>StartSequence</td><td></td><td>String</td><td>Animation to play when the actor is created. </td></tr>
<tr><td>Sequence</td><td>idle</td><td>String</td><td>Animation to play when the actor is idle. </td></tr>
<tr><td>Name</td><td>body</td><td>String</td><td>Identifier used to assign modifying traits to this sprite body. </td></tr>
<tr><td>ForceToGround</td><td>False</td><td>Boolean</td><td>Forces sprite body to be rendered on ground regardless of actor altitude (for example for custom shadow sprites). </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name. </td></tr>
<tr><td>IsPlayerPalette</td><td>False</td><td>Boolean</td><td>Palette is a player palette BaseName. </td></tr>
<tr><td>PauseOnCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to pause this trait. </td></tr>
<tr><td>RequiresCondition</td><td></td><td>BooleanExpression</td><td>Boolean expression defining the condition to enable this trait. </td></tr>
</table>

### WithTeleportChargeAnimation
This actor displays a charge-up animation when it receives a teleported unit.

Requires traits: [`RenderSprites`](#rendersprites), [`WithSpriteBody`](#withspritebody).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>ChargeSequence</td><td>active</td><td>String</td><td>Sequence to use for charge animation. </td></tr>
<tr><td>Body</td><td>body</td><td>String</td><td>Which sprite body to play the animation on. </td></tr>
</table>

### WithTeleportEnergyOverlay
This actor display an overlay upon arrival.

Requires traits: [`BodyOrientation`](#bodyorientation), [`RenderSprites`](#rendersprites).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Image</td><td></td><td>String</td><td>Defaults to the actor name. </td></tr>
<tr><td>Sequence</td><td></td><td>String</td><td>Sequence to use for charge animation. </td></tr>
<tr><td>Body</td><td>body</td><td>String</td><td>Which sprite body to play the animation on. </td></tr>
<tr><td>Offset</td><td>0,0,0</td><td>3D World Vector</td><td>Position relative to body </td></tr>
<tr><td>Palette</td><td></td><td>String</td><td>Custom palette name </td></tr>
</table>


### DebugPauseState
Checks for pause related desyncs. Attach this to the world actor.

### FrozenActorLayer
Required for FrozenUnderFog to work. Attach this to the player actor.

Requires trait: [`Shroud`](#shroud).
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>BinSize</td><td>10</td><td>Integer</td><td>Size of partition bins (cells) </td></tr>
</table>

### Shroud
Required for shroud and fog visibility checks. Add this to the player actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>FogCheckboxLabel</td><td>Fog of War</td><td>String</td><td>Descriptive label for the fog checkbox in the lobby. </td></tr>
<tr><td>FogCheckboxDescription</td><td>Line of sight is required to view enemy forces</td><td>String</td><td>Tooltip description for the fog checkbox in the lobby. </td></tr>
<tr><td>FogCheckboxEnabled</td><td>True</td><td>Boolean</td><td>Default value of the fog checkbox in the lobby. </td></tr>
<tr><td>FogCheckboxLocked</td><td>False</td><td>Boolean</td><td>Prevent the fog enabled state from being changed in the lobby. </td></tr>
<tr><td>FogCheckboxVisible</td><td>True</td><td>Boolean</td><td>Whether to display the fog checkbox in the lobby. </td></tr>
<tr><td>FogCheckboxDisplayOrder</td><td>0</td><td>Integer</td><td>Display order for the fog checkbox in the lobby. </td></tr>
<tr><td>ExploredMapCheckboxLabel</td><td>Explored Map</td><td>String</td><td>Descriptive label for the explored map checkbox in the lobby. </td></tr>
<tr><td>ExploredMapCheckboxDescription</td><td>Initial map shroud is revealed</td><td>String</td><td>Tooltip description for the explored map checkbox in the lobby. </td></tr>
<tr><td>ExploredMapCheckboxEnabled</td><td>False</td><td>Boolean</td><td>Default value of the explore map checkbox in the lobby. </td></tr>
<tr><td>ExploredMapCheckboxLocked</td><td>False</td><td>Boolean</td><td>Prevent the explore map enabled state from being changed in the lobby. </td></tr>
<tr><td>ExploredMapCheckboxVisible</td><td>True</td><td>Boolean</td><td>Whether to display the explore map checkbox in the lobby. </td></tr>
<tr><td>ExploredMapCheckboxDisplayOrder</td><td>0</td><td>Integer</td><td>Display order for the explore map checkbox in the lobby. </td></tr>
</table>

### DebugVisualizations
Enables visualization commands. Attach this to the world actor.

### Faction
Attach this to the `World` actor.
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>Name</td><td></td><td>String</td><td>This is the name exposed to the players. </td></tr>
<tr><td>InternalName</td><td></td><td>String</td><td>This is the internal name for owner checks. </td></tr>
<tr><td>RandomFactionMembers</td><td></td><td>Set of System.String[]</td><td>Pick a random faction as the player's faction out of this list. </td></tr>
<tr><td>Side</td><td></td><td>String</td><td>The side that the faction belongs to. For example, England belongs to the 'Allies' side. </td></tr>
<tr><td>Description</td><td></td><td>String</td><td></td></tr>
<tr><td>Selectable</td><td>True</td><td>Boolean</td><td></td></tr>
</table>

### ScreenMap
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>BinSize</td><td>250</td><td>Integer</td><td>Size of partition bins (world pixels) </td></tr>
</table>

### ScreenShaker
<table>
<tr><th>Property</th><th>Default Value</th><th>Type</th><th>Description</th></tr>
<tr><td>MinMultiplier</td><td>-3,-3</td><td>2D Real Number</td><td></td></tr>
<tr><td>MaxMultiplier</td><td>3,3</td><td>2D Real Number</td><td></td></tr>
</table>
