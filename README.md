README
======

I use the script in this project to create eBay listings with HTML that looks good on eBay. I've found eBay's default typography to be unnecessarily hard to read, quite unfriendly, and suspect items sell better if their descriptions are:

- typeset in a sans-serif font,
- at a larger size than the default, and
- in dark blue.

I've found that adding `style` attributes to my markup to be the best way to ensure that eBay doesn't meddle with my styles. Hand coding the HTML would, however, be a royal pain in the ass. So I write my listings in Markdown and use this script to generate the HTML.

Install
-------

All you need is the Python-Markdown library, which you can install in a virtual environment like this:

    # Create a virtual environment
    python -m venv .venv
    source .venv/bin/activate
    activate

    # Install dependencies
    pip install --upgrade pip
    pip install pip-tools
    pip-sync requirements.txt

Usage
-----

Markdown is read on stdin and HTML is printed on stdout. To use the HTML in your eBay listing, paste it into the "HTML" tab of the "Item description" field in your eBay listing.

Assuming you're in the virtual environment created above you can run the script like so:

    ./ebay-html < file.md > file.html

If you'd like to copy the HTMl to your clipboard for pasting it into your eBay listing you could use `xclip` on Linux or `pbcopy` on Mac:

    ./ebay-html < file.md | xclip -i -selection clipboard  # Linux
    ./ebay-html < file.md | pbcopy                         # Mac

When you're done you can exit the virtual environment:

    deactivate
