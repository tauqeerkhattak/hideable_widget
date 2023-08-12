## Hideable Widget

<img src="https://github.com/sameteyisan/hideable_widget/blob/main/sample.gif"  width="200">

First, create a scroll controller.

```dart
final scrollController = ScrollController();
```

Immediately afterwards, give this scroll controller to your scrollable widget.

```dart
ListView(
    controller: scrollController,
    physics: const ClampingScrollPhysics(),
    children: [
        ...List.generate(
        50,
        (index) => ListTile(
            title: Text("List item ${index + 1}"),
        ),
        ).toList(),
        const SizedBox(height: 100),
    ],
),
```

After wrapping your static widget with the hideable widget, give the hideable widget this scroll controller.

```dart
HideableWidget(
    scrollController: scrollController,
    child: BottomAppBar(...)
),
```

That's all. Now you are ready to use the hideable widget. 

Parameters are as follows. ☺️

 - **child**: This is the static widget you want to hide while scrolling.

 - **scrollController**: It should be the same as the scroll controller supplied with your scrollable widget.
 
 - **useOpacity**: Used to turn the opacity animation on and off. It is on by default.
 
 - **duration**: Use this to set the hiding time.

 - **opacityDuration**: Use this to set the opacity duration that runs during the hiding period.