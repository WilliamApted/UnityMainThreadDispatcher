# UnityMainThreadDispatcher 2020

A thread-safe way of calling functions/methods on the main thread.

### When is it useful?

* Calling methods to manipulate the GUI from anywhere
* Other actions typically limited to the main thread

## Version
Latest version tested with Unity 2019.3.0f6.

## Installation

No dependencies needed other than Unity. 

1. Download the UnityMainThreadDispatcher prefab and add it to your scene

2. Download the UnityMainThreadDispatcher.cs script and add it to the prefab.

3. Place the above prefab with code attached in any scene you want to use the main thread dispatcher. 

4. You are now ready to call methods on the main thread with the below code.

## Usage

###  Simple Method

```C#
	UnityMainThreadDispatcher.Instance().Enqueue(() => MethodToCall(SomeInput));
```

### Alternative

```C#
	public IEnumerator ThisWillBeExecutedOnTheMainThread() {
		Debug.Log ("This is executed from the main thread");
		yield return null;
	}
	public void ExampleMainThreadCall() {
		UnityMainThreadDispatcher.Instance().Enqueue(ThisWillBeExecutedOnTheMainThread()); 
	}
```

### Author
Originally created by @PimDeWitte, this fork by @WilliamApted tests and maintains the project with the latest unity versions. 






 
