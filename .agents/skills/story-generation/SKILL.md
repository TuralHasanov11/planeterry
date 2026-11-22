---
name: story-generation
description: Act as a professional animation storyboard artist. Convert the following story titled "[Story Title]" into a 30-second vertical animated video.
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

Maintain strict character consistency based on [character bibles](eterry\docs\characters).

Use the provided character reference descriptions for every scene.

I recommend generating scripts with approximately 60–75 spoken words for a 30-second video, then timing the narration rather than relying on word count alone.

Read our docs to get more insights about our YouTube channel and our project ([/docs](/docs)).

Video response:

```JSON
{
  "title": "Max and the Mystery Box",
  "duration": 30,
  "format": "9:16",
  "scenes": [
    {
      "scene_number": 1,
      "duration": 5,
      "characters": ["max"],
      "location": "colorful garden",
      "action": "Max discovers a mysterious box",
      "expression": "surprised",
      "camera": "medium shot",
      "narration": "Whoa! What is inside this box?",
      "image_prompt": "...",
      "video_prompt": "...",
      "sound_effects": ["soft magical sound"]
    }
  ]
}
```
