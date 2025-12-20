# TLDR

Use HTML with reveal.js to create the presentation
https://revealjs.com/

For export to PDF, use npm command: decktape


https://github.com/astefanutti/decktape


# details

https://maeda.pm/2023/11/12/convert-reveal-js-slides-to-powerpoint/

npm install -g decktape

python -m http.server 8000



decktape reveal http://localhost:8000/alex_slides.html alex_slides.pdf

# bad version on node

node --version

madon@toshibalex:~/amsterdam/slides $ decktape reveal http://localhost:8000/alex_slides.html blahblah.pdf
