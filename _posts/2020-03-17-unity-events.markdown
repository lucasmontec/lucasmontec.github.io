---
layout: post
title:  "Unity Events"
date:   2020-01-20
categories: Unity
excerpt_separator: <!--more-->
---

[WIP: This article is not ready. Last update was >1 year ago.]

# Events, events events everywhere

Today while implementing thousands of unity events I noticed some practices and tips that I thought would be nice to share. Events are a very important subject, they are a very important way of communication between classes. Because of that I decided we need to talk about events.
<!--more-->

## The default way of communication

Events are a way of solving communication, but what is communication you ask? Classes are not people, they don't talk... or do they? You might ask. But hold onto your butts, I'm about to shake your world. 
Classes do communicate! Their communication is actually really important. Class communication is a call that goes beyond the class context. Any method calls on other classes are "messages" that classes are exchanging.

An example:
```csharp
public class HealthController : MonoBehaviour
{
    //Required scriptable object
    [SerializeField]
    private HealthSettings healthSettings;

	[SerializeField]
    private int maxHealth;

	private void Awake()
	{
		if(!healthSettings)
		{
			Debug.LogWarning("No health settings!");
			return;
		}
		
		maxHealth = healthSettings.GetMaxHealth();
	}
    
}
```
### Dependencies

The code above is an example of class communication. When we declare that we need the HealthSettings reference in the health controller class, we are actually establishing a relationship. The HealthController class now depends on the existence of a HealthSettings class in order to work and to compile. Even if the field is not assigned, the code won't compile if some day we change the class name for health settings for example.

This is what we call a dependency. And this is an indication of a form of communication. When we establish that we need this dependency, probably we mean that later on in this class we will need to call some action or grab some data from that target class. This is what we call class communication, this need to transfer data or to call actions remotely.

### Communication

As we discovered together, communication between classes is when a class needs to do some action or to get or set some data in another class. We can see this happening in our example when we call the HealthSettings scriptable object to grab its `maxHealth` value. 

Here:
```csharp
maxHealth = healthSettings.GetMaxHealth();
```
When we call that method on the healthSettings class, we are asking that class to give us a value. The call is a message to that class. You can imagine the classes saying "hey, can you give me that maxHealth value that you have?" then the class executes the method and returns "here you are, 42". See? They talk.

This is the default way of communication between classes, the first form that we learn. Create a dependency by adding a reference, calling a method to set a value, get a value or execute some action, and *voilá*.

### The good, the bad and the ugly

This form of communication like everything else has advantages and disadvantages. Let's talk about that!

#### The good (validation, structure)

Just like Clint Eastwood, this method of communication has some great features. The main one that instantly comes to my mind is that when you opt to communicate this way, you enforce a certain structure that validates your code at compile-time. 

What does this mean? It means that your code is resilient to changes. When someone changes the classes that your code depends on, you'll get a compiler error and you'll be able to see where the changes caused problems in your IDE and in Unity itself. You'll be able to apply the necessary changes to your class that consumes those settings quickly.

This means that your code has some sort of *built-in validation*.

#### The bad (scalability, flexibility) 

Although this is a great way of enforcing a structure and rules on how your classes communicate, it has some disadvantages as well. When you enforce a certain structure like this you restrict your application at compile time. This means that changes in the application logic or structure that affect those classes may require you to write new code.

This behavior can be desired for our example, but it can really hinder your development under certain conditions. Let's read another piece of code that shows how this form of communication can be bad.

Here:
```csharp
public class MarketController : MonoBehaviour 
{
	//Required controller that shows UI errors using toasts
	private UIErrorDisplay errorDisplay;

	[...]
	
	public void BuyItem(StoreItem item, PlayerController player)
	{
		//Get the player money controller
		var moneyController = player.PlayerMoneyController;
		var playerInventory = player.InventoryController;
		
		if(moneyController.GetMoney() >= item.getValue()){
		{
			//Sell
		}
		else
		{
			errorDisplay.ShowError("Not enough money!", 2f);
		}
	}

	[...]

}
```

There are several things to talk about this example, I'll focus on communication only for now (I'll write more articles on architecture later).

There are several messages being passed in this class. We also have several dependencies so that we can communicate. The one that better examples the flexibility issues we were talking about is the error display dependency. Why? Well, let's dig deeper (and straight down until we fall into lava).

The main offender in this class is the UIErrorDisplay dependency. This dependency causes two problems in this class, one related to flexibility and another to separation of concerns. The later issue will be discussed in the next part (the ugly).

Why is adding the error display here a flexibility or scalability issue? Although we have compile-time validation when we do this, we also lock the way errors are displayed. The UIErrorDisplay class will handle market errors and only that class. Suppose that class shows the errors in a toast, what if later on the UX (user experience) team asks us to change the error display to a popup? We would change the UIErrorDisplay class and that would be it. But what if they ask us to keep the market using a toast? Add another class? What if, instead, the design team asks us to log that error in the analytics pipeline?

You see how quickly small requirement changes introduce code changes? This is the problem. Changing code is expensive, and the bigger your project gets it becomes harder and harder. You'll be handling hundreds of classes all interconnected and sending messages, all with different objectives and the requirements will keep changing:

> Requirements always change.

And also there is that separation of concerns that we talked about earlier.

#### The ugly (separation of concerns)

When we add the UIErrorDisplay dependency, we also are adding a **concern** to the MarketController class. Initially when we wrote this class, because of its name, we intended that this class would handle market actions, operations and maybe data. Why? Because when another developer (or even you later on) reads this class name he or she will understand that this is a market controller, which means it handles market actions. Still we betrayed that other developer, and possibly ourselves in the future, because we also added error handling to our class.

This is what a concern is, when we write classes we are defining a scope, we are defining data and actions that solve a specific problem set. This doesn't seem a problem at this scale, but when you have hundreds of classes, how can we understand and navigate a codebase where class names don't reflect what they do? Go crazy (or go full XGH).

## Events

This is where events come in handy. Events are another way of establishing communication between classes without introducing a lot of coupling in the process. They remove the need to have a dependency to the class that will receive the message, while also allowing  for more classes to receive the same message.

### Systems

actors, structures
listeners
producers, consumers, pipelines, channels, filtering

### Implementations

C# events
UnityEvent
UnityMessages
Unity Monobehaviour events
My event pipeline

# Unity Event Components

Flexible event components and UnityEvents helper class.

DelayedEvent (simple)
EventQueue
EventRelay
EventCircuitBreaker
