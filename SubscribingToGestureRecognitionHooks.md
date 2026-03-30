# Subscribing to Gesture Recognition Hooks

Author: Alex Bertrand
Status: Draft
Last edited time: March 30, 2026 1:15 PM

There are two main hooks you can subscribe to for information on gesture-related events: 

**Gesture Recognized:**

```csharp
public void SubscribeToGestureRecognized(OnGestureRecognized func)

// Example
public void NewGestureRecognized(string gestureName)
{
		Debug.Log($"Gesture {gestureName} was recognized!");
}

public PrehensionManager prehension;
prehension.SubscribeToGestureRecognized(NewGestureRecognized);
```

A function subscribed this way will be called any time the model has identified a gesture as having been performed.

**New Gesture Candidate**

```csharp
public void SubscribeToGestureCandidate(OnGestureCandidate func)

// Example
public void NewGestureCandidate(string gestureName)
{
		Debug.Log($"Gesture {gestureName} is now a candidate gesture");
}

public PrehensionManager prehension;
prehension.SubscribeToGestureCandidate(NewGestureCandidate);
```

A function subscribed this way will be called whenever the model recognizes a new gesture candidate. Internally, the model outputs a ‘most likely gesture’ at every frame. When that gesture switches (say from ‘User likely doing nothing’ to ‘User likely swiping right’) a new candidate gesture is registered (in this case ‘Swipe Right’). If the model continues to say the user is likely performing that gesture, it will eventually be fully recognized and the OnGestureRecognized event will fire.

This is useful for looking back in time to when a gesture started, for example when determining what a user was pointing at with their hand *before* they started swiping right.