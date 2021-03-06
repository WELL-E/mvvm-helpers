# mvvm-helpers

Collection of Mvvm helper classes for any application.


Grab the NuGet: https://www.nuget.org/packages/Refractored.MvvmHelpers

## What's included?

I wanted to keep this library really small and just created it for myself, but I hope others find it useful. Here is what I added in and feel free to request new things in the Issues tab.

### ObservableObject
Simple implementation of INotifyPropertyChanged that any class can inherit from.

```csharp
/// <summary>
/// Sets the property.
/// </summary>
/// <returns><c>true</c>, if property was set, <c>false</c> otherwise.</returns>
/// <param name="backingStore">Backing store.</param>
/// <param name="value">Value.</param>
/// <param name="propertyName">Property name.</param>
/// <param name="onChanged">On changed.</param>
/// <typeparam name="T">The 1st type parameter.</typeparam>
protected bool SetProperty<T>( ref T backingStore, T value,
    [CallerMemberName]string propertyName = "",
    Action onChanged = null)
```

```csharp
// <summary>
/// Raises the property changed event.
/// </summary>
/// <param name="propertyName">Property name.</param>
protected void OnPropertyChanged([CallerMemberName]string propertyName = "")
```

### BaseViewModel
Your base view model! It implements INotifyPropertyChanged and a bunch of default properties such as **Title, SubTitle, Icon, IsBusy, IsNotBusy, CanLoadMore**.

### Grouping
Best way to group items into a Key/Value pair ObservableCollection for managing groups of data. See my blog post: motzcod.es/post/94643411707/enhancing-xamarinforms-listview-with-grouping

### ObservableRangeCollection
A super awesome ObservableCollection that adds important methods such as: **AddRange, RemoveRange, Replace, and ReplaceRange**.

### Utils
Any and all extension methods that are nifty. Here are the current ones:

```csharp
/// <summary>
/// Task extension to add a timeout.
/// </summary>
/// <returns>The timeout.</returns>
/// <param name="task">Task.</param>
/// <param name="duration">Duration.</param>
/// <typeparam name="T">The 1st type parameter.</typeparam>
public async static Task<T> WithTimeout<T>(this Task<T> task, int duration)
```

