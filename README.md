# Sweep for Swift blog

## Setup Instructions
To run first install Hugo if you haven't already:

```bash
brew install hugo
```

Then clone down the repository to your machine using

```bash
git clone https://github.com/sweepforswift/blog.git
```

Next cd into the newly cloned repository and execute the following commands
```bash
cd themes
git clone https://github.com/nilproductions/hugo-incorporated.git
```

Lastly, you will need to install the Pygments python library by running
```bash
pip install Pygments
```

At this point you have installed everything needed to run the blog locally. To view it in the broswer you can run ```hugo server``` from the project directory and it will become avaliable at ```localhost:1313```. If you want to build the blog completely, just run ```hugo``` from the project directory and it will create the HTML files.

## Credits
This blog is created using the [Hugo](https://gohugo.io/) static blog generator and the [Hugo Incorporated](https://github.com/nilproductions/hugo-incorporated) theme.

## License
This blog and all of its content is licensed under the GNU Public license.