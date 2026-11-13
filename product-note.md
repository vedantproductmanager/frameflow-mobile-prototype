# Frameflow — MVP product note

**Purpose:** Help a person turn one story brief into an ordered image sequence, preview it with optional audio, and export an MP4.

## Product promise

The user describes the full story and the moments they imagine in one go. Frameflow proposes a complete, numbered frame list that fits the chosen video length. The user reviews the prompts before images are generated, then keeps the prompts, image versions, audio choice and finished video together in one project.

## Main user flow

1. Create and name a project.
2. Write the story and the moments they picture in sequence. Choose a target length and default time per frame.
3. Generate one complete, flat frame list. Keep the story order. Review, edit, add, remove or reorder frames.
4. Approve the list to generate the first image for each frame.
5. Edit a frame prompt, browse its image history, select a version or regenerate that frame.
6. Preview the sequence and optionally add one soundtrack.
7. Render an MP4 in the cloud. Play it from the project; copy it to the phone only after an explicit download.

## Screens

| Screen | Purpose | Key content and actions |
|---|---|---|
| 1. Projects | Start, resume or reopen work | New project; project name; status; frame count; runtime; Watch video; View frames; restore recently deleted project |
| 2. Project brief | Capture the story once | Project name; story and intended moments; target length; default seconds per frame; build frame list |
| 3. Frame plan | Review the proposed sequence | One globally numbered list; prompt per frame; estimated runtime; edit, add, remove, reorder; approve |
| 4. Storyboard | Refine the images | Ordered frames; image and prompt; image history; select version; regenerate this frame; add a new frame |
| 5. Preview & sound | Check the flow | Ordered playback; timeline; add or remove one audio file; return to editing |
| 6. Export | Create the MP4 | Format, size, duration and audio; start or retry export |
| 7. Finished video | Watch and inspect the result | Cloud playback; project name; duration; frame count; soundtrack; Download; View frames; prior exports |

## Frame and image rules

- Keep the original story brief separate from the generated frame prompts.
- Use one continuous ordered list. Do not group frames into scenes or sub-scenes.
- Editing a prompt does not silently change its image. Regeneration makes a new image version for the same frame; it does not add a frame or replace the current selection.
- Adding a frame creates a new position with its own prompt and image history.
- Reordering updates the global order and frame times. Show the estimated total before image generation.
- A failed image can be retried without losing other completed images.

## Project and result

A project is the home for its story, frame order, prompts, image history, audio choice and exports. Its card shows the name, status, frame count and runtime. When the video is ready, the card offers **Watch video** and **View frames**. The result screen plays the video first, then shows the exact ordered frames used for that export. Keep earlier exports in project history.

## Media handling

- Keep project details in the app database and images, uploaded audio copies and MP4s in private cloud storage.
- Stream media for review. Do not intentionally store project media in the phone gallery, browser cache or offline storage.
- **Download** is the only product action that saves the finished MP4 to the device.
- Preserve the cloud project if playback or download fails. Explain retention and recovery before deleting a project.

## MVP assumptions

- Mobile-first responsive web app. Plan a later mobile app around the same project data and versioned API.
- One configured admin account for MVP. Keep project records ready for future user-level ownership; no public sign-up or social login yet.
- Default five seconds per frame, up to two minutes, 16:9 and 720p MP4. Confirm model and rendering limits before launch.
- One image generation provider at launch, replaceable behind a provider adapter.
- Static generated images only; no generated video clips or animation.
- One optional audio file. Trim longer audio to video length; shorter audio ends with silence.

## Errors and recovery

| Problem | Expected behavior |
|---|---|
| Name or story is missing | Keep the user on the brief, preserve text and show what is missing. |
| Frame plan fails or loses story order | Keep the source story and existing edits; offer retry and prompt editing. |
| Target and estimated length differ | Show the updated runtime; let the user change length, frame count or frame duration before approval. |
| A frame prompt is blank | Point to that frame and block approval until it is fixed. |
| Image generation fails | Keep successful images and prior selections; retry only the failed frame. |
| Prompt changes after image generation | Keep the current image and say it was made from the earlier prompt. |
| Audio is unsupported or upload is interrupted | Explain the supported file limits; retry or remove audio. |
| Preview, export or download fails | Preserve project state, offer retry and keep earlier exports available. |

## Mobile design rules

- Design for 320 px wide phones first. Let labels wrap and allow vertical scrolling.
- Use a steady 4/8/12/16/24 px spacing scale; align content to shared edges.
- Give touch actions at least 44 px targets.
- Check at 320, 375 and 430 px widths for clipping, overlap and uneven gaps.

## MVP measures and decisions

Measure story-to-approved-plan completion, time to first preview, successful export rate, retries by stage, and use of Watch, Download and View frames. Confirm supported audio formats and size, frame limits, cloud retention, model/data terms and any user-visible generation or export cost.
