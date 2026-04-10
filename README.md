# erikbarbara.com
**GitHub Grab Bag**
```
gh auth login
gh repo clone https://github.com/erikbarbara/erikbarbara.com.git
git push
gh auth logout
```

**View draft essay**
```
cd essays-by-erik/
bundle exec jekyll serve
```

**Generate essay HTML**
```
cd essays-by-erik/
bundle exec jekyll build --destination ../essays
```

**Publish to AWS S3**
```
aws s3 sync --delete . s3://erikbarbara.com \
  --exclude ".*" \
  --exclude "*/.*" \
  --exclude "essays-by-erik" \
  --exclude "essays-by-erik/*" \
  --exclude README.md
```
