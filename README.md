# Visual Studio Report

<h2>Problem description</h2>

The Visual Studio WPF dialogs ([Microsoft.VisualStudio.PlatformUI.DialogWindow](https://learn.microsoft.com/en-us/dotnet/api/microsoft.visualstudio.platformui.dialogwindow?view=visualstudiosdk-2022)) with the resize mode ([System.Windows.ResizeMode](https://learn.microsoft.com/en-us/dotnet/api/system.windows.window.resizemode?view=windowsdesktop-6.0)) set to `NoResize` still allow users to resize using the context menu commands.

![alt text](https://github.com/deniskovalchuk/Visual-Studio-Report/blob/fc921a35ba3dd493bd4a19111833b0506774be53/Images/ContextMenu.png)

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

1. This problem is reproduced with the `Help -> About Microsoft Visual Studio` window.
2. This problem is not reproduced with [System.Windows.Window](https://learn.microsoft.com/en-us/dotnet/api/system.windows.window?view=windowsdesktop-6.0).
3. [HasMaximizeButton](https://learn.microsoft.com/en-us/dotnet/api/microsoft.visualstudio.platformui.dialogwindowbase.hasmaximizebutton?view=visualstudiosdk-2022#microsoft-visualstudio-platformui-dialogwindowbase-hasmaximizebutton) and [HasMinimizeButton](https://learn.microsoft.com/en-us/dotnet/api/microsoft.visualstudio.platformui.dialogwindowbase.hasminimizebutton?view=visualstudiosdk-2022) have no effect on this problem.

<h2>References</h2>
https://developercommunity.visualstudio.com/t/Non-resizable-DialogWindow-can-be-resize/10247555
