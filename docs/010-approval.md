# Human approval system

### Approval sequence

1. Stage 1. Script approval. You receive the proposed title, script, educational objective, and storyboard summary.
2. Stage 2. Visual approval. You receive the scene previews and generated character animations.
3. Stage 3. Final video approval. You receive the rendered MP4, audio, captions, and proposed metadata.
4. Stage 4. Publishing authorization. You approve the platforms and publication date. The publishing workflow can now proceed.

Use a database state machine:

```
IDEA_CREATED
     |
SCRIPT_GENERATED
     |
AWAITING_SCRIPT_APPROVAL
     |
SCRIPT_APPROVED
     |
ASSETS_GENERATED
     |
AWAITING_VISUAL_APPROVAL
     |
VISUALS_APPROVED
     |
VIDEO_RENDERED
     |
AWAITING_FINAL_APPROVAL
     |
VIDEO_APPROVED
     |
SCHEDULED
     |
PUBLISHED
```

Additional states:

```
REJECTED
FAILED
NEEDS_REVISION
CANCELLED
```

Every approval should store:

- User/action identifier.
- Timestamp.
- Version number.
- Decision.
- Optional revision notes.
