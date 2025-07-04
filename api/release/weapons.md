# Weapons

This documentation is aimed at modders and has been automatically generated for version `20250628` of OpenHV. Please do not edit it directly, but instead add new `[Desc("String")]` tags to the source code.

Listed below are a template for weapon definitions and the types it can use (warheads and projectiles) with default values and developer commentary.
Related types with their possible values are listed [at the bottom](#related-value-types-enums).


### Weapon

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| Range | 0c0 | 1D World Distance | The maximum range the weapon can fire. |
| FirstBurstTargetOffset | 0,0,0 | 3D World Vector | First burst is aimed at this offset relative to target position. |
| FollowingBurstTargetOffset | 0,0,0 | 3D World Vector | Each burst after the first lands by this offset away from the previous burst. |
| Report |  | Collection of String | The sound played each time the weapon is fired. |
| StartBurstReport |  | Collection of String | Sound played only on first burst in a salvo. |
| AfterFireSound |  | Collection of String | The sound played when the weapon is reloaded. |
| AfterFireSoundDelay | 0 | Integer | Delay in ticks to play reloading sound. |
| ReloadDelay | 1 | Integer | Delay in ticks between reloading ammo magazines. |
| Burst | 1 | Integer | Number of shots in a single ammo magazine. |
| CanTargetSelf | False | Boolean | Can this weapon target the attacker itself? |
| ValidTargets | Ground, Water | Collection of TargetableType | What types of targets are affected. |
| InvalidTargets |  | Collection of TargetableType | What types of targets are unaffected. Overrules ValidTargets. |
| AirThreshold | 0c128 | 1D World Distance | If weapon is not directly targeting an actor and targeted position is above this altitude, the weapon will ignore terrain target types and only check TargetTypeAir for validity. |
| BurstDelays | 5 | Collection of Integer | Delay in ticks between firing shots from the same ammo magazine. If one entry, it will be used for all bursts. If multiple entries, their number needs to match Burst - 1. |
| MinRange | 0c0 | 1D World Distance | The minimum range the weapon can fire. |
| TargetActorCenter | False | Boolean | Does this weapon aim at the target's center regardless of other targetable offsets? |
| Projectile |  | Projectile |  |
| Warheads |  | Collection of Warhead |  |


### AreaBeam
**Beam projectile that travels in a straight line.**

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| Speed | 0c128 | Collection of 1D World Distance | Projectile speed in WDist / tick, two values indicate a randomly picked velocity per beam. |
| Duration | 10 | Integer | The maximum duration (in ticks) of each beam burst. |
| DamageInterval | 3 | Integer | The number of ticks between the beam causing warhead impacts in its area of effect. |
| Width | 0c512 | 1D World Distance | The width of the beam. |
| Shape | Cylindrical | [`BeamRenderableShape`](#beamrenderableshape) | The shape of the beam.  Accepts values Cylindrical or Flat. |
| BeyondTargetRange | 0c0 | 1D World Distance | How far beyond the target the projectile keeps on travelling. |
| MinDistance | 0c0 | 1D World Distance | The minimum distance the beam travels. |
| Falloff | 100, 100 | Collection of Integer | Damage modifier applied at each range step. |
| Range | 0c0, 2097151c1023 | Collection of 1D World Distance | Ranges at which each Falloff step is defined. |
| Inaccuracy | 0c0 | 1D World Distance | The maximum/constant/incremental inaccuracy used in conjunction with the InaccuracyType property. |
| InaccuracyType | Maximum | [`InaccuracyType`](#inaccuracytype) | Controls the way inaccuracy is calculated. Possible values are 'Maximum' - scale from 0 to max with range, 'PerCellIncrement' - scale from 0 with range, 'Absolute' - use set value regardless of range. |
| Blockable | False | Boolean | Can this projectile be blocked when hitting actors with an IBlocksProjectiles trait. |
| TrackTarget | False | Boolean | Does the beam follow the target. |
| RenderBeam | True | Boolean | Should the beam be visually rendered? False = Beam is invisible. |
| ZOffset | 0 | Integer | Equivalent to sequence ZOffset. Controls Z sorting. |
| Color | FF0000 | Color (RRGGBB[AA] notation) | Color of the beam. |
| UsePlayerColor | False | Boolean | Beam color is the player's color. |

### Bullet
**Projectile that travels in a straight line or arc.**

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| Speed | 0c17 | Collection of 1D World Distance | Projectile speed in WDist / tick, two values indicate variable velocity. |
| Inaccuracy | 0c0 | 1D World Distance | The maximum/constant/incremental inaccuracy used in conjunction with the InaccuracyType property. |
| InaccuracyType | Maximum | [`InaccuracyType`](#inaccuracytype) | Controls the way inaccuracy is calculated. Possible values are 'Maximum' - scale from 0 to max with range, 'PerCellIncrement' - scale from 0 with range, 'Absolute' - use set value regardless of range. |
| Image |  | String | Image to display. |
| Sequences | idle | Collection of String | Loop a randomly chosen sequence of Image from this list while this projectile is moving. |
| Palette | effect | String | The palette used to draw this projectile. |
| IsPlayerPalette | False | Boolean | Palette is a player palette BaseName |
| Shadow | False | Boolean | Does this projectile have a shadow? |
| ShadowColor | 0000008C | Color (RRGGBB[AA] notation) | Color to draw shadow if Shadow is true. |
| TrailImage |  | String | Trail animation. |
| TrailSequences | idle | Collection of String | Loop a randomly chosen sequence of TrailImage from this list while this projectile is moving. |
| TrailInterval | 2 | Integer | Interval in ticks between each spawned Trail animation. |
| TrailDelay | 1 | Integer | Delay in ticks until trail animation is spawned. |
| TrailPalette | effect | String | Palette used to render the trail sequence. |
| TrailUsePlayerPalette | False | Boolean | Use the Player Palette to render the trail sequence. |
| Blockable | True | Boolean | Is this blocked by actors with BlocksProjectiles trait. |
| Width | 0c1 | 1D World Distance | Width of projectile (used for finding blocking actors). |
| LaunchAngle | 0 | Collection of 1D World Angle | Arc in WAngles, two values indicate variable arc. |
| BounceCount | 0 | Integer | Up to how many times does this bullet bounce when touching ground without hitting a target. 0 implies exploding on contact with the originally targeted position. |
| BounceRangeModifier | 60 | Integer | Modify distance of each bounce by this percentage of previous distance. |
| BounceSound |  | String | Sound to play when the projectile hits the ground, but not the target. |
| InvalidBounceTerrain |  | Set of String | Terrain where the projectile explodes instead of bouncing. |
| ValidBounceBlockerRelationships | Enemy, Neutral | [`PlayerRelationship`](#playerrelationship) | Trigger the explosion if the projectile touches an actor thats owner has these player relationships. |
| AirburstAltitude | 0c0 | 1D World Distance | Altitude above terrain below which to explode. Zero effectively deactivates airburst. |
| ContrailLength | 0 | Integer | When set, display a line behind the actor. Length is measured in ticks after appearing. |
| ContrailDelay | 1 | Integer | Time (in ticks) after which the line should appear. Controls the distance to the actor. |
| ContrailZOffset | 2047 | Integer | Equivalent to sequence ZOffset. Controls Z sorting. |
| ContrailStartWidth | 0c64 | 1D World Distance | Thickness of the emitted line at the start of the contrail. |
| ContrailEndWidth |  | 1D World Distance (optional) | Thickness of the emitted line at the end of the contrail. Will default to ContrailStartWidth if left undefined |
| ContrailStartColor | FFFFFF | Color (RRGGBB[AA] notation) | RGB color at the contrail start. |
| ContrailStartColorUsePlayerColor | False | Boolean | Use player remap color instead of a custom color at the contrail the start. |
| ContrailStartColorAlpha | 255 | Integer | The alpha value [from 0 to 255] of color at the contrail the start. |
| ContrailEndColor |  | Color (RRGGBB[AA] notation) (optional) | RGB color at the contrail end. Will default to ContrailStartColor if left undefined |
| ContrailEndColorUsePlayerColor | False | Boolean | Use player remap color instead of a custom color at the contrail end. |
| ContrailEndColorAlpha | 0 | Integer | The alpha value [from 0 to 255] of color at the contrail end. |

### GravityBomb
**Projectile with customisable acceleration vector.**

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| Image |  | String |  |
| Sequences | idle | Collection of String | Loop a randomly chosen sequence of Image from this list while falling. |
| OpenSequence |  | String | Sequence to play when launched. Skipped if null or empty. |
| Palette | effect | String | The palette used to draw this projectile. |
| IsPlayerPalette | False | Boolean | Palette is a player palette BaseName |
| Shadow | False | Boolean | Does this projectile have a shadow? |
| ShadowColor | 0000008C | Color (RRGGBB[AA] notation) | Color to draw shadow if Shadow is true. |
| Velocity | 0,0,0 | 3D World Vector | Projectile movement vector per tick (forward, right, up), use negative values for opposite directions. |
| Acceleration | 0,0,-15 | 3D World Vector | Value added to Velocity every tick. |

### InstantHit
**Instant, invisible, usually direct-on-target projectile.**

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| Inaccuracy | 0c0 | 1D World Distance | The maximum/constant/incremental inaccuracy used in conjunction with the InaccuracyType property. |
| InaccuracyType | Maximum | [`InaccuracyType`](#inaccuracytype) | Controls the way inaccuracy is calculated. Possible values are 'Maximum' - scale from 0 to max with range, 'PerCellIncrement' - scale from 0 with range, 'Absolute' - use set value regardless of range. |
| Blockable | False | Boolean | Projectile can be blocked. |
| Width | 0c1 | 1D World Distance | The width of the projectile. |
| BlockerScanRadius | -0c1 | 1D World Distance | Scan radius for actors with projectile-blocking trait. If set to a negative value (default), it will automatically scale to the blocker with the largest health shape. Only set custom values if you know what you're doing. |

### LaserZap
**Not a sprite, but an engine effect.**

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| Width | 0c86 | 1D World Distance | The width of the zap. |
| Shape | Cylindrical | [`BeamRenderableShape`](#beamrenderableshape) | The shape of the beam.  Accepts values Cylindrical or Flat. |
| ZOffset | 0 | Integer | Equivalent to sequence ZOffset. Controls Z sorting. |
| Duration | 10 | Integer | The maximum duration (in ticks) of the beam's existence. |
| DamageDuration | 1 | Integer | Total time-frame in ticks that the beam deals damage every DamageInterval. |
| DamageInterval | 1 | Integer | The number of ticks between the beam causing warhead impacts in its area of effect. |
| UsePlayerColor | False | Boolean |  |
| Color | FF0000 | Color (RRGGBB[AA] notation) | Color of the beam. |
| TrackTarget | True | Boolean | Beam follows the target. |
| Inaccuracy | 0c0 | 1D World Distance | The maximum/constant/incremental inaccuracy used in conjunction with the InaccuracyType property. |
| InaccuracyType | Maximum | [`InaccuracyType`](#inaccuracytype) | Controls the way inaccuracy is calculated. Possible values are 'Maximum' - scale from 0 to max with range, 'PerCellIncrement' - scale from 0 with range, 'Absolute' - use set value regardless of range. |
| Blockable | False | Boolean | Beam can be blocked. |
| SecondaryBeam | False | Boolean | Draw a second beam (for 'glow' effect). |
| SecondaryBeamWidth | 0c86 | 1D World Distance | The width of the zap. |
| SecondaryBeamShape | Cylindrical | [`BeamRenderableShape`](#beamrenderableshape) | The shape of the beam.  Accepts values Cylindrical or Flat. |
| SecondaryBeamZOffset | 0 | Integer | Equivalent to sequence ZOffset. Controls Z sorting. |
| SecondaryBeamUsePlayerColor | False | Boolean |  |
| SecondaryBeamColor | FF0000 | Color (RRGGBB[AA] notation) | Color of the secondary beam. |
| HitAnim |  | String | Impact animation. |
| HitAnimSequence | idle | String | Sequence of impact animation to use. |
| HitAnimPalette | effect | String |  |
| LaunchEffectImage |  | String | Image containing launch effect sequence. |
| LaunchEffectSequence |  | String | Launch effect sequence to play. |
| LaunchEffectPalette | effect | String | Palette to use for launch effect. |

### Missile
**Projectile with smart tracking.**

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| Image |  | String | Name of the image containing the projectile sequence. |
| Sequences | idle | Collection of String | Loop a randomly chosen sequence of Image from this list while this projectile is moving. |
| Palette | effect | String | Palette used to render the projectile sequence. |
| IsPlayerPalette | False | Boolean | Palette is a player palette BaseName |
| Shadow | False | Boolean | Does this projectile have a shadow? |
| ShadowColor | 0000008C | Color (RRGGBB[AA] notation) | Color to draw shadow if Shadow is true. |
| MinimumLaunchAngle | 960 | 1D World Angle | Minimum vertical launch angle (pitch). |
| MaximumLaunchAngle | 128 | 1D World Angle | Maximum vertical launch angle (pitch). |
| MinimumLaunchSpeed | -0c1 | 1D World Distance | Minimum launch speed in WDist / tick. Defaults to Speed if -1. |
| MaximumLaunchSpeed | -0c1 | 1D World Distance | Maximum launch speed in WDist / tick. Defaults to Speed if -1. |
| Speed | 0c384 | 1D World Distance | Maximum projectile speed in WDist / tick |
| Acceleration | 0c5 | 1D World Distance | Projectile acceleration when propulsion activated. |
| Arm | 0 | Integer | How many ticks before this missile is armed and can explode. |
| Blockable | True | Boolean | Is the missile blocked by actors with BlocksProjectiles: trait. |
| TerrainHeightAware | False | Boolean | Is the missile aware of terrain height levels. Only needed for mods with real, non-visual height levels. |
| Width | 0c1 | 1D World Distance | Width of projectile (used for finding blocking actors). |
| Inaccuracy | 0c0 | 1D World Distance | The maximum/constant/incremental inaccuracy used in conjunction with the InaccuracyType property. |
| InaccuracyType | Absolute | [`InaccuracyType`](#inaccuracytype) | Controls the way inaccuracy is calculated. Possible values are 'Maximum' - scale from 0 to max with range, 'PerCellIncrement' - scale from 0 with range, 'Absolute' - use set value regardless of range. |
| LockOnInaccuracy | -0c1 | 1D World Distance | Inaccuracy override when successfully locked onto target. Defaults to Inaccuracy if negative. |
| LockOnProbability | 100 | Integer | Probability of locking onto and following target. |
| HorizontalRateOfTurn | 20 | 1D World Angle | Horizontal rate of turn. |
| VerticalRateOfTurn | 24 | 1D World Angle | Vertical rate of turn. |
| Gravity | 10 | Integer | Gravity applied while in free fall. |
| RangeLimit | 0c0 | 1D World Distance | Run out of fuel after covering this distance. Zero for defaulting to weapon range. Negative for unlimited fuel. |
| ExplodeWhenEmpty | True | Boolean | Explode when running out of fuel. |
| AirburstAltitude | 0c0 | 1D World Distance | Altitude above terrain below which to explode. Zero effectively deactivates airburst. |
| CruiseAltitude | 0c512 | 1D World Distance | Cruise altitude. Zero means no cruise altitude used. |
| HomingActivationDelay | 0 | Integer | Activate homing mechanism after this many ticks. |
| TrailImage |  | String | Image that contains the trail animation. |
| TrailSequences | idle | Collection of String | Loop a randomly chosen sequence of TrailImage from this list while this projectile is moving. |
| TrailPalette | effect | String | Palette used to render the trail sequence. |
| TrailUsePlayerPalette | False | Boolean | Use the Player Palette to render the trail sequence. |
| TrailInterval | 2 | Integer | Interval in ticks between spawning trail animation. |
| TrailWhenDeactivated | False | Boolean | Should trail animation be spawned when the propulsion is not activated. |
| ContrailLength | 0 | Integer | When set, display a line behind the actor. Length is measured in ticks after appearing. |
| ContrailDelay | 1 | Integer | Time (in ticks) after which the line should appear. Controls the distance to the actor. |
| ContrailZOffset | 2047 | Integer | Equivalent to sequence ZOffset. Controls Z sorting. |
| ContrailStartWidth | 0c64 | 1D World Distance | Thickness of the emitted line at the start of the contrail. |
| ContrailEndWidth |  | 1D World Distance (optional) | Thickness of the emitted line at the end of the contrail. Will default to ContrailStartWidth if left undefined |
| ContrailStartColor | FFFFFF | Color (RRGGBB[AA] notation) | RGB color at the contrail start. |
| ContrailStartColorUsePlayerColor | False | Boolean | Use player remap color instead of a custom color at the contrail the start. |
| ContrailStartColorAlpha | 255 | Integer | The alpha value [from 0 to 255] of color at the contrail the start. |
| ContrailEndColor |  | Color (RRGGBB[AA] notation) (optional) | RGB color at the contrail end. Will default to ContrailStartColor if left undefined |
| ContrailEndColorUsePlayerColor | False | Boolean | Use player remap color instead of a custom color at the contrail end. |
| ContrailEndColorAlpha | 0 | Integer | The alpha value [from 0 to 255] of color at the contrail end. |
| Jammable | True | Boolean | Should missile targeting be thrown off by nearby actors with JamsMissiles. |
| JammedDiversionRange | 20 | Integer | Range of facings by which jammed missiles can stray from current path. |
| BoundToTerrainType |  | String | Explodes when leaving the following terrain type, e.g., Water for torpedoes. |
| AllowSnapping | False | Boolean | Allow the missile to snap to the target, meaning jumping to the target immediately when the missile enters the radius of the current speed around the target. |
| CloseEnough | 0c298 | 1D World Distance | Explodes when inside this proximity radius to target. Note: If this value is lower than the missile speed, this check might not trigger fast enough, causing the missile to fly past the target. |

### Railgun
**Laser effect with helix coiling around.**

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| DamageActorsInLine | False | Boolean | Damage all units hit by the beam instead of just the target? |
| Inaccuracy | 0c0 | 1D World Distance | The maximum/constant/incremental inaccuracy used in conjunction with the InaccuracyType property. |
| InaccuracyType | Maximum | [`InaccuracyType`](#inaccuracytype) | Controls the way inaccuracy is calculated. Possible values are 'Maximum' - scale from 0 to max with range, 'PerCellIncrement' - scale from 0 with range, 'Absolute' - use set value regardless of range. |
| Blockable | False | Boolean | Can this projectile be blocked when hitting actors with an IBlocksProjectiles trait. |
| Duration | 15 | Integer | Duration of the beam and helix |
| ZOffset | 0 | Integer | Equivalent to sequence ZOffset. Controls Z sorting. |
| BeamWidth | 0c86 | 1D World Distance | The width of the main trajectory. ("beam"). |
| BeamShape | Cylindrical | [`BeamRenderableShape`](#beamrenderableshape) | The shape of the beam.  Accepts values Cylindrical or Flat. |
| BeamColor | FFFFFF80 | Color (RRGGBB[AA] notation) | Beam color in (A),R,G,B. |
| BeamPlayerColor | False | Boolean | When true, this will override BeamColor parameter and draw the laser with player color. (Still uses BeamColor's alpha information) |
| BeamAlphaDeltaPerTick | -8 | Integer | Beam alpha gets + this value per tick during drawing; hence negative value makes it fade over time. |
| HelixThickness | 0c32 | 1D World Distance | Thickness of the helix |
| HelixRadius | 0c64 | 1D World Distance | The radius of the spiral effect. (WDist) |
| HelixPitch | 0c512 | 1D World Distance | Height of one complete helix turn, measured parallel to the axis of the helix (WDist) |
| HelixRadiusDeltaPerTick | 8 | Integer | Helix radius gets + this value per tick during drawing |
| HelixAlphaDeltaPerTick | -8 | Integer | Helix alpha gets + this value per tick during drawing; hence negative value makes it fade over time. |
| HelixAngleDeltaPerTick | 16 | 1D World Angle | Helix spins by this much over time each tick. |
| QuantizationCount | 16 | Integer | Draw each cycle of helix with this many quantization steps |
| HelixColor | FFFFFF80 | Color (RRGGBB[AA] notation) | Helix color in (A),R,G,B. |
| HelixPlayerColor | False | Boolean | Draw helix in PlayerColor? Overrides RGB part of the HelixColor. (Still uses HelixColor's alpha information) |
| HitAnim |  | String | Impact animation. |
| HitAnimSequence | idle | String | Sequence of impact animation to use. |
| HitAnimPalette | effect | String |  |


### ArcLaserZap
**Not a sprite, but an engine effect.**

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| Width | 0c86 | 1D World Distance | The width of the zap. |
| ZOffset | 0 | Integer | Equivalent to sequence ZOffset. Controls Z sorting. |
| Duration | 10 | Integer |  |
| Angle | 85 | 1D World Angle | The angle of the arc of the beam. |
| QuantizedSegments | 32 | Integer | Controls how fine-grained the resulting arc should be. |
| UsePlayerColor | False | Boolean |  |
| Color | FF0000 | Color (RRGGBB[AA] notation) | Color of the beam. |
| TrackTarget | True | Boolean | Beam follows the target. |
| Inaccuracy | 0c0 | 1D World Distance | Maximum offset at the maximum range. |
| Blockable | False | Boolean | Beam can be blocked. |
| HitAnim |  | String | Impact animation. |
| HitAnimSequence | idle | String | Sequence of impact animation to use. |
| HitAnimPalette | effect | String |  |

### EnergyBolt
**Renders an energy discharge.**

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| Duration | 10 | Integer | The maximum duration (in ticks) of the beam's existence. |
| Color | FFFFFF00 | Color (RRGGBB[AA] notation) | Color of the beam. Default falls back to player color. |
| InnerLightness | 255 | Byte | Inner lightness of the beam. |
| OuterLightness | 128 | Byte | Outer lightness of the beam. |
| Radius | 3 | Integer | The radius of the beam. |
| Distortion | 0 | Integer | Distortion offset. |
| DistortionAnimation | 0 | Integer | Distortion animation offset. |
| SegmentLength | 0c0 | 1D World Distance | Maximum length per segment. |
| FadeOut | False | Boolean | Fade the beams out during lifetime. |
| ZOffset | 0 | Integer | Equivalent to sequence ZOffset. Controls Z sorting. |

### InstantExplode
**Imminently explode the weapon directly at the firing position. Written with cases where the actor would attack everything around itself in an aura pattern, but without self-destructing.**

### InstantHitWithTracers
**Instant and usually direct-on-target projectile, with tracer ammunition.**

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| Inaccuracy | 0c0 | 1D World Distance | The maximum/constant/incremental inaccuracy used in conjunction with the InaccuracyType property. |
| InaccuracyType | Maximum | [`InaccuracyType`](#inaccuracytype) | Controls the way inaccuracy is calculated.  Possible values are 'Maximum' - scale from 0 to max with range,  'PerCellIncrement' - scale from 0 with range and 'Absolute' - use set value regardless of range. |
| Blockable | False | Boolean | Projectile can be blocked. |
| Width | 0c1 | 1D World Distance | The width of the projectile. |
| BlockerScanRadius | -0c1 | 1D World Distance | Scan radius for actors with projectile-blocking trait. If set to a negative value (default), it will automatically scale to the blocker with the largest health shape. Only set custom values if you know what you're doing. |
| TracerAmount | 0 | Integer | Amount of Tracers. |
| TracerSpawnInterval | 3 | Integer | Tracer spawn interval. Only useful when Amount > 0 |
| TracerSpeed | 1024 | Integer | Tracer speed |
| TracerInaccuracy | 0c0 | 1D World Distance | Tracer inaccuracy, use set value regardless of range |
| Image |  | String | Image to display. |
| Sequence | idle | String | Loop sequence of Image from this list while this projectile is moving. |
| Palette | effect | String | The palette used to draw this projectile. |
| IsPlayerPalette | False | Boolean |  |
| TrailImage |  | String | Trail animation. |
| TrailSequence | idle | String | Loop sequence of TrailImage from this list while this projectile is moving. |
| TrailInterval | 2 | Integer | Interval in ticks between each spawned Trail animation. |
| TrailPalette | effect | String | Palette used to render the trail sequence. |
| TrailUsePlayerPalette | False | Boolean | Use the Player Palette to render the trail sequence. |
| ContrailLength | 0 | Integer | When set, display a line behind the tracer bullet. Length is measured in ticks after appearing. |
| ContrailDelay | 1 | Integer | Time (in ticks) after which the line should appear. Controls the distance to the actor. |
| ContrailZOffset | 2047 | Integer | Equivalent to sequence ZOffset. Controls Z sorting. |
| ContrailStartWidth | 0c64 | 1D World Distance | Thickness of the emitted line at the start of the contrail. |
| ContrailEndWidth |  | 1D World Distance (optional) | Thickness of the emitted line at the end of the contrail. Will default to ContrailStartWidth if left undefined |
| ContrailStartColor | FFFFFF | Color (RRGGBB[AA] notation) | RGB color at the contrail start. |
| ContrailStartColorUsePlayerColor | False | Boolean | Use player remap color instead of a custom color at the contrail the start. |
| ContrailStartColorAlpha | 255 | Integer | The alpha value [from 0 to 255] of color at the contrail the start. |
| ContrailEndColor |  | Color (RRGGBB[AA] notation) (optional) | RGB color at the contrail end. Will default to ContrailStartColor if left undefined |
| ContrailEndColorUsePlayerColor | False | Boolean | Use player remap color instead of a custom color at the contrail end. |
| ContrailEndColorAlpha | 0 | Integer | The alpha value [from 0 to 255] of color at the contrail end. |


### ChangeOwnerWarhead
**Interacts with the `TemporaryOwnerManager` trait.**

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| Duration | 0 | Integer | Duration of the owner change (in ticks). Set to 0 to make it permanent. |
| Range | 1c0 | 1D World Distance |  |
| ValidTargets | Ground, Water | Collection of TargetableType | What types of targets are affected. |
| InvalidTargets |  | Collection of TargetableType | What types of targets are unaffected. Overrules ValidTargets. |
| ValidRelationships | Enemy, Neutral, Ally | [`PlayerRelationship`](#playerrelationship) | What player relationships are affected. |
| AffectsParent | False | Boolean | Can this warhead affect the actor that fired it. |
| AirThreshold | 0c128 | 1D World Distance | If impact is above this altitude, warheads that would affect terrain ignore terrain target types (and either do nothing or perform their own checks). |
| Delay | 0 | Integer | Delay in ticks before applying the warhead effect. 0 = instant (old model). |
| DebugOverlayColor | FF0000 | Color (RRGGBB[AA] notation) | The color used for this warhead's visualization in the world's `WarheadDebugOverlay` trait. |

### CreateEffectWarhead
**Spawn a sprite with sound.**

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| Explosions |  | Collection of String | List of explosion sequences that can be used. |
| Image | explosion | String | Image containing explosion effect sequence. |
| ExplosionPalette | effect | String | Palette to use for explosion effect. |
| UsePlayerPalette | False | Boolean | Remap explosion effect to player color, if art supports it. |
| ForceDisplayAtGroundLevel | False | Boolean | Display explosion effect at ground level, regardless of explosion altitude. |
| ImpactSounds |  | Collection of String | List of sounds that can be played on impact. |
| ImpactSoundChance | 100 | Integer | Chance of impact sound to play. |
| ImpactActors | True | Boolean | Whether to consider actors in determining whether the explosion should happen. If false, only terrain will be considered. |
| Inaccuracy | 0c0 | 1D World Distance | The maximum inaccuracy of the effect spawn position relative to actual impact position. |
| ValidTargets | Ground, Water | Collection of TargetableType | What types of targets are affected. |
| InvalidTargets |  | Collection of TargetableType | What types of targets are unaffected. Overrules ValidTargets. |
| ValidRelationships | Enemy, Neutral, Ally | [`PlayerRelationship`](#playerrelationship) | What player relationships are affected. |
| AffectsParent | False | Boolean | Can this warhead affect the actor that fired it. |
| AirThreshold | 0c128 | 1D World Distance | If impact is above this altitude, warheads that would affect terrain ignore terrain target types (and either do nothing or perform their own checks). |
| Delay | 0 | Integer | Delay in ticks before applying the warhead effect. 0 = instant (old model). |
| DebugOverlayColor | FF0000 | Color (RRGGBB[AA] notation) | The color used for this warhead's visualization in the world's `WarheadDebugOverlay` trait. |

### CreateResourceWarhead
**Creates resources in a circle.**

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| Size | 0, 0 | Collection of Integer | Size of the area. The resources are seeded within this area. Provide 2 values for a ring effect (outer/inner). |
| AddsResourceType | *(required)* | String | Will this splatter resources and which? |
| ValidTargets | Ground, Water | Collection of TargetableType | What types of targets are affected. |
| InvalidTargets |  | Collection of TargetableType | What types of targets are unaffected. Overrules ValidTargets. |
| ValidRelationships | Enemy, Neutral, Ally | [`PlayerRelationship`](#playerrelationship) | What player relationships are affected. |
| AffectsParent | False | Boolean | Can this warhead affect the actor that fired it. |
| AirThreshold | 0c128 | 1D World Distance | If impact is above this altitude, warheads that would affect terrain ignore terrain target types (and either do nothing or perform their own checks). |
| Delay | 0 | Integer | Delay in ticks before applying the warhead effect. 0 = instant (old model). |
| DebugOverlayColor | FF0000 | Color (RRGGBB[AA] notation) | The color used for this warhead's visualization in the world's `WarheadDebugOverlay` trait. |

### DestroyResourceWarhead
**Destroys resources in a circle.**

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| Size | 0, 0 | Collection of Integer | Size of the area. The resources are removed within this area. Provide 2 values for a ring effect (outer/inner). |
| ResourceAmount | 0 | Integer | Amount of resources to be removed. If negative or zero, all resources within the area will be removed. |
| ResourceTypes |  | Set of String | Resource types to remove with this warhead. If empty, all resource types will be removed. |
| ValidTargets | Ground, Water | Collection of TargetableType | What types of targets are affected. |
| InvalidTargets |  | Collection of TargetableType | What types of targets are unaffected. Overrules ValidTargets. |
| ValidRelationships | Enemy, Neutral, Ally | [`PlayerRelationship`](#playerrelationship) | What player relationships are affected. |
| AffectsParent | False | Boolean | Can this warhead affect the actor that fired it. |
| AirThreshold | 0c128 | 1D World Distance | If impact is above this altitude, warheads that would affect terrain ignore terrain target types (and either do nothing or perform their own checks). |
| Delay | 0 | Integer | Delay in ticks before applying the warhead effect. 0 = instant (old model). |
| DebugOverlayColor | FF0000 | Color (RRGGBB[AA] notation) | The color used for this warhead's visualization in the world's `WarheadDebugOverlay` trait. |

### FireClusterWarhead
**Fires weapons from the point of impact.**

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| Weapon | *(required)* | String | Has to be defined in weapons.yaml as well. |
| RandomClusterCount | -1 | Integer | Number of weapons fired at random 'x' cells. Negative values will result in a number equal to 'x' footprint cells fired. |
| Dimensions | 0,0 | 2D Cell Vector | Size of the cluster footprint |
| Footprint | *(required)* | String | Cluster footprint. Cells marked as X will be attacked. Cells marked as x will be attacked randomly until RandomClusterCount is reached. |
| ValidTargets | Ground, Water | Collection of TargetableType | What types of targets are affected. |
| InvalidTargets |  | Collection of TargetableType | What types of targets are unaffected. Overrules ValidTargets. |
| ValidRelationships | Enemy, Neutral, Ally | [`PlayerRelationship`](#playerrelationship) | What player relationships are affected. |
| AffectsParent | False | Boolean | Can this warhead affect the actor that fired it. |
| AirThreshold | 0c128 | 1D World Distance | If impact is above this altitude, warheads that would affect terrain ignore terrain target types (and either do nothing or perform their own checks). |
| Delay | 0 | Integer | Delay in ticks before applying the warhead effect. 0 = instant (old model). |
| DebugOverlayColor | FF0000 | Color (RRGGBB[AA] notation) | The color used for this warhead's visualization in the world's `WarheadDebugOverlay` trait. |

### FlashEffectWarhead
**Used to trigger a FlashPostProcessEffect trait on the world actor.**

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| FlashType |  | String | Corresponds to `Type` from `FlashPostProcessEffect` on the world actor. |
| Duration | 0 | Integer | Duration of the flashing, measured in ticks. Set to -1 to default to the `Length` of the `FlashPostProcessEffect`. |
| ValidTargets | Ground, Water | Collection of TargetableType | What types of targets are affected. |
| InvalidTargets |  | Collection of TargetableType | What types of targets are unaffected. Overrules ValidTargets. |
| ValidRelationships | Enemy, Neutral, Ally | [`PlayerRelationship`](#playerrelationship) | What player relationships are affected. |
| AffectsParent | False | Boolean | Can this warhead affect the actor that fired it. |
| AirThreshold | 0c128 | 1D World Distance | If impact is above this altitude, warheads that would affect terrain ignore terrain target types (and either do nothing or perform their own checks). |
| Delay | 0 | Integer | Delay in ticks before applying the warhead effect. 0 = instant (old model). |
| DebugOverlayColor | FF0000 | Color (RRGGBB[AA] notation) | The color used for this warhead's visualization in the world's `WarheadDebugOverlay` trait. |

### FlashTargetsInRadiusWarhead
**Trigger a flash effect on the targeted actor, or actors within a circle.**

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| ActorFlashOverlayColor | FFFFFF | Color (RRGGBB[AA] notation) | The overlay color to display when ActorFlashType is Overlay. |
| ActorFlashOverlayAlpha | 0.5 | Real Number | The overlay transparency to display when ActorFlashType is Overlay. |
| ActorFlashTint | 1.4,1.4,1.4 | float3 | The tint to apply when ActorFlashType is Tint. |
| ActorFlashCount | 2 | Integer | Number of times to flash actors. |
| ActorFlashInterval | 2 | Integer | Number of ticks between actor flashes. |
| Radius | 0c0 | 1D World Distance | Radius of an area at which effect will be applied. If left default effect applies only to target actor. |
| DamageCalculationType | HitShape | [`DamageCalculationType`](#damagecalculationtype) | Controls the way damage is calculated. Possible values are 'HitShape', 'ClosestTargetablePosition' and 'CenterPosition'. |
| ValidTargets | Ground, Water | Collection of TargetableType | What types of targets are affected. |
| InvalidTargets |  | Collection of TargetableType | What types of targets are unaffected. Overrules ValidTargets. |
| ValidRelationships | Enemy, Neutral, Ally | [`PlayerRelationship`](#playerrelationship) | What player relationships are affected. |
| AffectsParent | False | Boolean | Can this warhead affect the actor that fired it. |
| AirThreshold | 0c128 | 1D World Distance | If impact is above this altitude, warheads that would affect terrain ignore terrain target types (and either do nothing or perform their own checks). |
| Delay | 0 | Integer | Delay in ticks before applying the warhead effect. 0 = instant (old model). |
| DebugOverlayColor | FF0000 | Color (RRGGBB[AA] notation) | The color used for this warhead's visualization in the world's `WarheadDebugOverlay` trait. |

### GrantExternalConditionWarhead
**Grant an external condition to hit actors.**

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| Condition | *(required)* | String | The condition to apply. Must be included in the target actor's ExternalConditions list. |
| Duration | 0 | Integer | Duration of the condition (in ticks). Set to 0 for a permanent condition. |
| Range | 1c0 | 1D World Distance |  |
| ValidTargets | Ground, Water | Collection of TargetableType | What types of targets are affected. |
| InvalidTargets |  | Collection of TargetableType | What types of targets are unaffected. Overrules ValidTargets. |
| ValidRelationships | Enemy, Neutral, Ally | [`PlayerRelationship`](#playerrelationship) | What player relationships are affected. |
| AffectsParent | False | Boolean | Can this warhead affect the actor that fired it. |
| AirThreshold | 0c128 | 1D World Distance | If impact is above this altitude, warheads that would affect terrain ignore terrain target types (and either do nothing or perform their own checks). |
| Delay | 0 | Integer | Delay in ticks before applying the warhead effect. 0 = instant (old model). |
| DebugOverlayColor | FF0000 | Color (RRGGBB[AA] notation) | The color used for this warhead's visualization in the world's `WarheadDebugOverlay` trait. |

### HealthPercentageDamageWarhead
**Apply damage based on the target's health.**

> Inherits from: [`TargetDamageWarhead`](#targetdamagewarhead), `DamageWarhead`.

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| Spread | 0c0 | 1D World Distance | Damage will be applied to actors in this area. A value of zero means only targeted actor will be damaged. |
| Damage | 0 | Integer | How much (raw) damage to deal. |
| DamageTypes |  | Collection of DamageType | Types of damage that this warhead causes. Leave empty for no damage types. |
| Versus |  | Dictionary with Key: String, Value: Integer | Damage percentage versus each armor type. |
| ValidTargets | Ground, Water | Collection of TargetableType | What types of targets are affected. |
| InvalidTargets |  | Collection of TargetableType | What types of targets are unaffected. Overrules ValidTargets. |
| ValidRelationships | Enemy, Neutral, Ally | [`PlayerRelationship`](#playerrelationship) | What player relationships are affected. |
| AffectsParent | False | Boolean | Can this warhead affect the actor that fired it. |
| AirThreshold | 0c128 | 1D World Distance | If impact is above this altitude, warheads that would affect terrain ignore terrain target types (and either do nothing or perform their own checks). |
| Delay | 0 | Integer | Delay in ticks before applying the warhead effect. 0 = instant (old model). |
| DebugOverlayColor | FF0000 | Color (RRGGBB[AA] notation) | The color used for this warhead's visualization in the world's `WarheadDebugOverlay` trait. |

### LeaveSmudgeWarhead
**Creates a smudge in `SmudgeLayer`.**

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| Size | 0, 0 | Collection of Integer | Size of the area. A smudge will be created in each tile. Provide 2 values for a ring effect (outer/inner). |
| SmudgeType |  | Set of String | Type of smudge to apply to terrain. |
| Chance | 100 | Integer | Percentage chance the smudge is created. |
| ValidTargets | Ground, Water | Collection of TargetableType | What types of targets are affected. |
| InvalidTargets |  | Collection of TargetableType | What types of targets are unaffected. Overrules ValidTargets. |
| ValidRelationships | Enemy, Neutral, Ally | [`PlayerRelationship`](#playerrelationship) | What player relationships are affected. |
| AffectsParent | False | Boolean | Can this warhead affect the actor that fired it. |
| AirThreshold | 0c128 | 1D World Distance | If impact is above this altitude, warheads that would affect terrain ignore terrain target types (and either do nothing or perform their own checks). |
| Delay | 0 | Integer | Delay in ticks before applying the warhead effect. 0 = instant (old model). |
| DebugOverlayColor | FF0000 | Color (RRGGBB[AA] notation) | The color used for this warhead's visualization in the world's `WarheadDebugOverlay` trait. |

### ShakeScreenWarhead
**Makes the screen shake.**

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| Duration | 0 | Integer | Duration of the shaking. |
| Intensity | 0 | Integer | Shake intensity. |
| Multiplier | 0,0 | 2D Real Number | Shake multipliers by the X and Y axis, comma-separated. |
| ValidTargets | Ground, Water | Collection of TargetableType | What types of targets are affected. |
| InvalidTargets |  | Collection of TargetableType | What types of targets are unaffected. Overrules ValidTargets. |
| ValidRelationships | Enemy, Neutral, Ally | [`PlayerRelationship`](#playerrelationship) | What player relationships are affected. |
| AffectsParent | False | Boolean | Can this warhead affect the actor that fired it. |
| AirThreshold | 0c128 | 1D World Distance | If impact is above this altitude, warheads that would affect terrain ignore terrain target types (and either do nothing or perform their own checks). |
| Delay | 0 | Integer | Delay in ticks before applying the warhead effect. 0 = instant (old model). |
| DebugOverlayColor | FF0000 | Color (RRGGBB[AA] notation) | The color used for this warhead's visualization in the world's `WarheadDebugOverlay` trait. |

### SpreadDamageWarhead
**Apply damage in a specified range.**

> Inherits from: `DamageWarhead`.

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| Spread | 0c43 | 1D World Distance | Range between falloff steps. |
| Falloff | 100, 37, 14, 5, 0 | Collection of Integer | Damage percentage at each range step |
| Range |  | Collection of 1D World Distance | Ranges at which each Falloff step is defined. Overrides Spread. |
| DamageCalculationType | HitShape | [`DamageCalculationType`](#damagecalculationtype) | Controls the way damage is calculated. Possible values are 'HitShape', 'ClosestTargetablePosition' and 'CenterPosition'. |
| Damage | 0 | Integer | How much (raw) damage to deal. |
| DamageTypes |  | Collection of DamageType | Types of damage that this warhead causes. Leave empty for no damage types. |
| Versus |  | Dictionary with Key: String, Value: Integer | Damage percentage versus each armor type. |
| ValidTargets | Ground, Water | Collection of TargetableType | What types of targets are affected. |
| InvalidTargets |  | Collection of TargetableType | What types of targets are unaffected. Overrules ValidTargets. |
| ValidRelationships | Enemy, Neutral, Ally | [`PlayerRelationship`](#playerrelationship) | What player relationships are affected. |
| AffectsParent | False | Boolean | Can this warhead affect the actor that fired it. |
| AirThreshold | 0c128 | 1D World Distance | If impact is above this altitude, warheads that would affect terrain ignore terrain target types (and either do nothing or perform their own checks). |
| Delay | 0 | Integer | Delay in ticks before applying the warhead effect. 0 = instant (old model). |
| DebugOverlayColor | FF0000 | Color (RRGGBB[AA] notation) | The color used for this warhead's visualization in the world's `WarheadDebugOverlay` trait. |

### TargetDamageWarhead
**Apply damage to the targeted actor.**

> Inherits from: `DamageWarhead`.

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| Spread | 0c0 | 1D World Distance | Damage will be applied to actors in this area. A value of zero means only targeted actor will be damaged. |
| Damage | 0 | Integer | How much (raw) damage to deal. |
| DamageTypes |  | Collection of DamageType | Types of damage that this warhead causes. Leave empty for no damage types. |
| Versus |  | Dictionary with Key: String, Value: Integer | Damage percentage versus each armor type. |
| ValidTargets | Ground, Water | Collection of TargetableType | What types of targets are affected. |
| InvalidTargets |  | Collection of TargetableType | What types of targets are unaffected. Overrules ValidTargets. |
| ValidRelationships | Enemy, Neutral, Ally | [`PlayerRelationship`](#playerrelationship) | What player relationships are affected. |
| AffectsParent | False | Boolean | Can this warhead affect the actor that fired it. |
| AirThreshold | 0c128 | 1D World Distance | If impact is above this altitude, warheads that would affect terrain ignore terrain target types (and either do nothing or perform their own checks). |
| Delay | 0 | Integer | Delay in ticks before applying the warhead effect. 0 = instant (old model). |
| DebugOverlayColor | FF0000 | Color (RRGGBB[AA] notation) | The color used for this warhead's visualization in the world's `WarheadDebugOverlay` trait. |


### FireRadiusWarhead
**Fires a defined amount of weapons with their maximum range in a wave pattern.**

> Inherits from: `ValidateTriggerWarhead`.

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| Weapon | *(required)* | String | Has to be defined in weapons.yaml as well. |
| Amount | 1 | Collection of Integer | Amount of weapons fired. |
| AroundTarget | False | Boolean | Should the weapons be fired around the intended target or at the explosion's epicenter. |
| TransferAltitude | False | Boolean | Should the weapons be fired towards the same altitude of the original explosion. |
| ValidTargets | Ground, Water | Collection of TargetableType | What types of targets are affected. |
| InvalidTargets |  | Collection of TargetableType | What types of targets are unaffected. Overrules ValidTargets. |
| ValidRelationships | Enemy, Neutral, Ally | [`PlayerRelationship`](#playerrelationship) | What player relationships are affected. |
| AffectsParent | False | Boolean | Can this warhead affect the actor that fired it. |
| AirThreshold | 0c128 | 1D World Distance | If impact is above this altitude, warheads that would affect terrain ignore terrain target types (and either do nothing or perform their own checks). |
| Delay | 0 | Integer | Delay in ticks before applying the warhead effect. 0 = instant (old model). |
| DebugOverlayColor | FF0000 | Color (RRGGBB[AA] notation) | The color used for this warhead's visualization in the world's `WarheadDebugOverlay` trait. |

### FireShrapnelWarhead

> Inherits from: `ValidateTriggerWarhead`.

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| Weapon | *(required)* | String | Has to be defined in weapons.yaml as well. |
| Amount | 1 | Collection of Integer | Amount of shrapnels thrown. |
| AimChance | 0 | Integer | The percentage of aiming this shrapnel to a suitable target actor. |
| AimTargetStances | Enemy, Neutral, Ally | [`PlayerRelationship`](#playerrelationship) | What diplomatic stances can be targeted by the shrapnel. |
| ThrowWithoutTarget | True | Boolean | Allow this shrapnel to be thrown randomly when no targets found. |
| AllowDirectHit | False | Boolean | Should the shrapnel hit the direct target? |
| AroundTarget | False | Boolean | Should the weapons be fired around the intended target or at the explosion's epicenter. |
| ValidTargets | Ground, Water | Collection of TargetableType | What types of targets are affected. |
| InvalidTargets |  | Collection of TargetableType | What types of targets are unaffected. Overrules ValidTargets. |
| ValidRelationships | Enemy, Neutral, Ally | [`PlayerRelationship`](#playerrelationship) | What player relationships are affected. |
| AffectsParent | False | Boolean | Can this warhead affect the actor that fired it. |
| AirThreshold | 0c128 | 1D World Distance | If impact is above this altitude, warheads that would affect terrain ignore terrain target types (and either do nothing or perform their own checks). |
| Delay | 0 | Integer | Delay in ticks before applying the warhead effect. 0 = instant (old model). |
| DebugOverlayColor | FF0000 | Color (RRGGBB[AA] notation) | The color used for this warhead's visualization in the world's `WarheadDebugOverlay` trait. |

### FlashPaletteEffectWarhead
**Used to trigger a FlashPaletteEffect trait on the world actor.**

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| FlashType |  | String | Corresponds to `Type` from `FlashPaletteEffect` on the world actor. |
| Duration | 0 | Integer | Duration of the flashing, measured in ticks. Set to -1 to default to the `Length` of the `FlashPaletteEffect`. |
| ValidTargets | Ground, Water | Collection of TargetableType | What types of targets are affected. |
| InvalidTargets |  | Collection of TargetableType | What types of targets are unaffected. Overrules ValidTargets. |
| ValidRelationships | Enemy, Neutral, Ally | [`PlayerRelationship`](#playerrelationship) | What player relationships are affected. |
| AffectsParent | False | Boolean | Can this warhead affect the actor that fired it. |
| AirThreshold | 0c128 | 1D World Distance | If impact is above this altitude, warheads that would affect terrain ignore terrain target types (and either do nothing or perform their own checks). |
| Delay | 0 | Integer | Delay in ticks before applying the warhead effect. 0 = instant (old model). |
| DebugOverlayColor | FF0000 | Color (RRGGBB[AA] notation) | The color used for this warhead's visualization in the world's `WarheadDebugOverlay` trait. |

### RobMoneyWarhead
**Steals money from the target's owner.**

> Inherits from: `ValidateTriggerWarhead`.

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| Amount | 0 | Integer | Amount to be taken away from the target. |
| PercentageGranted | 100 | Integer | Percentage of the taken money granted to the firer. |
| Range | 0c64 | 1D World Distance | Range of actors to be stolen from. |
| RobbedNotification |  | String | Sound the victim will hear when they get robbed. |
| RobbedTextNotification |  | String | Text notification the victim will see when they get robbed. |
| RobNotification |  | String | Sound the perpetrator will hear after successful leeching. |
| RobTextNotification |  | String | Text notification the perpetrator will see after successful leeching. |
| ShowTicks | True | Boolean | Whether to show a floating text. |
| ValidTargets | Ground, Water | Collection of TargetableType | What types of targets are affected. |
| InvalidTargets |  | Collection of TargetableType | What types of targets are unaffected. Overrules ValidTargets. |
| ValidRelationships | Enemy, Neutral, Ally | [`PlayerRelationship`](#playerrelationship) | What player relationships are affected. |
| AffectsParent | False | Boolean | Can this warhead affect the actor that fired it. |
| AirThreshold | 0c128 | 1D World Distance | If impact is above this altitude, warheads that would affect terrain ignore terrain target types (and either do nothing or perform their own checks). |
| Delay | 0 | Integer | Delay in ticks before applying the warhead effect. 0 = instant (old model). |
| DebugOverlayColor | FF0000 | Color (RRGGBB[AA] notation) | The color used for this warhead's visualization in the world's `WarheadDebugOverlay` trait. |

### TreeDamageWarhead
**A simplified SpreadDamageWarhead that interacts with ForestLayer**

> Inherits from: `DamageWarhead`.

| Property | Default Value | Type | Description |
| -------- | ------------- | ---- | ----------- |
| Spread | 0c43 | 1D World Distance | Range between falloff steps. |
| Falloff | 100, 37, 14, 5, 0 | Collection of Integer | Damage percentage at each range step |
| Damage | 0 | Integer | How much (raw) damage to deal. |
| DamageTypes |  | Collection of DamageType | Types of damage that this warhead causes. Leave empty for no damage types. |
| Versus |  | Dictionary with Key: String, Value: Integer | Damage percentage versus each armor type. |
| ValidTargets | Ground, Water | Collection of TargetableType | What types of targets are affected. |
| InvalidTargets |  | Collection of TargetableType | What types of targets are unaffected. Overrules ValidTargets. |
| ValidRelationships | Enemy, Neutral, Ally | [`PlayerRelationship`](#playerrelationship) | What player relationships are affected. |
| AffectsParent | False | Boolean | Can this warhead affect the actor that fired it. |
| AirThreshold | 0c128 | 1D World Distance | If impact is above this altitude, warheads that would affect terrain ignore terrain target types (and either do nothing or perform their own checks). |
| Delay | 0 | Integer | Delay in ticks before applying the warhead effect. 0 = instant (old model). |
| DebugOverlayColor | FF0000 | Color (RRGGBB[AA] notation) | The color used for this warhead's visualization in the world's `WarheadDebugOverlay` trait. |

# Related value types (enums):

### BeamRenderableShape
Possible values: `Cylindrical`, `Flat`

Referenced by: [`AreaBeam`](#areabeam), [`LaserZap`](#laserzap), [`Railgun`](#railgun)

### DamageCalculationType
Possible values: `HitShape`, `ClosestTargetablePosition`, `CenterPosition`

Referenced by: [`FlashTargetsInRadiusWarhead`](#flashtargetsinradiuswarhead), [`SpreadDamageWarhead`](#spreaddamagewarhead)

### InaccuracyType
Possible values: `Maximum`, `PerCellIncrement`, `Absolute`

Referenced by: [`AreaBeam`](#areabeam), [`Bullet`](#bullet), [`InstantHit`](#instanthit), [`InstantHitWithTracers`](#instanthitwithtracers), [`LaserZap`](#laserzap), [`Missile`](#missile), [`Railgun`](#railgun)

### PlayerRelationship
Possible values: `None`, `Enemy`, `Neutral`, `Ally`

Referenced by: [`Bullet`](#bullet), [`ChangeOwnerWarhead`](#changeownerwarhead), [`CreateEffectWarhead`](#createeffectwarhead), [`CreateResourceWarhead`](#createresourcewarhead), [`DestroyResourceWarhead`](#destroyresourcewarhead), [`FireClusterWarhead`](#fireclusterwarhead), [`FireRadiusWarhead`](#fireradiuswarhead), [`FireShrapnelWarhead`](#fireshrapnelwarhead), [`FlashEffectWarhead`](#flasheffectwarhead), [`FlashPaletteEffectWarhead`](#flashpaletteeffectwarhead), [`FlashTargetsInRadiusWarhead`](#flashtargetsinradiuswarhead), [`GrantExternalConditionWarhead`](#grantexternalconditionwarhead), [`HealthPercentageDamageWarhead`](#healthpercentagedamagewarhead), [`LeaveSmudgeWarhead`](#leavesmudgewarhead), [`RobMoneyWarhead`](#robmoneywarhead), [`ShakeScreenWarhead`](#shakescreenwarhead), [`SpreadDamageWarhead`](#spreaddamagewarhead), [`TargetDamageWarhead`](#targetdamagewarhead), [`TreeDamageWarhead`](#treedamagewarhead)

