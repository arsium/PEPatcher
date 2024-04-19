# PEPatcher
A PE patcher.
The code source is not public. However, the release is not obfuscated. Feel free to reverse it.

This program is reserved to x64 PE binaries. It is currently able to :

* erase file timestamp          
* erase debug information
* erase exception information
* erase rich header
* set the PE checksum correct value

The idea to create this program comes from studying PE format and modifying the binaries while keeping them still working. More features will be added.
The program works as follows : 

```
"PEPatcher.exe value_choosen "\??\C:\your_path""
```

Possible values are : ```ERASE_FILE_TIME_STAMP (1), ERASE_DEBUG_INFORMATION (2), ERASE_EXCEPTION_INFORMATION (4), ERASE_RICH_HEADER (8), SET_CHECKSUM_VALUE (16)```.<br>
Example with  ```ERASE_DEBUG_INFORMATION + ERASE_EXCEPTION_INFORMATION + ERASE_RICH_HEADER``` : 

```
"PEPatcher.exe 14 "\??\C:\your_path""
```

<h2>Debug information </h2>
<p>After being compiled, executable always contains debug information. This is not possible to remove them without manipulating the binaries after being built.</p>
<img
  src="https://github.com/arsium/PEPatcher/blob/main/Images/DebugInfo.png"
  alt="DebugInfo" />

<h2>Exception information </h2>
<p>After being compiled, even with exception option disabled, the executable still contains exception directory and information. This mecanism is intrinsically linked to Windows 64 bit executable. This is not possible to remove them without manipulating the binaries after being built.</p>

<img
  src="https://github.com/arsium/PEPatcher/blob/main/Images/ExceptionInfo.png"
  alt="Exception information" />

<h2>Rich header</h2>
<p>After being compiled, executable contains information about tools that served to build it. Those information are not officially documented and won't be explain there. There are amazing resources you can find by google it. Those information are located after DOS stub and before starting of NT Header.</p> 
<img
  src="https://github.com/arsium/PEPatcher/blob/main/Images/RichInfo.png"
  alt="Rich header" />


<h2>Checksum value</h2>
<p>After being compiled, executable never contains its checksum value located in Optional Header. However, the algorithm is well-known and it is possible to compute it and set the value to Optional Header.</p>
<img
  src="https://github.com/arsium/PEPatcher/blob/main/Images/ChecksumInfo.png"
  alt="Rich header" />

<h2>Timestamp</h2>
<p>Just for fun.</p>
