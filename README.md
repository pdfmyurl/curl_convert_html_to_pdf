# Convert HTML to PDF with cURL on the Linux command line

The examples below use our [HTML to PDF API](https://pdfmyurl.com/html-to-pdf-api) to create PDFs from HTML or URLs. Many more options can be used to influence the layout of the PDFs as well as the way the conversion takes place.


## cURL URL to PDF conversion example

Here we're converting the example URL https://www.example.com to PDF and storing it in a file called "result.pdf".

    curl 	-d "license=yourlicensekey" \
	    	--data-urlencode "url=https://www.example.com" \
	    	-o result.pdf \
	    	-H "Content-Type: application/x-www-form-urlencoded" \
	    	-X POST https://pdfmyurl.com/api

You can add additional parameters by using the cURL -d parameter or the cURL --data-urlencode parameter in case you need URL encoding.

## cURL HTML to PDF conversion example

This example will convert raw HTML from a file named "html.html" to a PDF with the name "result.pdf". Since you want to usually convert quite a bit of HTML to get a full page, it makes sense to store that in a file first before using cURL. Otherwise your cURL command becomes really large, just due to the html parameter.

    curl 	-d "license=yourlicensekey" \ 
        	--data-urlencode html@html.html \
        	-o result.pdf \
        	-H "Content-Type: application/x-www-form-urlencoded" \
        	-X POST https://pdfmyurl.com/api

To use this example just copy/paste it and make sure you have a file named "html.html" in the current directory that contains the HTML.

