# AppSDKBugs

VisualStudio 2022 tries to attach another debugger when App.xaml.cs tries to activate two Windows.

Output:
`The program '[26132] DebuggerCrash.exe' has exited with code 3221225477 (0xc0000005) 'Access violation'.`

This happens using a project (**DebuggerCrash**) dependend on 
- Microsoft.WindowsAppSDK 1.4.231008000 
- Microsoft.Windows.SDK.BuildTools 10.0.22621.756

This does not happen using a project (**DebuggerNoCrash**) dependend
- Microsoft.WindowsAppSDK 1.3.230602002
- Microsoft.Windows.SDK.BuildTools 10.0.22621.755