# Model Tuning

While the model and recognition algorithm can get a lot just from the samples you record and upload, there are a few things you can do to help it produce the desired output.

### Specifying Opposite Gestures

Each gesture in your config has an optional ‘Opposite Gesture’ field. This is for specifying gestures that tend to contain opposing movements and helping the model disambiguate between them.

We find that opposing sets of gestures are 1) common and 2) very easily confused. Consider, for example, ‘swipe left’ and ‘swipe right’: it would make plenty of sense for both to be included in the interface design for an application, but most end-users tend to perform both in the same movement. While swiping left, they might move from a neutral position to a rightward position, through the swipe, and then back to neutral. Both the initial setup and the return to neutral are likely to be recognized as a ‘swipe right’, since they are rightward movement. Marking gestures as opposites helps the model distinguish and correctly identify these motions.