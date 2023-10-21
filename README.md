# AppSDKBugs

VisualStudio 2022 tries to attach another debugger when `App.xaml.cs` tries to activate two Windows:

```
protected override void OnLaunched(Microsoft.UI.Xaml.LaunchActivatedEventArgs args)
{
    m_window = new MainWindow();
    m_window.Activate();

    m_window = new MainWindow();
    m_window.Activate();
}
```

Output:
`The program '[26132] DebuggerCrash.exe' has exited with code 3221225477 (0xc0000005) 'Access violation'.`

This **happens** (**DebuggerCrash** project) using 
- Microsoft.WindowsAppSDK 1.4.231008000 
- Microsoft.Windows.SDK.BuildTools 10.0.22621.756

This does **not** happen (**DebuggerNoCrash** project) using
- Microsoft.WindowsAppSDK 1.3.230602002
- Microsoft.Windows.SDK.BuildTools 10.0.22621.755