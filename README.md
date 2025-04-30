> [!WARNING]
> This is patched in ChromeOS versions higher than 134

## LightSPED Killer Agent
LightSPED is a tool made by [Blobby-Boi](https://github.com/Blobby-Boi) that allows ChromeOS users to easily disable the "Lightspeed Filter Agent" extension. This will persist until you restart your computer or flip the switch again.

## How does this even work?
This works by exploiting a vulnerability in Lightspeed where if you load any of its pages and then try opening a long URI afterwards (as in, over 1 million charactes) the extension page gets permanently hanged. This is a really neat way of hanging an extension and much more reliable than ExtPrint3r and ExtHang3r, though sadly it only works for Lightspeed. I dont really know the reason why, but someone suggested it could have to do with Lighspeed's processes not being OS-level like in other filters.

### How to use
- Step 1. Go to [this link](https://blobby-boi.github.io/LightSPED-Killer-Agent/) or open the following data URI:
```
data:text/html;charset=utf-8,%3C!DOCTYPE%20html%3E%0A%3Chtml%20lang%3D%22en%22%3E%0A%3Chead%3E%0A%20%3Cmeta%20charset%3D%22UTF-8%22%3E%0A%20%3Cmeta%20name%3D%22viewport%22%20content%3D%22width%3Ddevice-width%2C%20initial-scale%3D1.0%22%3E%0A%20%3Ctitle%3ELightSPED%20Killer%20Agent%3C%2Ftitle%3E%0A%20%3Clink%20rel%3D%22shortcut%20icon%22%20type%3D%22image%2Fpng%22%20href%3D%22https%3A%2F%2Fraw.githubusercontent.com%2FBlobby-Boi%2FLightSPED-Killer-Agent%2Frefs%2Fheads%2Fmain%2Flightspeed.png%22%3E%0A%20%3Clink%20href%3D%22https%3A%2F%2Ffonts.googleapis.com%2Fcss2%3Ffamily%3DRoboto%3Awght%40400%3B700%26display%3Dswap%22%20rel%3D%22stylesheet%22%3E%0A%20%20%3Cstyle%3E%0A%20%20body%20%7B%0A%20%20%20%20%20background-color%3A%20%231e1f22%3B%0A%20%20%7D%0A%20%20%3C%2Fstyle%3E%0A%20%3Cscript%3E%0A%20document.addEventListener(%22DOMContentLoaded%22%2C%20()%20%3D%3E%20%7B%0A%20const%20main%20%3D%20%22https%3A%2F%2Fraw.githubusercontent.com%2FBlobby-Boi%2FLightSPED-Killer-Agent%2Frefs%2Fheads%2Fmain%2Findex.html%22%3B%0A%20const%20fallback%20%3D%20%22https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2FBlobby-Boi%2FLightSPED-Killer-Agent%2Findex.html%22%3B%0A%0A%20fetch(main)%0A%20.then(response%20%3D%3E%20%7B%0A%20if%20(!response.ok)%20throw%20new%20Error(%22Main%20URL%20failed%22)%3B%0A%20return%20response.text()%3B%0A%20%7D)%0A%20.catch(()%20%3D%3E%20%7B%0A%20return%20fetch(fallback).then(response%20%3D%3E%20%7B%0A%20if%20(!response.ok)%20throw%20new%20Error(%22Fallback%20URL%20failed%22)%3B%0A%20return%20response.text()%3B%0A%20%7D)%3B%0A%20%7D)%0A%20.then(html%20%3D%3E%20%7B%0A%20document.open()%3B%0A%20document.write(html)%3B%0A%20document.close()%3B%0A%20%7D)%0A%20%7D)%3B%0A%20%3C%2Fscript%3E%0A%3C%2Fhead%3E%0A%3C%2Fhtml%3E
```
- Step 2. Click the big "Launch" button
- Step 3. Follow the instructions on the popup
- Step 4. Lightspeed has been disabled! To re-enable it, go to `chrome://extensions/?id=adkcpkpghahmbopkjchobieckeoaoeem` again and flip the "Allow access to file URLs" switch once more.
