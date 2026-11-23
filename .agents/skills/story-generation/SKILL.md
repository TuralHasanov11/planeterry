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
