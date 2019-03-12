# CV
The goal of this repo is to generate a CV using Markdown and CSS style.
The benefits of using Markdown + CSS are : 
- Easy to maintain
- Separation content/style and so a better control on the style
- Easy and reliable export to HTML or PDF formats

## The markdwon file

The markdown file has been written with Remarkable.

https://github.com/jamiemcg/Remarkable/releases

## The CSS

We need to consider that some default CSS styles are applied to the HTML objects by default.
https://www.w3schools.com/cssref/css_default_values.asp

It's also important to well understand the principle of the model boxes in CSS philosophy. Personnaly, i choose to set all paddings to 0 and to play only with the margins.
https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Box_model

## Generating the HTML file

### Diversity of HTML engines standards

Don't trust only the HTML viewer integrated in Remarkable! Generate also some "HTML styled files" and open them in other browsers. Modify the CSS file till you reach the layout you want.

### Modifying the HTML file (title and images)

Once you got the perfect HTML file, edit the HTML code and replace the title by your name.

The HTML file currently propose links to the images, so in case you plan to send the html file by e-mails, the links will be broken. To make the HTML file "standalone", convert the images to base64 format. There are many HTML -> Base64 converters on the web.

https://www.base64-image.de/

## Generating the PDF

The Remarkable package integrates the library PDFkit (https://pypi.org/project/pdfkit) to generate PDF from HTML page.

Unfortunately, Remarkable doesn't propose yet to manage the margins of the PDF document created. You can do it manually editing the code of "RemarkableWindow.py".

> sudo gedit /usr/lib/python3/dist-packages/remarkable/RemarkableWindow.py

    pdfkit.from_string(html, file_name, options= {'quiet': '', 'page-size': 'Letter',
                    'margin-top': '0.1in',
                    'margin-right': '0.5in',
                    'margin-bottom': '0.1in',
                    'margin-left': '0.5in',
                    'encoding': "UTF-8",
                    'javascript-delay' : '550',
                    'no-outline': None})

I recommend using the margin as indicated above.
