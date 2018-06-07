This repository contains code to host the site https://pentimenti.github.io/

This website is for editing the output of OCR text (text automatically transcribed via software) in order to produce an accurate transcription of a book.

# Getting started

In order to view and edit the website, you need to sign in with your github account. If you don't have a github account, please sign up here: https://github.com/

Next, you will need to get write access to this repository. To do so, please contact an administrator of pentimenti organization (tguinard@gmail.com will work), and let them know your github username.

When you first navigate to https://pentimenti.github.io/, there will be a popup for sign-in. Please tell your browser to allow popups if it blocks the popup.

# How to edit a book

## How the interface works

You can view one page at a time from a specific book. The original image is on the right side, and the text transcription is on the left side. Originally, the transcription is automatically done by a computer, but there's always mistakes present when we use this method. 

The interface has a 'read out loud' feature which may make it easier for you to quickly proofread a page.

When you click save, your work for the current page will be saved. Anyone should be able to see your changes afterwards.

### Colors

Areas of high confidence are colored black, areas of medium confidence are colored blue, and areas of low confidence are colored red. This color scheme is meant to aid the proofreading process, but it is not perfect. There can be an error anywhere!

You can edit the colors via the "A" symbol at the top of the text editor. When doing so, please follow the black-blue-red scheme discussed here. Note that colors are used in this interface only, and will be removed automatically once you are done with the project and download your book as text files. 

## Text format standards

You should check with your project supervisor on specific requirements for your project, but a good place to start is by checking out "Key help documents" of Distributed Proofreaders (Project Gutenberg's tool): https://www.pgdp.net/

# How to download the edited text

Updated edited text is located in this repository under bookname/txts. For example [1872-etzensberger-up-nile-by-steam-cook/txts](https://github.com/pentimenti/pentimenti.github.io/tree/master/1872-etzensberger-up-nile-by-steam-cook/txts)

If you don't know git commands, the easiest way to download text files is to navigate to the top of this page, under the green "Clone or download" button, choose to download zip. After you download, you will have a folder that has the same structure as this website.

# How to add a book to this project

*The rest of this README assumes you have technical knowledge*

You need to add a new data folder, and a new dropdown option in index.html

You need to add these directories, where "mybook" is the name of your new book
* mybook/htmls/
* mybook/pngs/
* mybook/txts/ (not strictly required, but recommended)

Please follow the naming conventions. See [this folder](https://github.com/pentimenti/pentimenti.github.io/tree/master/1872-etzensberger-up-nile-by-steam-cook) for example:
* 1.html, 2.html, ...
* 1.png, 2.png, ...
* 1.txt, 2.txt, ...

See the [pentimento README](https://github.com/Linguistics575/pentimento#post-ocr-editing-interface-1) on how you can use our sister project to generate editable output from a PDF.

Please try to keep this repository under 1GB per github's [recommendation](https://help.github.com/articles/what-is-my-disk-quota/). Currently, that's about 4 books. If you really want more, push for someone to look at [this issue](https://github.com/pentimenti/pentimenti.github.io/issues/1).

Next, edit index.html in order to make your change viewable in the editor. Change the code that looks like this
```
            <select id="book">
                <option value="1872-etzensberger-up-nile-by-steam-cook">1872-etzensberger-up-nile-by-steam-cook</option>
                <option value="1885-baedekers-lower-egypt">1885-baedekers-lower-egypt</option>
                <option value="1889-sandwith-egypt-as-winter-resort">1889-sandwith-egypt-as-winter-resort</option>
                <option value="1892-baedeker-egypt_upper_egypt">1892-baedeker-egypt_upper_egypt</option>
            </select>
```
To this (if the name of your book is "mybook")
```
            <select id="book">
                <option value="1872-etzensberger-up-nile-by-steam-cook">1872-etzensberger-up-nile-by-steam-cook</option>
                <option value="1885-baedekers-lower-egypt">1885-baedekers-lower-egypt</option>
                <option value="1889-sandwith-egypt-as-winter-resort">1889-sandwith-egypt-as-winter-resort</option>
                <option value="1892-baedeker-egypt_upper_egypt">1892-baedeker-egypt_upper_egypt</option>
                <option value="mybook">mybook</option>
            </select>
```

# How to move this project to some other github repository

General steps:
* You will need to change any code in [index.html](https://github.com/pentimenti/pentimenti.github.io/blob/master/index.html) that makes assumptions about the name of the repository.
* The administrator of the new repo should ensure Github pages is allowed for this repo (Settings -> options -> Github Pages)

If you want to keep the same OAuth config:
* In order for OAuth (signing in via github) to work, you should ask [Theresa](mailto:tguinard@gmail.com) to add your new website url to the list of allowed domains.

If you want to use your own OAuth:
* Create a github oauth app [here](https://github.com/settings/developers). The homepage url is your new website (https://orgname.github.io or https://orgname.github.io/path). The authorization callback url should be https://oauth.io/auth 
* Create an account on [oauth.io](https://oauth.io/). 
* Navigate to https://oauth.io/dashboard -> Integrated APIs -> +Add APIs -> select "github"
* Add the webpage url (https://orgname.github.io or https://orgname.github.io/path) to "Domains & URLs whitelist" (under "General" tab)
* In index.html, replace "VnRodo6ycABEgsuWx0LF7BBgO-I" with the value under "Public key"

# JavaScript libraries used in this project
* [Github.js](https://github.com/github-tools/github)
* [Oauth js](https://github.com/oauth-io/oauth-js)
* [Responsive Voice](https://responsivevoice.org/)
* [Tiny MCE](https://www.tinymce.com/)
* [Bootstrap](https://getbootstrap.com/)
* [jQuery](https://jquery.com/)
