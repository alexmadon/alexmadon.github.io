---
layout: post
title: remove the tilde ~ files in emacs backup by changing the backup location
date: '2014-03-27T01:10:00.003-07:00'
author: Alex Madon
tags: unix 
modified_time: '2014-03-27T01:11:00.623-07:00'
blogger_id: tag:blogger.com,1999:blog-7521237649117347170.post-5582750065344306334
blogger_orig_url: http://tuxunix.blogspot.com/2014/03/remove-tilde-files-in-emacs-backup-by.html
---

<pre>(defun make-backup-file-name (file)
(concat "~/.emacs_backups/" (file-name-nondirectory file) "~"))
</pre>