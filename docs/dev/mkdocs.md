# MKDocs

## Troubleshooting

### GitHub Pages Custom Domain
If you are deploying your MKDocs site via the `mkdocs gh-deploy` command and finding that it is resetting your custom domain name settings, there is a solution for that.

There is an [undocumented feature][1] of MKDocs that it will publish your site to GitHub Pages using a custom domain name _only_ if you create a file called `CNAME` which contains the custom domain name of your site.  If you do not create this special file, your site's custom domain name will be wiped out each time you deploy your site.

For example if your site was called `modelmodem.com` you would (and I did) create a file called `CNAME` and place it at the root of your [`docs_dir`][2].

```
modelmodem.com
```

File `/docs/CNAME`
{: .caption }

[1]: https://github.com/mkdocs/mkdocs/issues/1257
[2]: https://www.mkdocs.org/user-guide/styling-your-docs/#using-the-docs_dir