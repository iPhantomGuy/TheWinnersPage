I created the Git repository on github, and cloned it locally with SourceTree.
I made a new Windows Form Application project in the repository. 

Then I made 3 other repositories and put the nuget.exe in each repo. After that, I used the nuget spec command to make a nuget .nuspac package. 
I added the <files> element and put each image in there. 

Then I used the nuget pack method to create a .nupkg file. At this time, I made three different packages with each containing different images.

Next, I used the nuget package manager to import the previously created packages, so I could use the images. Then, I edited the form so it would show the right content.
However, a problem showed up. I forgot to edit the .gitignore so it would not commit the images themself. 
So, I had to use git rebase to go back to the commit before the images were commited. 
Then I had to use git push --force, so git wouldn't give notice that I couldn't push. 

Afterwards, I ran a few scenarios to see the effect of those changes. 
First I changed the images in the nuget packages. I again used nuget pack to make a nuget package, but I changed the version from 1.0.0 to 1.0.1. 
This resulted in Visual Studio giving me notice that there was an update for one of my nuget packages. When I updated the package, I had to manually edit the images.
What I also noticed, was that it kept the images of the previous version of the package. 