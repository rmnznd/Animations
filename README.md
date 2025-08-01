SwiftUI Animations
This project showcases a simple SwiftUI view (ContentView) that demonstrates text animation and user interaction through gestures.

Features
Animated Text: The phrase "Hello SwiftUI" is displayed, with each letter animated individually.

Color Change: The background color of each letter changes between blue and red based on a toggle.

Drag Gesture Interaction:

Dragging any part of the text moves all letters together.

Releasing the drag causes the letters to snap back to their original position and toggles their background color.

Staggered Animation: Each letter's animation is slightly delayed, creating a smooth, staggered effect when dragged.

How It Works
The ContentView uses an HStack to display individual Text views for each letter of "Hello SwiftUI".

@State private var enabled: A boolean that controls the background color of the letters.

@State private var dragAmount: A CGSize that stores the translation amount from the DragGesture, used to offset the letters.

ForEach: Iterates through the letters, applying padding, font styling, and background color.

.offset(dragAmount): Applies the current drag translation to each letter.

.animation(.linear.delay(Double(num) / 20), value: dragAmount): This is the core of the staggered animation. It applies a linear animation to the offset property, with a delay that increases for each subsequent letter.

DragGesture(): Detects drag movements.

.onChanged: Updates dragAmount as the user drags.

.onEnded: Resets dragAmount to zero (snapping back) and toggles the enabled state.

Usage
Open this code in Xcode.

Run the ContentView on a simulator or device.

Tap and drag the "Hello SwiftUI" text around the screen.

Release the drag to see the text snap back and change color.

Requirements
iOS 17.0+

Xcode 15.0+

Swift 5.9+
