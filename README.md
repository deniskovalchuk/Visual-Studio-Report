<h2>Problem description</h2>

The Visual Studio WPF dialogs ([Microsoft.VisualStudio.PlatformUI.DialogWindow](https://learn.microsoft.com/en-us/dotnet/api/microsoft.visualstudio.platformui.dialogwindow?view=visualstudiosdk-2022)) with the resize mode ([System.Windows.ResizeMode](https://learn.microsoft.com/en-us/dotnet/api/system.windows.window.resizemode?view=windowsdesktop-6.0)) set to `NoResize` still allow users to resize using the context menu commands.

<h2>Steps to reproduce</h2>

1. Download the project.
2. Open the solution in Visual Studio.
3. `Debug -> Start Debugging (F5)`.
4. In the opened experimental instance: `Tools -> Show Non-Resizable Window`.
5. Right-click on the title bar to open the context menu. The `Size`, `Minimize` and `Maximize` commands are enabled and behave in the following way:
    - Clicking the `Size` command does not allow you to resize.
    - Clicking the `Minimize` command minimizes the window and minimizes Visual Studio.
    - Clicking the `Maximize` command maximizes the window so that it takes up the whole screen, including the taskbar.

<h2>Notes</h2>

1. This problem is not reproduced with [System.Windows.Window](https://learn.microsoft.com/en-us/dotnet/api/system.windows.window?view=windowsdesktop-6.0).
2. [HasMaximizeButton](https://learn.microsoft.com/en-us/dotnet/api/microsoft.visualstudio.platformui.dialogwindowbase.hasmaximizebutton?view=visualstudiosdk-2022#microsoft-visualstudio-platformui-dialogwindowbase-hasmaximizebutton) and [HasMinimizeButton](https://learn.microsoft.com/en-us/dotnet/api/microsoft.visualstudio.platformui.dialogwindowbase.hasminimizebutton?view=visualstudiosdk-2022) have no effect on this problem.
