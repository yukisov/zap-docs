zap-docs
========

- OWASP ZAP's tips

How to update articles
-----

1. Edit articles
2.  $ git add .
3. $ gitbook serve
    * check the content on your browser
4. $ git commit -m 'Comment'
5. $ git push
6. $ git checkout gh-pages
7. $ git rm -rf .
8. $ mv _book/* ./
9. $ git rm _book
10. $ git add .
11. $ git commit -m 'Comment'
12. $ git push

About GitBook
-----
- [GitbookIO/gitbook](https://github.com/GitbookIO/gitbook)
