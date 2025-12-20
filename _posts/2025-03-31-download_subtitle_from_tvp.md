# convert TVP ttml subtitle to SRT

http://www.w3.org/ns/ttml


https://video.stackexchange.com/questions/33241/convert-ttml-subtitles-to-stl-or-srt-in-linux
https://pypi.org/project/ttconv/

$ pip3 install ttconv

tt convert 

madon@toshibalex:~/FTP/new14/Nad Niemnem (1986) $ tt convert -i subtitle_131.xml -o subtitle_131.srt --itype TTML --otype SRT
Input file is subtitle_131.xml
Output file is subtitle_131.srt
Reading: |██████████████████████████████████████████████████| 100% Complete
Merging ISD regions.                                                        
Merging ISD paragraphs.                                                     
Merging ISD regions.                                                        
Merging ISD paragraphs.                                                     
Merging ISD regions.                                                        
Merging ISD paragraphs.                                                     
Merging ISD regions.                                                        
Merging ISD paragraphs.                                                     
Merging ISD regions.                                                        
Merging ISD paragraphs.                                                     
Merging ISD regions.                                                        
Merging ISD paragraphs.                                                     
Merging ISD regions.                                                        
Merging ISD paragraphs.                                                     
Merging ISD regions.                                                        
Merging ISD paragraphs.                                                     
Writing: |██████████████████████████████████████████████████| 100% Complete

# then translate

~/srtgenerator/srtcombine  --target fr -p  subtitle_131.srt 
