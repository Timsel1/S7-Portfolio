# Continuation of Secrets of Ignacios
If there ever will be people continuing to work on/modifying Secrets of Ignacios, this document will provide some technical as well as design advice to improve their experience.

## Design

### Gestures
As you work on designing gestures, it’s important to keep inclusivity in mind. Testing with players of different ages can reveal how hand shapes and mobility vary. Some gestures might feel more natural to those with thinner, longer fingers, while others might struggle with shorter, stubbier hands. To ensure that your gestures are universally recognizable, aim for designs that can work across different hand types. This will allow a wider range of players to engage seamlessly with your spellcasting system. I have personally experienced this during the development of Secrets of Ignacios. At the start I was in charge of creating gestures we could use to control the game and cast spells, during this time I have created many gestures only I was able to perform. So make sure to keep testing.

### Sequences
When creating gesture sequences, avoid making them purely random. Players will find it harder to remember sequences that lack logic. Instead, design sequences with a clear progression, for Secrets of Ignacios we created a system which starts with a base gesture, followed by an element selection, and finally choosing the type of spell. This method creates more intuitive and meaningful combinations that are easier for players to recall and execute. This will also add progression for the player to the newly learned sequences and could create the possibility for the player to guess new spells based on gestures they already know if you give them the ability to do so.

## Technical

### Code Convention
One of the keys to maintaining a clean and efficient project is adhering to a consistent code convention. Without it, the codebase can quickly become chaotic, filled with inconsistent naming and structure. It’s easy to overlook this in, but it pays to implement clear conventions from the start. if you’re continuing with the existing project, I would recommend to follow the existing convention, this way no refactoring is needed. If you're starting fresh, make sure to establish a code structure that everyone can follow. A well organized codebase will save countless hours in debugging and future enhancements. But even with your convention in place make sure to review eachothers code before merging anything, I have seen some bad habits come to light during my time of working on Secrets of Ignacios (don't name properties with snake case or just one letter out of nowhere). 

### Gesture Recognition
When selecting a gesture recognition system, choose the one which you think fits your project the best. Many packages can only recognise static gestures, these packages won't suffice for a game or system which needs to recognise movement/dynamic gestures. In this case, you may need to develop your own solution. I’ve done some research on gesture packages, which can be found [here](../../1.%20Blast%20and%20Search/1.%20Research/1.%20Gesture%20Package.md). I have also tried to create my own dynamic recognition system which can be found [here](../../3.%20Deep%20Dive/1.%20Research/1.%20Dynamic%20Movement%20Detection.md). You can use these documents to help make the right choice for your project or improve upon my dynamic recognition system ideas. 

### Sequence System
The sequence system is a core part of the spellcasting mechanic in Secrets of Ignacios, so it’s crucial to have a clear understanding of its purpose from the start. It’s easy to be tempted to change things up, but doing so can lead to complications since other systems depend on it (like the vfx systems). We ran into this issue when someone wanted to introduce late changes to the sequence system, which wasn’t problematic in itself. The real issue arose from the ripple effect it had on other systems that relied on the original “start, element, type” structure. Make sure to build a system that can’t be easily disrupted by late adjustments save yourself from unnecessary redesigns. 
