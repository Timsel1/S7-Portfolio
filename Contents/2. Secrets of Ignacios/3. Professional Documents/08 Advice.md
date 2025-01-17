# Continuation of Secrets of Ignacios
If there ever will be people continuing to work on/modifying Secrets of Ignacios, this document will provide some technical as well as design advice to improve their experience.

## Design

### Gestures

As you work on designing gestures, it’s important to keep inclusivity in mind. Testing with players of different ages can reveal how hand shapes and mobility vary. Some gestures might feel more natural to those with thinner, longer fingers, while others might struggle with shorter, stubbier hands. To ensure that your gestures are universally recognizable, aim for designs that can work across different hand types. This will allow a wider range of players to engage seamlessly with your spellcasting system.

### Sequences

When creating gesture sequences, avoid making them purely random. Players will find it harder to remember sequences that lack logic. Instead, design sequences with a clear progression—perhaps starting with a base gesture, followed by an element selection, and finally choosing the type of spell. This method creates more intuitive and meaningful combinations that are easier for players to recall and execute.

## Technical

### Code Convention

One of the keys to maintaining a clean and efficient project is adhering to a consistent code convention. Without it, the codebase can quickly become chaotic, filled with inconsistent naming and structure. It’s easy to overlook this in the excitement of development, but it pays to implement clear conventions from the start. Whether you’re continuing with the existing project or starting fresh, make sure to establish a code structure that everyone can follow. A well-organized codebase will save countless hours in debugging and future enhancements.

### Gesture Recognition

When selecting a gesture recognition system, choose carefully. Many packages focus only on single-handed gestures, which won’t work if you need something more robust—like a system that recognizes two-handed gestures. In this case, you may need to develop your own solution. I’ve done some research on gesture packages, and it might be helpful to review those findings to make the right choice for your system’s needs.

### Sequence System

The sequence system is a core part of the spellcasting mechanic, so it’s crucial to have a clear understanding of its purpose from the start. It’s easy to be tempted to change things up later, but doing so can lead to complications if other systems depend on it. We ran into this issue when someone wanted to introduce late changes to the sequence system, which wasn’t problematic in itself. The real issue arose from the ripple effect it had on other systems that relied on the original “start, element, type” structure. Make sure to build a system that can’t be easily disrupted by late adjustments—save yourself from unnecessary redesigns.
