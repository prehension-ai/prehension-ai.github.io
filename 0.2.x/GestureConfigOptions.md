---
title: Gesture Config Options
nav_order: 5
version: 0.2.x
---

# Gesture Config Options

Within each gesture in the Prehension Config are a number of options intended to allow you to customize the behavior of the gesture recognition algorithm:

**Handedness**: Whether the gesture is for the left hand or right hand. This setting also controls which hand is captured at recording time.

**Active**: Whether or not this is checked at training time controls whether or not samples are included in the model. This is also checked at runtime for the gesture recognition algorithm to know which gestures the model is working with. Note that desync between the two (for example, a model trained on 3 gestures with a config that says 4 are active) will cause issues at runtime.

**Rapid re-fire**: Checking this box will allow gestures to fire repeatedly without any reset. Normally the gesture recognition algorithm looks for a few frames ('cooldown frames' in the Prehension Manager prefab inspector) of null movement in between successive gestures of the same type, but turning this setting on bypasses that check.

**Fire and Hold**: Checking this box denotes a gesture that you expect the player to begin, and then hold in some position for an indefinite amount of time. Specifically, in addition to the normal OnGestureCandidate and OnGestureRecognized callbacks, you will also get an OnGestureReleased when the player stops holding the gesture.

**Build Frames Override**: The gesture recognition algorithm looks for a certain number of frames in a row before it fires a recognition event (tunable in the PrehensionManager prefab). Setting this on a particular gesture will override that number for that gesture only. Use it to make certain gestures more or less twitchy, depending on your needs.

**Mirror Data From**: Setting this option will take all the samples from an opposite hand gesture and copy them over (at training time), mirrored across the body. You can also add samples on top of that, but you don't have to. Think of this as a quick shortcut to enable you to train gestures for one hand and get the same thing for the other. Note that the mirroring is a 'dumb' x axis flip, so if your gesture has some notion of left or right encoded this may not give you the expected results. For example: mirroring 'thumbs up' will work as you probably intend, but 'swipe left' will turn into 'swipe right'.

**Opposite**: Opposite gestures (e.g. 'swipe left' and 'swipe right') tend to be more difficult for the model distinguish properly, largely because players tend to perform one as a 'wind-up' or preparation for the other. Setting this helps the model distinguish between actual gesture and preparation or return to neutral for those types of motions.