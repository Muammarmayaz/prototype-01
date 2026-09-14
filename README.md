# Prototype 01 — Top-down arena

Unity 6.3 LTS · C# · URP

First prototype in a 14-week game dev roadmap.

## Systems
- WASD movement, frame-rate independent
- Camera follow (LateUpdate to avoid one-frame lag)
- Enemy chase via vector subtraction + normalisation
- Click to shoot, prefab instantiation with lifetime cleanup
- Death trigger on contact

## The design decision
The bullet doesn't know what it hit. It checks for `IDamageable`
and calls `TakeDamage()`. Any object can implement the interface
and define what damage means for itself — the bullet never changes.

See `Assets/Scripts/Bullet.cs` and `IDamageable.cs`.

