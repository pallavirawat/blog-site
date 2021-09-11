## Personal blog
The template used in build with hugo using theme https://hugoloveit.com/theme-documentation-basics/


## Deployment
This will create a build and publish it to pallavirawat.github.io
```shell script
./deploy.sh "commit details"
```

## Local run in dev mode
This will also show all unpublished drafted posts
```shell script
hugo server -D
```

## Production run in local machine
useful for viewing some settings which are only acttive in prod like comment config, cdn, fingerprintt etc
```shell script
hugo serve -e production
```

## Hugo content commands
to create a new post
```
hugo new posts/my-first-post.md
```
this will put in some basic details like data time etc

#useful links
hugo shortcuts
https://gohugo.io/content-management/shortcodes#figure

