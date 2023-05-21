TO DEPLOY:

$ REPO=`git config remote.origin.url`
$ rm -r _site/
$ git clone $REPO _site
$ cd _site
$ git checkout gh-pages
$ cd ..
$ rm -rf _site/**/* || exit 0
$ bundle exec jekyll build
$ cp CNAME _site/
$ cd _site
$ git add -A . 
$ git commit -m "Deploy to GitHub Pages: ${SHA}"
$ git push

