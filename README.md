import requests

# GitHub kişisel erişim token'ınızı buraya girin
token = "your_github_token"

# GitHub kullanıcı adı ve depo adı
username = "your_github_username"
repo = "your_repo_name"

# README dosyası için içerik
readme_content = """
# My Awesome Project

This project is awesome because it solves a problem efficiently.

## Features
- Feature 1
- Feature 2
- Feature 3

## Installation
```bash
git clone https://github.com/{username}/{repo}.git
