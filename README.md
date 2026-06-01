# Playlist Chaos

Your AI assistant tried to build a smart playlist generator. The app runs, but some of the behavior is unpredictable. Your task is to explore the app, investigate the code, and use an AI assistant to debug and improve it.

This activity is your first chance to practice AI-assisted debugging on a codebase that is slightly messy, slightly mysterious, and intentionally imperfect.

You do not need to understand everything at once. Approach the app as a curious investigator, work with an AI assistant to explain what you find, and make targeted improvements.

---

## How the code is organized

### `app.py`  

The Streamlit user interface. It handles things like:

- Showing and updating the mood profile  
- Adding songs  
- Displaying playlists  
- Lucky pick  
- Stats and history

### `playlist_logic.py`  

The logic behind the app, including:

- Normalizing and classifying songs  
- Building playlists  
- Merging playlist data  
- Searching  
- Computing statistics  
- Lucky pick mechanics

You will need to look at both files to understand how the app behaves.

---

## What you will do

### 1. Explore the app  

Run the app and try things out:

- Add several songs with different titles, artists, genres, and energy levels  
- Change the mood profile  
- Use the search box  
- Try the lucky pick  
- Inspect the playlist tabs and stats  
- Look at the history  

As you explore, write down at least five things that feel confusing, inconsistent, or strange. These might be bugs, quirks, or unexpected design decisions.

### 2. Ask AI for help understanding the code  

Pick one issue from your list. Use an AI coding assistant to:

- Explain the relevant code sections  
- Walk through what the code is supposed to do  
- Suggest reasons the behavior might not match expectations  

For example:

> "Here is the function that classifies songs. The app is mislabeling some songs. Help me understand what the function is doing and where the logic might need adjustment."

Before making changes, summarize in your own words what you think is happening.

### 3. Fix at least four issues  

Make improvements based on your investigation.

For each fix:

- Identify the source of the issue  
- Decide whether to accept or adjust the AI assistant's suggestions  
- Update the code  
- Add a short comment describing the fix  

Your fixes may involve logic, calculations, search behavior, playlist grouping, lucky pick behavior, or anything else you discover.

### 4. Test your changes  

After each fix, try interacting with the app again:

- Add new songs  
- Change the profile  
- Try search and stats  
- Check whether playlists behave more consistently  

Confirm that the behavior matches your expectations.

### 5. Optional stretch goals  

If you finish early or want an extra challenge, try one of these:

- Improve search behavior  
- Add a "Recently added" view  
- Add sorting controls  
- Improve how Mixed songs are handled  
- Add new features to the history view  
- Introduce better error handling for empty playlists  
- Add a new playlist category of your own design  

---

## Tips for success

- You do not need to solve everything. Focus on exploring and learning.  
- When confused, ask an AI assistant to explain the code or summarize behavior.  
- Test the app often. Small experiments reveal useful clues.  
- Treat surprising behavior as something worth investigating.  
- Stay curious. The unpredictability is intentional and part of the experience.

When you finish, Playlist Chaos will feel more predictable, and you will have taken your first steps into AI-assisted debugging.
---

## Fixes Completed

For this lab, I used the intended behavior from the Playlist Chaos assignment as my guide. I focused on making the app more predictable by improving playlist classification, search behavior, playlist statistics, Lucky Pick behavior, and input normalization.

### 1. Song Classification Fix

One issue I noticed was that some songs were being placed into the wrong playlist. The intended behavior is that Hype songs should be based on high energy, favorite genre, or hype-related genre keywords, while Chill songs should be based on low energy or chill-related title keywords.

I updated the playlist classification logic so that songs are categorized more consistently into Hype, Chill, or Mixed. This helped make the playlist results match the expected behavior more closely.

### 2. Search Functionality Fix

The search feature was unreliable because searches did not always match songs the way a user would expect. I improved the search behavior so that it handles text more consistently and supports case-insensitive partial matches.

For example, a user should be able to search using part of a title, artist, or genre without needing the exact capitalization.

### 3. Playlist Statistics Fix

The playlist statistics were not always accurate. In particular, the total song count, average energy, and hype ratio needed to reflect the actual songs in the app.

I updated the stats logic so that:
- Total songs represents the unique count of songs.
- Average energy is calculated across all songs.
- Hype ratio is calculated as the number of Hype songs divided by the total number of songs.

This makes the stats easier to trust and compare with what appears in the playlists.

### 4. Lucky Pick Fix

The Lucky Pick feature could behave incorrectly when choosing songs from a selected playlist. I updated the logic so that selecting Hype or Chill only chooses from that specific playlist.

I also made the “Any” option pull from a combined group of available playlists so that it behaves more like a general random pick.

### 5. Data Normalization Improvement

I also improved how user input is handled. Titles, artists, and genres are normalized by trimming extra whitespace and handling capitalization consistently. This helps prevent duplicate or mismatched entries caused by small formatting differences.

## Refactor

After fixing the bugs, I refactored part of the code to make it easier to read and maintain. The goal of the refactor was not to change the app’s behavior, but to make the logic clearer and easier to follow.

This matched the lab requirement that a refactor should preserve behavior while improving code structure.

## Testing

After each fix, I tested the app by running it in Streamlit and trying different user actions, including:

- Adding songs with different titles, artists, genres, and energy levels
- Checking whether songs appeared in the correct Hype, Chill, or Mixed playlist
- Searching with different capitalization and partial words
- Testing Lucky Pick with Hype, Chill, and Any
- Comparing the playlist statistics with the visible songs

These tests helped confirm that the app behaved more consistently after the changes.

## AI Debugging Reflection

AI was helpful for explaining what different functions were doing and for suggesting possible causes of bugs. However, I still had to compare the AI’s suggestions with the assignment requirements and test the app myself.

One thing I learned is that AI can give confident answers that are not always fully correct, especially for edge cases. The most useful strategy was to describe what I expected, what actually happened, and which part of the code seemed related.

Overall, I used AI as a debugging partner, but I verified the fixes through my own testing.

## Summary 

Students should be able to understand the differences between syntax vs logic vs control problem. Each are unique, in how they show up in error messages and app behavior. They are most likely to struggle when their codes are able to run but their is logic and algorithm mistakes. Also, their tools may fail if their enviornment is not set up correctly (e.g. missing packages or git push/pull conflicts). AI was the most helpful when looking for error messages and suggesting fixes for dependencies/Git workflow (especially helpful because of it beoong pattern based and concrete). It may be misleading when it skips certain edge cases and does not match the question the assignment is asking. It always good to double check and verify. As a TF, one was I would guide the student without giving the direct answer would to first ask the student to give an example of what they think the app/code should do given the prompt. I would tell them to create a smaller test case to pinpoint how exactly to create/fix code. Then, I would ask them to use AI as a partner to explain the funcationality of the code in a conceptual way rather than giving the straight code. I also would remind them that AI is being presented as a helper and is not also guranteed to give the right answer. It is helpful to keep this in mind, especially using AI because it may not always be correct. 