# Using git (specifically when working with others)

---
## Creating a new repository
On github, navigate to the TPose-labs organization. Towards the right hand side of the page, you'll see a green button that says "new." You'll be directed to a page that prompts you to specify the name and description of the repository. Go ahead and do that, and then click the green button at the bottom. Now you have a git repository!

You probably don't have anything in the repository right now. Here's how you link it to a directory on your local machine. Once you create a new repository, you'll be directed to a page with a bunch of stuff on it. Ignore most of that. There's a URL in the top blue-shaded box on that page, though. Copy that to your clipboard. Next, using the command line, navigate to the directory you want to link to the repository, and type the following commands:
* `git init`
* `git remote add origin <the_url_you_just_copied>`

And that's it. You've linked the repository to your local machine, and now you can go about adding whatever you want to it.

## Adding stuff to your repository
Now that you've linked your local directory to your repository, you can go about adding whatever you want to it. That doesn't mean, however, that those changes will be reflected on git. There are three easy steps to logging your changes to git:
* `git add .`
* `git commit -m "<commit_message_goes_here>"`
* `git push`

When you use those three commands, all of your changes will be logged to the repository, and you can see them on github.
Be careful, though. The first time you push something to a new branch or new repository, you have to use the following command instead of `git push`:

If you've just created a new repository, then the command is `git push --set-upstream origin master`.

If you've just created a new branch (we'll talk about that later), then the command is `git push --set-upstream origin <your_branch_name>`.

## Branches: what they are, why we use them, and how to make them
The "master" branch in a repository is where all the "complete" code lies. That code is final. That code represents the current working state of a project. So how do you go and do other work on that same project, without editing the master branch? Simple. You "branch" off from master and create your own branch. What that does is simply take whatever is in master and copies it to a new branch. Whatever changes are made in your new branch will not be reflected in master (we'll talk more about that in a bit). So how do you make a branch? Locally, navigate to the directory that has the contents of the repository. First, type `git pull` to get whatever changes have been madeto the master branch so far. Then, type `git branch <your_branch_name>` to make a new branch.

Be careful, though, because you're still inside the master branch. To navigate between branches, type `git checkout <your_branch_name>`.

## Registering your changes into the master branch
Say you've gone off and added a new feature to the project in your own branch, and tested it thoroughly to make sure it works. How do you add that to the master branch? You need to make a pull request. What is that, though? A pull request is a way of asking the other developers working on the same project if you can merge your changes into the master branch. The other developers will then take a look at your code, comment on it through github, and maybe even request changes to refactor your code.

So here's how you make a pull request.
* On github, navigate to the repository.
* Click on the "pull tequests" tab.
* Click on the green button that says "New pull request".
* On the tab that says "compare: ...", select your branch.
* Finallly, click the green button and your pull request is in!

If someone requests changes or leaves a comment on your pull request, you can just make another commit to the branch you want to merge – there's no need to make a new pull request, which is awesome.

## Final things
Here's the way we'll do pull requests and code review in TPose-labs: I review all your code, and you review my code. Code style will follow the pep-8 guidelines, and we can both find ways to refactor each other's code. To test your code for potential pep-8 violations, use flake8. To get flake8, run `pip install flake8`, and, to run flake8, run `flake8 <python_file_name>`.