# Blurry Landing Page

This is a component that we can use as a site loading progress.  There is a counter and an image.  As teh site is loading, the counter counts from 0 to 100 and dims as it counts.  At the same time the image goes from being blurry to full focus.  

by [David Gallivan](http://twitter.com/CodingwithDavid)


## Getting Started

1. Clone this repository

   ```Command Line
   git clone https://github.com/CodingWithDavid/SimpleProjects
   cd SimpleProjects
   ```

1.	Open in Visual Studio or Visual Code
a.	With Visual Code you will need to install the C# extensions
2.	Press F5

## What's in the App

This project had 3 Blazor changes
1. Timer
    1. We need a timer to track when we need to update the display
    2. Timers between Server-Side and Client-Side are a little different
        1. On server side, you can not cal StateHasChanged on the timer thread, you can only call it on the UI thread
            1. There are a couple of ways to resolve this
                1. Application state with eventing
                2. Use Invoke on the timer thread
                3. I chose to go with the Invoke method
        2. Client side
            1. Since there is only the UI thread for the timer, you can call StateHasChanged
2. Setting a style value, not a class
    1. Have had updated styles before by making the style class a variable and setting the class name of the variable
    2. With this project we have to change the actual value of the opacity and the image filter as the counter changes
    3. To achieve this we will use an in line style
        1. `<section class="bg" style="@filtering"></section>`
        2.  we change the variable filtering as the counter counts
3. We need a method that would allow us to scale the filter form 30 to 100 as the counter went from 0 to 100
    1. We simply created a scale method that did the math



## Problems or Suggestions

[Open an issue here]( https://github.com/CodingWithDavid/SimpleProjects/issues)

## Thank You


## Resources

- [VS Code](https://code.visualstudio.com)
- [Visual Studio]( https://visualstudio.microsoft.com/)



