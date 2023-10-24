## Objetivo

## Datos de acceso al nivel
```
Link: https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/message.wav

```
## Solución

```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ sstv -d message.wav -o img.jpg
Traceback (most recent call last):
  File "/usr/local/bin/sstv", line 33, in <module>
    sys.exit(load_entry_point('sstv==0.1', 'console_scripts', 'sstv')())
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/dist-packages/sstv-0.1-py3.11.egg/sstv/__main__.py", line 18, in main
  File "/usr/local/lib/python3.11/dist-packages/sstv-0.1-py3.11.egg/sstv/command.py", line 108, in start
  File "/usr/local/lib/python3.11/dist-packages/sstv-0.1-py3.11.egg/sstv/decode.py", line 45, in __init__
  File "/usr/local/lib/python3.11/dist-packages/PySoundFile-0.9.0.post1-py3.11.egg/soundfile.py", line 372, in read
    with SoundFile(file, 'r', samplerate, channels,
         ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/dist-packages/PySoundFile-0.9.0.post1-py3.11.egg/soundfile.py", line 740, in __init__
    self._file = self._open(file, mode_int, closefd)
                 ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/dist-packages/PySoundFile-0.9.0.post1-py3.11.egg/soundfile.py", line 1264, in _open
    _error_check(_snd.sf_error(file_ptr),
  File "/usr/local/lib/python3.11/dist-packages/PySoundFile-0.9.0.post1-py3.11.egg/soundfile.py", line 1455, in _error_check
    raise RuntimeError(prefix + _ffi.string(err_str).decode('utf-8', 'replace'))
RuntimeError: Error opening <_io.BufferedReader name='message.wav'>: Format not recognised.
                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ sstv -d message.wav -o img.jpg
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...   [#################################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ open img.jpg
                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ 


```
## Notas adicionales
```bash

```
![[Pasted image 20231018105238.png]]