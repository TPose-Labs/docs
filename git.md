# Using git (specifically when working with others)

---
## Creating a new repository
On github, navigate to the TPose-labs organization. Towards the right hand side of the page, you'll see a green button that says "new." You'll be directed to a page that prompts you to specify the name and description of the repository. Go ahead and do that, and then click the green button at the bottom. Now you have a git repository!
You probably don't have anything in the repository right now. Here's how you link it to a directory on your local machine. Once you create a new repository, you'll be directed to a page with a bunch of stuff on it. Ignore most of that. There's a URL in the top blue-shaded box on that page, though. Copy that to your clipboard. Next, using the command line, navigate to the directory you want to link to the repository, and type the following commands:
* `git init`
* `git remote add origin <the_url_you_just_copied>`

And that's it. You've linked the repository to your local machine, and now you can go about adding whatever you want to it.

## Adding stuff to your repository
