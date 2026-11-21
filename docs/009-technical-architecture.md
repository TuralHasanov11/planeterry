# Technical Architecture



### n8n vs .NET

#### Responsibility boundaries

| Responsibility                     | n8n | .NET |
| ---------------------------------- | --- | ---- |
| Weekly episode scheduling          | x   |      |
| Triggering a new episode           | x   |      |
| Selecting an episode series        |     | x    |
| Creative AI agents                 |     | x    |
| Script and scene validation        |     | x    |
| Telegram approval messages         | x   |      |
| Approval workflow branching        | x   |      |
| Persisting approval decisions      |     | x    |
| Calling image/video/TTS providers  | x   | x    |
| Character consistency rules        |     | x    |
| FFmpeg rendering                   |     | x    |
| Technical video validation         |     | x    |
| YouTube upload and scheduling      | x   | x    |
| Collecting analytics               | x   |      |
| Business analytics and reporting   | x   | x    |
| Error notifications and escalation | x   |      |

Some capabilities deliberately overlap at the integration boundary. For example, n8n can invoke a provider directly for a simple integration, but the .NET application should own provider-specific functionality when it depends on WonderPals domain rules, character references, asset records or reproducibility.

#### The n8n workflows

Instead of one enormous workflow, split automation into independent workflows. This makes failures easier to diagnose and lets you rerun individual stages.


##### Workflow 1 - Episode planning


Scheduled

1. Schedule Trigger (e.g. Monday morning)
2. HTTP Request → .NET /api/episodes/generate
3. .NET runs Creative Director, Scriptwriter and Quality Reviewer
4. Save the episode and script
5. Send script to Telegram for approval
6. Wait for approval or revision

##### Workflow 2 - Script approval

Telegram

1. Receive approval decision
2. Call .NET /api/approvals/{id}/decision
3. Check the result
4. Approved → start visual production
5. Revision → send notes back to .NET and request another script version
6. Rejected → close the episode

##### Workflow 3 - Visual production

Production

1. Call .NET to generate scene images
2. Wait/poll for generation completion
3. Send image previews to Telegram
4. Wait for approval
5. Approved → start animation and voice generation
6. Rejected → regenerate selected scenes

##### Workflow 4 - Video production


Production

1. Request video clips and narration from .NET
2. Wait for all provider jobs to finish
3. Request FFmpeg rendering
4. Poll for render completion
5. Send final MP4 to Telegram

##### Workflow 5 - Final approval and publishing


Human approval required

1. Receive final approval
2. Call .NET to record approval
3. Upload through YouTube integration or .NET publisher
4. Set Made for Kids metadata where applicable
5. Schedule or publish
6. Save the YouTube video ID

##### Workflow 6 - Analytics and reporting

Recurring

1. Daily or weekly schedule
2. Retrieve YouTube Analytics
3. Send metrics to .NET or store a snapshot
4. Generate a performance summary
5. Send a Telegram report
