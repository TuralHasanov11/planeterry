---
name: story-generation
description: Act as a professional animation storyboard artist. Generate scenes for the following story titled "[Story Title]"
---
For every scene return:

- Scene number
- Duration
- Character descriptions
- Character actions
- Facial expressions
- Camera angle
- Camera movement
- Environment
- Lighting
- Narration
- Sound effects
- Image generation prompt
- Video generation prompt

Maintain strict character consistency based on [character bibles](..\..\..\docs\characters).

Use the provided character reference descriptions for every scene.

I recommend generating scripts with approximately 60–75 spoken words for a 30-second video, then timing the narration rather than relying on word count alone.

Refer to our [business-overview.md](..\..\..\docs\business-overview.md), [channel-positioning.md](..\..\..\docs\channel-positioning.md), [character bible files](..\..\..\docs\characters) and [world building images](..\..\..\docs\world-building) for more insights.

Store the results under  [/docs/episodes/episode{xxx}](..\..\..\docs\episodes\episode{xxx}) folder as scenes.md file, but ask me the number first. I would either tell you  create a new episode or update the existing episode.

Example episode story:

```
# Robo, You're Watering the Wrong Thing!

**Total duration:** 30 seconds  
**Scenes:** 6  
**Format:** YouTube Short

## Scene 1 — Max Makes a Request (0–5 seconds)

**Characters:** Max, Robo

In a bright garden, Max stands beside a small flower and asks Robo to give it a little water. Robo turns toward Max, ready to help.

**Dialogue**
- **Max:** "Robo, could you give this flower a little water?"

## Scene 2 — Robo Gets to Work (5–10 seconds)

**Characters:** Robo

Robo picks up a blue watering can. He studies the area with a serious, focused expression, as if scanning for the correct target.

**Dialogue**
- **Robo:** "Affirmative! Locating thirsty target..."

## Scene 3 — The Wrong Target (10–15 seconds)

**Characters:** Robo

Robo confidently tilts the watering can in the wrong direction and pours water over his own head and body. The flower remains completely dry. Water splashes harmlessly over Robo.

**Dialogue**
- **Robo:** "Target found. Beginning hydration!"

## Scene 4 — A Helpful Correction (15–20 seconds)

**Characters:** Max, Luna, Robo

Max points toward Robo in surprise. Luna calmly points toward the flower, helping Robo understand where the water should go.

**Dialogue**
- **Max:** "Robo! You're watering the wrong thing!"
- **Luna:** "The flower is over there!"

## Scene 5 — Robo Understands (20–25 seconds)

**Characters:** Max, Robo

Robo looks down at his wet body. One of his digital eyes becomes a spiral while the other remains round, showing his confusion. Max gestures toward the flower and shows Robo which way to point the watering can.

**Dialogue**
- **Robo:** "Oh! My sensors selected... me?"
- **Max:** "Beep boop! Try the spout this way!"

## Scene 6 — Mission Accomplished (25–30 seconds)

**Characters:** Max, Luna, Robo

Robo turns the watering can toward the flower and waters it correctly. The flower gets a gentle splash. Max and Luna smile and celebrate with him. Robo looks pleased with his successful correction.

**Dialogue**
- **Robo:** "System update: flowers need water too!"
- **Luna:** "A little for the flower, please!"
- **Max:** "Much better!"
```