# 🚀 Simple Conveyor Setup with Windows UiAccess Manifest

This project demonstrates a simple Godot 4 Mono application that:
- Displays a UI for application updates
- Verifies if the application has a manifest with `uiaccess=true` inside the 

And a conveyor config file that:
- Embeds the manifest by setting `windows.manifests.exe.content` in `conveyor.conf` to match the content of `app.manifest`

## 🚦 Getting Started

1. Generate the output:
   ```bash
   conveyor make site
   ```

2. Host the files locally:
   ```bash
   npx serve ./output
   ```

3. Access the application:
   - Navigate to http://localhost:3000/download
   - Install the application
   - Upon launch, the application will automatically display whether it has a manifest with UiAccess enabled

## 🔍 Verifying the Manifest

To verify the embedded manifest of the installed application:
1. Navigate to the installation folder in `ProgramFiles/WindowsApps/UiaTest_...`
2. Run the following command:
   ```bash
   mt.exe -manifest -inputresource:".\Godot4SimpleTest.exe;#1" -out:manifest.xml
   ```