---
description: Microsoft Edge DevTools Protocol Version 0.1 supports the following tooling clients.
title: DevTools Protocol Version 0.1 Clients (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.service: microsoft-edge
ms.custom: seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
---
# DevTools Protocol Version 0.1 Clients (EdgeHTML)  

> [!NOTE]
> The Microsoft Edge DevTools Protocol works only on [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) and later [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) builds.

**DevTools Protocol 0.1** supports the following tooling clients.

[![Microsoft Edge DevTools Preview](../media/microsoft-edge-devtools.png)](#microsoft-edge-devtools-preview) [![Microsoft Visual Studio 15.7 Preview 2](../media/visual-studio-2017.png)](#microsoft-visual-studio-preview)

## Microsoft Edge DevTools Preview

You can use the standalone [**Microsoft Edge DevTools Preview**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) Windows 10 app from the Microsoft Store to remotely debug a host device running Microsoft Edge ([EdgeHTML 17](../../dev-guide/index.md) or later).

This preliminary Version 0.1 release of the DevTools Protocol provides core debugging functionality, such as setting breakpoints, stepping through code, and exploring stack traces. In the Edge DevTools UI, this translates to functionality available in the [**Debugger**](../../devtools-guide/debugger.md) panel, minus cache inspection (for Web storage, Service worker, Cache API, and IndexedDB). Currently Microsoft Edge remote debugging is limited to desktop hosts, with support for other Windows 10 devices coming in future releases.

Here's how to set up remote debugging with the Microsoft Edge DevTools Preview app. The DevTools Protocol is in preview and requires [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) or a later Windows Insider Preview build on the host (debugee) machine. The Edge DevTools Preview app (used on the debugger machine) will run on Fall Creators Update (version 1709) and Windows Insider Preview builds.

**On the host (debugee) machine...**

1. If you're on a WiFi network, ensure the network is marked as either **Domain** or **Private**. You can verify this by opening the [**Windows Defender Security Center**](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) app, clicking on **Firewall & network protection** and checking if your network is listed as a *Domain network* or *Private network*. 

    If its listed as *Public*, go to **Settings** > **Network & Internet** > **Wi-Fi**, click on your network and toggle the *Network profile* button to **Private**.

2. Open the **For developers** control panel in Windows *Settings* (search for *developer* and click on *Use developer features*), and: 

    a. Toggle on **Developer Mode**. This will install the *Developer Mode* package, enabling remote tooling for desktop.

    b. Enable [**Device Portal**](/windows/uwp/debug-test-perf/device-portal) (*Turn on remote diagnostics over local area network connections*) and **Device discovery** (*Make your device visible to USB connections and your local network*).

    c. Turn on **Authentication** and supply a username / password.

    d. Note the machine IP address and connection port (50443) displayed.

3. Open tabs in Microsoft Edge that you wish to debug from the client machine.

**On the client (debugger) machine...**

1.  Install and launch the standalone [Microsoft Edge DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) app from the Microsoft Store.

2. Open the **Remote** panel and enter the network location (URL and port) of the host machine and click **Connect**.

3. **Install** the host machine's certificate from the *Untrusted Certificate* dialog that appears.

4. Supply the username/password you designated for Device Portal authentication.

5. The *Remote* panel will load a list of debuggable page targets on the host machine. Select one to start debugging.

6. Use the **Refresh** button to update and reload the list of remote page targets on the host machine. Click the **Disconnect** button to return to the *Connect to a remote device* screen and attach to a different host.

## Microsoft Visual Studio Preview

Using the latest [**Visual Studio Preview**](https://www.visualstudio.com/vs/preview/) build (Visual Studio 15.7 Preview 1 or later), you can launch and debug Microsoft Edge from the IDE on any ASP.NET or .NET Core project. The DevTools Protocol is currently in preview and requires you to be running a [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) build.

Here's how to set up Microsoft Edge debugging with Visual Studio:

1.  Install and launch the latest [**Visual Studio Preview**](https://www.visualstudio.com/vs/preview/) build (Visual Studio 15.7 Preview 1 or later).

2. Open an existing ASP.NET or .NET Core project or **Create new project...** using one of the **Visual C#** .NET templates.

3. In the project **Solution Explorer**, open the JavaScript files you wish to debug and set breakpoints within the IDE just as you would with server-side code.

4. Press `F5` to launch Microsoft Edge running the DevTools Server. When a breakpoint is hit, you'll break into Visual Studio and can further inspect and step through the code from there.
