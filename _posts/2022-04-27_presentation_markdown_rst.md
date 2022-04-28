
# hovercraft

apt-cache search hovercraft
hovercraft - generator for impress.js presentations from reStructuredText

```
description: Platform Little Friend Presentation.
	      
	      To compile: (generate HTML)
	      hovercraft -s platform_little_friend_presentation.rst platform_little_friend_presentation
	      
	      To print: (generate PDF)
	      pandoc -o platform_little_friend_presentation.pdf platform_little_friend_presentation.rst

	      To get the CJK chars:
	      pandoc --latex-engine=xelatex -V CJKmainfont="AR PL UKai CN" -o platform_little_friend_presentation.pdf platform_little_friend_presentation.rst
	      with:
	      fc-list | grep -i ukai
	      /usr/share/fonts/truetype/arphic/ukai.ttc: AR PL UKai CN:style=Book
	      /usr/share/fonts/truetype/arphic/ukai.ttc: AR PL UKai HK:style=Book
	      /usr/share/fonts/truetype/arphic/ukai.ttc: AR PL UKai TW:style=Book
	      /usr/share/fonts/truetype/arphic/ukai.ttc: AR PL UKai TW MBE:style=Book

	      jira at platformsh.atlassian.net/browse/CC-137
	      
:keywords: presentation, ps
:css: platform_little_friend_presentation.css
:data-transition-duration: 10
:skip-help: true

.. header::

   Say hello

.. footer::

   Platform Little Friend, https://lab.plat.farm/alexmadon/cse-tools/blob/master/platform_little_friend

----

.. image:: platform_little_friend_presentation_medias/say_hello_urban2.jpg

	   
.. note::

   A picture from urban dictionary
   https://www.urbandictionary.com/define.php?term=say%20hello%20to%20my%20little%20friend

----

.. image:: platform_little_friend_presentation_medias/exp03.png

.. note::

   A picture from the movie Scarface
```
