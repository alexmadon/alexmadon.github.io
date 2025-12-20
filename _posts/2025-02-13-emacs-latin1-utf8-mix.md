# fix a file with mlixed utf8 and latin1

https://superuser.com/questions/549497/how-to-switch-back-text-encoding-to-utf-8-with-emacs

If you haven't changed the file, you can try M-x revert-buffer-with-coding-system. One of latin-1 or utf-8 should work, depending on the file.

You can also mark the entire file with C-x h and then try M-x recode-region. It will ask you for Text was really in and But was interpreted as. For the first file in your question, it looks like it should be latin-1 and utf-8, and for the second example it should probably be the other way around, utf-8 and latin-1.

After you got it right, you can choose which coding system to save the file with using M-x set-buffer-file-coding-system (or C-x C-m f for short).
