# Rename files and folders

Can rename string in files and folder in a directory structure with `rename` .

```bash 
find . -depth -exec rename 's/oldstring/newstring/g' {} \;
```

### Install rename

```bash
cpan
cpan[1](http://search.cpan.org/)> install File::Rename 
```



