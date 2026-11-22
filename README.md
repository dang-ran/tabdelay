# tabdelay
TabDelay mirrors an Edge tab's audio/video to PotPlayer on Windows with a configurable delay, like a local screen-record-and-rebroadcast. Useful for A/V sync and aligning browser playback with external sources.
TabDelay

First-Time Setup

1. Install Python 3.10 or later (check "Add Python to PATH" during installation).
2. In Edge, open edge://extensions, or open the extensions page via Settings, and enable Developer mode.
3. Click "Load unpacked extension" and select the extension folder inside this directory.
4. Double-click 点这个使用.pyw ("Double-click to Run.pyw") in this folder.
5. Download PotPlayer. Updating it is optional.
6. The installer is included in the folder.

After double-clicking, the following will happen:
- The local server starts.
- http://127.0.0.1:17392/ opens automatically.
- Closing the control page will automatically stop the server and PotPlayer.
- The extension must be disabled manually.

If double-clicking the .pyw file does nothing, it means .pyw is not associated with pythonw. Create a shortcut instead and set its target to:
pythonw.exe "ThisFolder点这个使用.pyw"

Usage

1. On the control page, first select either "Video + Audio" or "Audio Only".
2. On the page you want to delay, click the extension icon to begin capturing.
3. Wait for the buffer to fill, select the delay in seconds, then click "Apply Delay & Start".
4. PotPlayer will launch automatically.

After switching modes, you must click the extension icon again to restart capture. The page will detect a mode mismatch and block startup, instead of getting stuck buffering indefinitely.

Exit

Simply close the control page tab.
The server and PotPlayer will shut down automatically after about 8 seconds.
Once the extension detects that the server has gone, it will stop capturing and unmute the tab.

Port Conflict

If port 17392 or 17393 is already in use, a dialog will display:
- PID
- Process name

Close the program using the port, then double-click 点这个使用.pyw again.

To check manually:
netstat -ano | findstr :17392

Known Limitations

- Only Windows, Edge, and PotPlayer are supported.
- The extension must be loaded manually on first use.
- Background or minimized tabs may be throttled to 10–20 fps by Edge.
- Hardware H.264 encoding is preferred; it falls back to software encoding when hardware encoding is unavailable.
- The maximum buffer duration is about 65 seconds.

Compliance Notice

This tool only provides local assistance for page playback in your browser. Please use it in a lawful and compliant manner, and confirm on your own that your usage complies with the terms, rules, and applicable laws of any website or service you use. Do not use it for any purpose that may infringe upon others' legitimate rights or violate relevant agreements or laws and regulations. All consequences arising from use are borne solely by the user; if you do not agree, stop using it immediately.
