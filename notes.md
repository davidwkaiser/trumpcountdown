At first, this worked locally but not on Heroku
It appeared that the JS wasn't compiling.
I was getting an error that Bootstrap needed Tether to run Tooltips
So I added the Tether gem: 'rails-assets-tether', '>= 1.1.0'
I also put it into the application.js file
//= require tether
I added it after jquery but before bootstrap.
Lastly, I ran a pre-compile on the command line:
RAILS_ENV=production bundle exec rake assets:precompile

Then i committed the results to git and github
before deploying to Heroku.
Now it works!

Got it, here is the plan:
1> push to github, merge, checkout master, pull
2> run precompile
3> git add.
4> git commit -m "precompile"
5> git push heroku master

Now it sticks!