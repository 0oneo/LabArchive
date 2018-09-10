### Background

Company project was writing with python3, I only install python2.7. So I need to install python3

### Process

#### Try & Result
```sh
brew install python3
```
hint me to update python using:
```sh
brew upgrade python
```

python3 was succesfully installed. But only python2.7 was also soft linked to python 3.7.

#### solve link problem

```sh
brew unlink python@2
brew link python@2
brew link python@3
```
