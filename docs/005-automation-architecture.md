
# Automation architecture



## Recommended technical stack

| Component         | Technology                          |
| ----------------- | ----------------------------------- |
| Orchestration     | n8n and Microsoft Agent Framework  |
| Script generation | OpenAI API                          |
| Image generation  | Mid Journey / Nano Banana / ComfyUI |
| Video generation  | Kling / Veo / OpenArt              |
| Voice generation  | ElevenLabs API                      |
| Video assembly    | CapCut / FFmpeg                     |
| Metadata storage  | PostgreSQL                          |
| File storage      | Cloudinary                          |
| Job scheduling    | n8n / .NET Hangfire                 |
| Publishing        | YouTube Data API                    |
| Analytics         | YouTube Analytics API               |
| Monitoring        | Telegram Bot                        |



```
                 CONTENT IDEATION
                       |
                       v
              Generate story ideas
                       |
                       v
                Script generation
                       |
                       v
              Script quality review
                       |
                       v
                Storyboard JSON
                       |
                       v
              Character references
                       |
                       v
              Generate scene images
                       |
                       v
              Generate video clips
                       |
                       v
                Generate voices
                       |
                       v
                 FFmpeg assembly
                       |
                       v
                 Quality review
                       |
                 Human approval
                       |
                       v
                Publishing queue
                  /     |      \
                 v      v       v
              YouTube Instagram TikTok
                 |
                 v
               Analytics
                 |
                 v
          Improve future scripts
```


## Workflows

### Workflow A - Content idea generation

1. Trigger every Monday.
2. Ask an LLM to generate 20 original children's story ideas.
3. Categorize ideas into education, comedy, and storytelling.
4. Check for duplicate ideas against PostgreSQL.
5. Save the approved candidates.

### Workflow B - Video generation

1. Select an approved idea.
2. Generate script and scene descriptions.
3. Generate image references.
4. Generate video clips.
5. Generate voiceovers.
6. Assemble the video with FFmpeg.
7. Store the result in Cloudinary.
8. Notify you through Telegram.

### Workflow C - Publishing

1. Read the approved video from the queue.
2. Generate title and description.
3. Upload to YouTube.
4. Schedule publication.
5. Save the video ID.
6. Notify you when publishing succeeds.



## Folder Structure

```
/prompts
    /ideation
        educational-ideas.md
        funny-stories.md
        adventure-stories.md

    /scripts
        30-second-story.md
        educational-short.md
        interactive-quiz.md

    /characters
        character-creation.md
        character-consistency.md
        facial-expressions.md

    /video
        image-to-video.md
        character-animation.md
        camera-movement.md

    /quality
        script-review.md
        visual-review.md
        child-safety-review.md
```


Example Prompts
