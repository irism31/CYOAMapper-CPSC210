# My Personal Project

## A "Choose Your Own Adventure" Novel

A "choose your own adventure" (CYOA) novel is an interactive story where the reader jumps to certain pages in a book depending on the choice they want to make. For example:

> The path splits ahead. The left leads to a forest, rumoured to be the home of a river spirit. The right leads to open plains, where you might be able to find more foodstuff to replenish your rations.
> - Go left *(Go to page 3)*
> - Go right *(Go to page 4)*

There may even be certain conditions that need to have been met before a choice can be made.

>There's a locked door in front of you.
>- Pick the lock *(Required item: lockpick. Then, go to page 34)*
>- Break it down *(Required stat: strength 3. Then, go to page 25)*
>- Find another way *(Go to page 13)*

The application will allow the user to make their own digital CYOA novel using "story cards". Story cards will display the written scene and choices can be made by pressing a button. These buttons will link to other story cards to a longer narrative. This project is of interest to me because I quite enjoy these novels and want to make it easier to make one. This application can not only be used by people who wish to write a CYOA novel, but can also be used by anyone who wants to make a choice-based story such as a Dungeons & Dragons campaign.

## User Stories
- As a user, I want to be able to make a story card and add it to a collection of story cards
- As a user, I want to be able to view a list of the story cards in a collection
- As a user, I want to be able to remove a story card from from the collection it is in
- As a user, I want to be able to be able to edit the story cards I have already made in a collection
- As a user, I want to be able to have the option to save a created story to file
- As a user, I want to be able to have the option to load a created story from file

# Instructions for End User

- You can view the panel that displays the cards that have already been added to the story by clicking any of the following   buttons inside the Story Editor Menu:
    - "Remove a story card"
    - "Edit a story card"
    - "Set a start card"
    
    A drop-down menu will appear with the names of all story cards currently in the story.
- You can generate the first required action related to the user story "adding multiple cards to a story" by clicking on the button "Add a new story card" inside the Story Editor Menu, then filling in the text fields. This will create a new card and add it to the story.
- You can generate the second required action related to the user story "adding multiple cards to a story" by clicking on the button "Remove a story card" inside the Story Editor Menu, then filling in the text fields. This will remove the specified card that has been added to the story.
- You can locate my visual component by launching the app from main. A splash window with an image will appear for a couple seconds before it is replaced by the GUI.
- You can save the state of my application by clicking on the button "Save a story to file" in the Start Menu, then filling in the text field with the name of the story you want to save. This will write the story to file in the data folder.
- You can reload the state of my application by clicking on the button "Load a story from file" in the Start Menu, then filling in the text field with the name of the story you want to load. If a JSON file with the corresponding name is found, the story will be loaded into the app.

# Phase 4: Task 2

A sample of the events that occur when this program is run is provided below:

>Thu Mar 26 01:42:19 PDT 2026
testWriterGeneralStory loaded from file.
>
>Thu Mar 26 01:42:29 PDT 2026
SpecialBook loaded from file.
>
>Thu Mar 26 01:42:43 PDT 2026
>Card1 story card added.
>
>Thu Mar 26 01:42:54 PDT 2026
>Card2 story card added.
>
>Thu Mar 26 01:42:58 PDT 2026
>Card1 story card removed.
>
>Thu Mar 26 01:43:05 PDT 2026
>Card1 story card added.
>
>Thu Mar 26 01:43:12 PDT 2026
>SpecialBook title was changed to VerySpecialBook
>
>Thu Mar 26 01:43:18 PDT 2026
>Card1 set as starting card for VerySpecialBook.
>
>Thu Mar 26 01:43:29 PDT 2026
>Choice Go to card 2 added in Card1 story card
>
>Thu Mar 26 01:43:34 PDT 2026
>Card1 story card was changed to Start  
>
>Thu Mar 26 01:43:37 PDT 2026
>Start story card's text was edited.
>
>Thu Mar 26 01:43:40 PDT 2026
>Choice test added in Start story card 
>
>Thu Mar 26 01:43:45 PDT 2026
>Choice test removed from Start story card  
>
>Thu Mar 26 01:43:56 PDT 2026
>Choice Go to card 2 changed to Run to card 2!
>
>Thu Mar 26 01:43:59 PDT 2026
>Choice Run to card 2! linked to Card2 story card
>
>Thu Mar 26 01:44:10 PDT 2026
>VerySpecialBook saved to file.

# Phase 4: Task 3

If I had more time to work on this project, I would change how the different menus are implemented. All four menus share very similar code for methods that do the same thing to different types of objects, so I would create an abstract class for a general menu with a shared constructor for the StoryAppGUI field, and any concrete/abstract methods as needed. The four menus would then extend the abstract class and overwrite methods as needed. This should reduce a significant amount of duplicate code in the final version.

Another refactoring decision I would make is to add more helper functions. For example, in the Story class there is a common for-loop to find a story card in 4 different methods. That loop can be extracted and turned into a helper method. Any changes to the program would only require editing the helper method instead of all 4 methods, following the single point of control principle. Another instance of where a helper method would be useful is in the construction of the menus. A helper method that handles creating a button, attaching a listener, and adding it to the layout would further increase cohesion.

