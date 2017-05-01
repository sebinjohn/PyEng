FILE: Multiprocessing/thread.py
Error: SyntaxError: Missing parentheses in call to 'print'
Cause: Python 2 vs Python 3 problem. print is a statement in py2 and a function in py3.
Solution: use print as a function: print("Hello")


FILE: audio/get_freq.py
Error: FileNotFoundError: [Errno 2] No such file or directory: 'test.wav'
Cause: File 'test.wav' is missing
Solution: execut create_wave.py before get_freq.py

FILE: machine/ml_main.py
Error: SyntaxError: Missing parentheses in call to 'print'
Cause: Python 2 vs Python 3 problem. print is a statement in py2 and a function in py3.
Solution: use print as a function: print("Hello")


FILE: machine/mcalc_correlation.py
Error: SyntaxError: Missing parentheses in call to 'print'
Cause: Python 2 vs Python 3 problem. print is a statement in py2 and a function in py3.
Solution: use print as a function: print("Hello")


FILE: Pandas/pandas_movie.py
Error: 
  File "pandas_movie.py", line 19
    print "Top rated movies (overall): \n" , movie_data.groupby('title').size().order(ascending=False)[:20]
                                         ^
SyntaxError: invalid syntax
Cause: Python 2 vs Python 3 problem. print is a statement in py2 and a function in py3.
Solution:
	- use print as a function: print("Hello")
	- Once the print statement is fixed we will hit the below issue
		"UnicodeDecodeError: 'utf-8' codec can't decode byte 0xe9 in position 3: invalid continuation byte"
		This is because the file is encoded using windows-1252 (Latin)
		This can be verified by `uchardet movie_lens/u.item`
		To fix this issue, conver the file to utf-8 encoding (iconv -f windows-1252 -t utf-8 movie_lens/u.item > movie_lens/u.item)



FILE: Pandas/obesity.py
Error:
  File "obesity.py", line 5
    print  data.sheet_names
              ^
SyntaxError: Missing parentheses in call to 'print'
Cause: Python 2 vs Python 3 problem. print is a statement in py2 and a function in py3.
Solution: use print as a function: print("Hello")



FILE: rpi/webapp.py
ERROR:
Traceback (most recent call last):
  File "webapp.py", line 28, in <module>
    app.run(host='0.0.0.0', port=80, debug=True)
  File "/home/zein/anaconda3/lib/python3.6/site-packages/flask/app.py", line 841, in run
    run_simple(host, port, self, **options)
  File "/home/zein/anaconda3/lib/python3.6/site-packages/werkzeug/serving.py", line 691, in run_simple
    s.bind((hostname, port))
PermissionError: [Errno 13] Permission denied

Cause: The web app is trying to bind to port 80 which is not possible if we are executing the program as a normal user
Solution: change the port number to > 1024 
executing the program as root is also a solution, but that would require additional boostraping(eg: setting up anaconda)


FILE: rpi/webapp_boostrap.py
ERROR:
Traceback (most recent call last):
  File "webapp_bootstrap.py", line 28, in <module>
    app.run(host='0.0.0.0', port=80, debug=True)
  File "/home/zein/anaconda3/lib/python3.6/site-packages/flask/app.py", line 841, in run
    run_simple(host, port, self, **options)
  File "/home/zein/anaconda3/lib/python3.6/site-packages/werkzeug/serving.py", line 691, in run_simple
    s.bind((hostname, port))
PermissionError: [Errno 13] Permission denied

Cause: The web app is trying to bind to port 80 which is not possible if we are executing the program as a normal user
Solution: change the port number to > 1024 
executing the program as root is also a solution, but that would require additional boostraping(eg: setting up anaconda)


FILE: Image_Video/*.py
ERROR:
```
zein@zein-VirtualBox:~/dev/PyEng/Image_Video$ find . -name "*.py" -exec python {} \;
Traceback (most recent call last):
  File "./display.py", line 1, in <module>
    import cv2
ModuleNotFoundError: No module named 'cv2'
Traceback (most recent call last):
  File "./motion_detect.py", line 7, in <module>
    import cv2
ModuleNotFoundError: No module named 'cv2'
Traceback (most recent call last):
  File "./count_cards.py", line 1, in <module>
    import cv2
ModuleNotFoundError: No module named 'cv2'
Traceback (most recent call last):
  File "./color_train.py", line 6, in <module>
    from SimpleCV import *
ModuleNotFoundError: No module named 'SimpleCV'
Traceback (most recent call last):
  File "./face_detect.py", line 7, in <module>
    import cv2
ModuleNotFoundError: No module named 'cv2'
Traceback (most recent call last):
  File "./edge_detect.py", line 1, in <module>
    import cv2
ModuleNotFoundError: No module named 'cv2'
Traceback (most recent call last):
  File "./webcam_face_detect.py", line 7, in <module>
    import cv2
ModuleNotFoundError: No module named 'cv2'
Traceback (most recent call last):
  File "./color_test.py", line 6, in <module>
    from SimpleCV import *
ModuleNotFoundError: No module named 'SimpleCV'
Traceback (most recent call last):
  File "./blur.py", line 1, in <module>
    import cv2
ModuleNotFoundError: No module named 'cv2'
zein@zein-VirtualBox:~/dev/PyEng/Image_Video$

```

FILE: Image_video/color_test.py

ERROR-1:
Traceback (most recent call last):
  File "color_test.py", line 6, in <module>
    from SimpleCV import *
ModuleNotFoundError: No module named 'SimpleCV'

Cause: SimpleCV is not installed.
Solution: pip install simplecv

ERROR-2:
Traceback (most recent call last):
  File "color_test.py", line 6, in <module>
    from SimpleCV import *
  File "/home/zein/anaconda3/lib/python3.6/site-packages/SimpleCV/__init__.py", line 3, in <module>
    from SimpleCV.base import *
  File "/home/zein/anaconda3/lib/python3.6/site-packages/SimpleCV/base.py", line 139
    print 'unit test'
                    ^
SyntaxError: Missing parentheses in call to 'print'

Cause: No python3 support for simplecv
Solution: Merge this PR: https://github.com/sightmachine/SimpleCV/pull/677


FILE: blur.py
STATUS: OK


FILE: color_train.py
ERROR:
Traceback (most recent call last):
  File "color_test.py", line 6, in <module>
    from SimpleCV import *
  File "/home/zein/anaconda3/lib/python3.6/site-packages/SimpleCV/__init__.py", line 3, in <module>
    from SimpleCV.base import *
  File "/home/zein/anaconda3/lib/python3.6/site-packages/SimpleCV/base.py", line 139
    print 'unit test'
                    ^
SyntaxError: Missing parentheses in call to 'print'

Cause: No python3 support for simplecv
Solution: Merge this PR: https://github.com/sightmachine/SimpleCV/pull/677


